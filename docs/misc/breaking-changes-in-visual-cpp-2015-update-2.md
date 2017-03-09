---
title: "Visual C++ 2015 업데이트 2의 주요 변경 내용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5545ce3f-d8da-4007-88b7-8dba7dcd4d10
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "mithom"
---
# Visual C++ 2015 업데이트 2의 주요 변경 내용
Visual C\+\+ 2015 업데이트 2 CTP로 업그레이드하는 경우 이전에 컴파일하고 올바르게 실행한 코드에서 컴파일 및\/또는 런타임 오류가 발생할 수 있습니다. 그러한 문제를 일으키는 컴파일러 또는 런타임 동작의 변경 내용은 *주요 변경 내용*이라고 하며 일반적으로 C\+\+ 언어 표준, 함수 서명 또는 메모리의 레이아웃 개체 수정에 필요합니다.  
  
 이 문서의 나머지 부분에서는 Visual C\+\+ 2015 업데이트 2 CTP의 구체적인 주요 변경 내용을 설명하며, 이 문서에서 “새 동작” 또는 “현재”라는 용어는 해당 버전을 나타냅니다. "이전 동작" 및 "이전"은 Visual C\+\+ 2015 업데이트 1 이전 릴리스를 나타냅니다. Visual C\+\+ 2015의 최초 릴리스와 Visual C\+\+ 2015 업데이트 1 사이에 발생한 주요 변경 내용에 대한 자세한 내용은 [업데이트 1의 주요 변경 내용](../misc/breaking-changes-in-visual-cpp-2015-update-1.md) 항목을 참조하세요. Visual C\+\+ 2013과 Visual C\+\+ 2015 사이에 발생한 주요 변경 내용에 대한 자세한 내용은 [Visual C\+\+ 2015의 주요 변경 내용](/visual-cpp/porting/visual-cpp-change-history-2003-20151) 항목을 참조하세요.  
  
-   [컴파일러 주요 변경 내용](#BK_compiler)  
  
##  <a name="BK_compiler"></a> Visual C\+\+ 컴파일러  
  
-   **SFINAE 식에 대한 부분 지원으로 인해 추가 경고 및 오류가 발생할 수 있습니다.**  
  
     이전 버전의 컴파일러는 SFINAE 식에 대한 지원 부족으로 `decltype` 지정자 내의 특정 유형의 식을 구문 분석하지 않았습니다. 이 이전 동작은 올바르지 않으며 C\+\+ 표준을 따르지 않습니다. 지속적인 규칙 향상으로 인해 이제 컴파일러는 이러한 식을 구문 분석하고 SFINAE 식에 대한 부분 지원을 합니다. 결과적으로 이제 컴파일러는 이전 버전의 컴파일러가 구문 분석하지 않았던 식에서 경고 및 오류를 발생합니다.  
  
     이 새로운 동작이 아직 선언되지 않은 형식을 포함하는 `decltype` 식을 구문 분석할 때, 컴파일러는 결과적으로 오류 C2039를 발생합니다.  
  
 **오류 C2039: *'형식'*:이 *'전역 네임스페이스'*의 멤버가 아닙니다.**     예제 1: 선언되지 않은 형식 사용\(이전\)  
  
    ```cpp  
    struct s1  
    {  
      template <typename T>  
      auto f() -> decltype(s2<T>::type::f());  // error C2039  
  
      template<typename>  
      struct s2 {};  
    }  
    ```  
  
     예제 1\(이후\)  
  
    ```cpp  
    struct s1  
    {  
      template <typename>  // forward declare s2struct s2;  
  
      template <typename T>  
      auto f() -> decltype(s2<T>::type::f());  
  
      template<typename>  
      struct s2 {};  
    }  
    ```  
  
     이 새로운 동작이 종속 이름이 형식임을 지정하기 위해 필요한 `typename` 키워드 사용이 누락된 `decltype` 식을 구문 분석할 때 컴파일러는 컴파일러 오류 C2923과 함께 컴파일러 경고 C4346을 발생합니다.  
  
 **경고 C4346: *'S2\<T\>::Type'*: 종속 이름이 형식이 아닙니다. 오류 C2923: *'s1'*: *'S2\<T\>::Type'*은 매개 변수 *'T'*에 대한 올바른 템플릿 형식 인수가 아닙니다.**     예제 2: 종속 이름이 형식이 아님\(이전\)  
  
    ```cpp  
    template <typename T>  
    struct s1  
    {  
      typedef T type;  
    };  
  
    template <typename T>  
    struct s2  
    {  
      typedef T type;  
    };  
  
    template <typename T>  
    T declval();  
  
    struct s  
    {  
      template <typename T>  
      auto f(T t) -> decltype(t(declval<S1<S2<T>::type>::type>()));  // warning C4346, error C2923  
    };  
    ```  
  
     예제 2\(이후\)  
  
    ```cpp  
    template <typename T> struct s1 {...};  // as above  
    template <typename T> struct s2 {...};  // as above  
  
    template <typename T>  
    T declval();  
  
    struct s  
    {  
      template <typename T>  
      auto f(T t) -> decltype(t(declval<S1<typename S2<T>::type>::type>()));  
    };  
    ```  
  
-   `volatile` **멤버 변수가 암시적으로 정의된 생성자와 대입 연산자를 막음**  
  
     이전 버전의 컴파일러는 `volatile` 멤버 변수가 있는 클래스가 기본 복사\/이동 생성자 및 기본 복사 대입 연산자를 자동으로 생성하도록 허용했습니다. 이 이전 동작은 올바르지 않으며 C\+\+ 표준을 따르지 않습니다. 이제 컴파일러는 volatile 멤버 변수가 있는 클래스는 특수한 생성자 및 대입 연산자가 있는 것으로 간주하여 이러한 연산자의 기본 구현이 자동으로 생성되는 것을 막습니다.  이러한 클래스가 공용 구조체\(또는 클래스 내의 익명 공용 구조체\)의 멤버이면 공용 구조체\(또는 익명 공용 구조체를 포함하는 클래스\)의 복사\/이동 생성자 및 복사\/이동 대입 연산자는 삭제된 것으로 암시적으로 정의됩니다. 명시적으로 정의하지 않고 공용 구조체\(또는 익명 공용 구조체를 포함하는 클래스\)를 만들거나 복사하려 하면 오류가 발생하며 컴파일러에서 결과적으로 컴파일러 오류 C2280을 발생합니다.  
  
 **오류 C2280: *'B::B\(const B &\)'*: 삭제된 함수를 참조하려고 합니다.**     예제\(이전\)  
  
    ```cpp  
    struct A  
    {  
      volatile int i;  
      volatile int j;  
    };  
  
    extern A* pa;  
  
    struct B  
    {  
      union  
      {  
        A a;  
        int i;  
      };  
    };  
  
    B b1 {*pa};  
    B b2 (b1);  // error C2280  
    ```  
  
     예제\(이후\)  
  
    ```cpp  
    struct A  
    {  
      int i;int j;  
    };  
  
    extern volatile A* pa;  
  
    A getA()  // returns an A instance copied from contents of pa  
    {  
      A a;  
      a.i = pa->i;  
      a.j = pa->j;  
      return a;  
    }  
  
    struct B;  // as above  
  
    B b1 {GetA()};  
    B b2 (b1);  // error C2280  
    ```  
  
-   **정적 멤버 함수는 cv 한정자를 지원하지 않습니다.**  
  
     이전 버전의 Visual C\+\+ 2015는 정적 멤버 함수에 cv 한정자가 포함되는 것을 허용했습니다. 이 동작은 Visual C\+\+ 2015 및 Visual C\+\+ 2015 업데이트 1에서의 문제 재발로 인한 것입니다. Visual C\+\+ 2013 및 이전 버전의 Visual C\+\+는 이런 식으로 작성된 코드를 거부합니다. Visual C\+\+ 2015 및 Visual C\+\+ 2015 업데이트 1의 동작은 잘못되었으며 C\+\+ 표준과 일치하지 않습니다.  Visual Studio 2015 업데이트 2는 이런 식으로 작성된 코드를 거부하며 대신 컴파일러 오류 C2511을 발생합니다.  
  
 **오류 C2511: 'void A::func\(void\) const': 오버로드된 멤버 함수를 'A'에서 찾을 수 없습니다.**     예제\(이전\)  
  
    ```  
    struct A  
    {  
      static void func();  
    };  
  
    void A::func() const {}  // C2511  
  
    ```  
  
     예제\(이후\)  
  
    ```  
    struct A  
    {  
      static void func();  
    };  
  
    void A::func() {}  // removed const  
  
    ```  
  
-   **열거형의 정방향 선언은 WinRT 코드에서 허용되지 않습니다**\(\/ZW만 영향을 줌\).  
  
     WinRT\(Windows 런타임\)에 대해 컴파일된 코드는 `enum` 형식이 정방향 선언되는 것을 허용하지 않습니다. \/clr 컴파일러 스위치를 사용하여 관리되는 C\+\+ 코드가 .Net Framework에 대해 컴파일되는 경우와 비슷합니다. 이 동작은 열거형의 크기를 항상 알 수 있으며 WinRT 형식 시스템에 올바르게 프로젝션될 수 있음을 확인합니다. 컴파일러는 이러한 방식으로 작성된 코드를 거부하고 컴파일러 오류 C3197과 함께 컴파일러 오류 C2599를 발생합니다.  
  
 **오류 C2599: *'CustomEnum'*: WinRT 열거형의 정방향 선언은 허용되지 않습니다. 오류 C3197: *'public'*: 정의에만 사용할 수 있습니다.**     예제\(이전\)  
  
    ```cpp  
    namespace A {  
      public enum class CustomEnum: int32;  // forward declaration; error C2599, error C3197  
    }  
  
    namespace A {  
      public enum class CustomEnum: int32  
      {  
        Value1  
      };  
    }  
  
    public ref class Component sealed  
    {  
    public:  
      CustomEnum f()  
      {  
        return CustomEnum::Value1;  
      }  
    };  
    ```  
  
     예제\(이후\)  
  
    ```cpp  
  
              // forward declaration of CustomEnum removed  
  
    namespace A {  
      public enum class CustomEnum: int32  
      {  
        Value1  
      };  
    }  
  
    public ref class Component sealed  
    {  
    public:  
      CustomEnum f()  
      {  
        return CustomEnum::Value1;  
      }  
    };  
    ```  
  
-   **오버로드된 멤버가 아닌 연산자 new 및 연산자 delete는 인라인으로 선언할 수 없습니다**\(수준 1\(\/ W1\)이 기본적으로 설정되어 있음\).  
  
     이전 버전의 컴파일러는 멤버가 아닌 연산자 new 및 연산자 delete 함수가 인라인으로 선언될 때 경고를 발생하지 않습니다. 이 방식으로 작성된 코드는 형식이 잘못되었으며\(진단이 필요하지 않음\) 진단하기 힘들 수 있는 일치하지 않는 new 및 delete 연산자로 인해 특히 크기가 지정된 할당 해제와 함께 사용 시 메모리 문제를 일으킬 수 있습니다.   이제 컴파일러는 이런 식으로 작성된 코드를 식별하기 위해 경고 C4595를 발생합니다.  
  
 **경고 C4595: *'new 연산자'*: 멤버가 아닌 연산자 new 또는 delete 함수는 인라인으로 선언될 수 없습니다.**     예제\(이전\)  
  
    ```cpp  
  
              inline void* operator new(size_t sz)  // warning C4595  
    {  
      ...  
    }  
    ```  
  
     예제\(이후\)  
  
    ```cpp  
  
              void* operator new(size_t sz)  // removed inline  
    {  
      ...  
    }  
    ```  
  
     이러한 방식으로 작성된 코드를 수정하려면 연산자 정의를 헤더 파일에서 해당하는 소스 파일로 이동해야 합니다.