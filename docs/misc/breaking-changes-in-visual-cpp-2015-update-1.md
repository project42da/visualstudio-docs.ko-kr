---
title: "Visual C++ 2015 업데이트 1의 주요 변경 내용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c0b1c2b-e1cf-4767-885b-b98df9b3730e
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "mithom"
manager: "ghogen"
---
# Visual C++ 2015 업데이트 1의 주요 변경 내용
Visual C\+\+ 2015 업데이트 1로 업그레이드하는 경우 이전에 컴파일하고 올바르게 실행한 코드에서 컴파일 및\/또는 런타임 오류가 발생할 수 있습니다. 그러한 문제를 일으키는 컴파일러 또는 런타임 동작의 변경 내용은 *주요 변경 내용*이라고 하며 일반적으로 C\+\+ 언어 표준, 함수 서명 또는 메모리의 레이아웃 개체 수정에 필요합니다.  
  
 이 문서의 나머지 부분에서는 Visual C\+\+ 2015 업데이트 1의 구체적인 주요 변경 내용을 설명하며, 이 문서에서 “새 동작" 또는 “현재"라는 용어는 해당 버전을 나타냅니다. "이전 동작" 및 "이전"은 Visual Studio 2015의 초기 릴리스 및 이전 릴리스를 나타냅니다. Visual Studio 2013과 Visual Studio 2015 사이에 발생한 주요 변경 내용에 대한 자세한 내용은 [Visual C\+\+ 2015의 주요 변경 내용](/visual-cpp/porting/visual-cpp-change-history-2003-20151)을 참조하세요.  
  
-   [컴파일러 주요 변경 내용](#BK_compiler)  
  
##  <a name="BK_compiler"></a> Visual C\+\+ 컴파일러  
  
-   **개인 가상 기본 클래스 및 간접 상속**  
  
     이전 버전의 컴파일러에서는 파생 클래스에서 *간접적으로 파생된* `private virtual` 기본 클래스의 멤버 함수를 호출할 수 있었습니다. 이 이전 동작은 올바르지 않으며 C\+\+ 표준을 따르지 않습니다. 컴파일러는 이러한 방식으로 작성된 코드를 더 이상 허용하지 않으며, 결과적으로 컴파일러 오류 C2280이 발생합니다.  
  
 **오류 C2280: *'void \*S3::\_\_delDtor\(unsigned int\)'*: 삭제된 함수를 참조하려고 합니다.**     예제\(이전\)  
  
    ```cpp  
    class base { protected: base(); ~base(); }; class middle: private virtual base {};class top: public virtual middle {}; void destroy(top *p) { delete p;  // }  
    ```  
  
     예제\(이후\)  
  
    ```cpp  
    class base;  // as above class middle: protected virtual base {}; class top: public virtual middle {}; void destroy(top *p) { delete p; }  
    ```  
  
     또는  
  
    ```  
    class base;  // as above class middle: private virtual base {}; class top: public virtual middle, private virtual bottom {}; void destroy(top *p) { delete p; }  
    ```  
  
-   **오버로드된 operator new 및 operator delete**  
  
     이전 버전의 컴파일러에서는 멤버가 아닌 `operator new` 및 멤버가 아닌 `operator delete`를 정적으로 선언할 수 있었으며 전역 네임스페이스 이외의 네임스페이스에서 선언할 수 있었습니다.  이 이전 동작은 프로그램에서 프로그래머가 의도한 `new` 또는 `delete` 연산자 구현을 호출하지 않아서 잘못된 자동 런타임 동작이 발생하는 위험을 초래했습니다. 컴파일러는 이러한 방식으로 작성된 코드를 더 이상 허용하지 않으며, 대신 컴파일러 오류 C2323이 발생합니다.  
  
 **오류 C2323: *'operator new'*: 멤버가 아닌 operator new 또는 delete 함수는 정적으로 선언하거나 전역 네임스페이스 이외의 네임스페이스에서 선언할 수 없습니다.**     예제\(이전\)  
  
    ```cpp  
  
    static inline void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // error C2323  
    ```  
  
     예제\(이후\)  
  
    ```cpp  
  
    void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // removed 'static inline'  
    ```  
  
     또한 컴파일러가 특정 진단을 제공하지는 않지만, 인라인 operator new는 잘못된 형식으로 간주됩니다.  
  
-   **비클래스 형식에서 'operator *type*\(\)'\(사용자 정의 변환\) 호출**  
  
     이전 버전의 컴파일러에서는 'operator *type*\(\)'을 자동으로 무시하면서 비클래스 형식에서 호출할 수 있었습니다. 이 이전 동작으로 잘못된 코드가 자동으로 생성되어 예기치 않은 런타임 동작이 발생하는 위험이 초래되었습니다. 컴파일러는 이러한 방식으로 작성된 코드를 더 이상 허용하지 않으며, 대신 컴파일러 오류 C2228이 발생합니다.  
  
 **오류 C2228: '.operator *type*' 왼쪽에 클래스\/구조체\/공용 구조체가 있어야 합니다.**     예제\(이전\)  
  
    ```cpp  
    typedef int index_t; void bounds_check(index_t index); void login(int column) { bounds_check(column.operator index_t());  // error C2228 }  
    ```  
  
     예제\(이후\)  
  
    ```cpp  
    typedef int index_t; void bounds_check(index_t index); void login(int column) { bounds_check(column);  // removed cast to 'index_t', 'index_t' is an alias of 'int' }  
    ```  
  
-   **상세 형식 지정자의 중복 typename**  
  
     이전 버전의 컴파일러에서는 상세 형식 지정자에 `typename`이 허용되었습니다. 이러한 방식으로 작성된 코드는 의미 체계가 잘못되었습니다. 컴파일러는 이러한 방식으로 작성된 코드를 더 이상 허용하지 않으며, 대신 컴파일러 오류 C3406이 발생합니다.  
  
 **오류 C3406: 상세 형식 지정자에는 'typename'을 사용할 수 없습니다.**     예제\(이전\)  
  
    ```cpp  
    template <typename class T> class container;  
    ```  
  
     예제\(이후\)  
  
    ```cpp  
    template <class T>  // alternatively, could be 'template <typename T>'; 'typename' is not elaborating a type specifier in this case class container;  
    ```  
  
-   **이니셜라이저 목록에서 배열의 형식 추론**  
  
     이전 버전의 컴파일러는 이니셜라이저 목록에서 배열의 형식 추론을 지원하지 않았습니다. 이제 컴파일러가 이러한 형태의 형식 추론을 지원합니다. 결과적으로 이니셜라이저 목록을 사용한 함수 템플릿 호출은 이제 모호하거나 이전 버전의 컴파일러와 다른 오버로드가 선택될 수 있습니다. 이러한 문제를 해결하려면 이제 프로그램에서 프로그래머가 의도한 오버로드를 명시적으로 지정해야 합니다.  
  
     이 새로운 동작으로 오버로드 확인에서 기록 후보와 똑같이 우수한 추가 후보를 고려하게 되는 경우, 호출이 모호해지며 결과적으로 컴파일러에서 컴파일러 오류 C2668이 발생합니다.  
  
 **오류 C2668: '*function*' : 오버로드된 함수에 대한 호출이 모호합니다.**     예제 1: 오버로드된 함수에 대한 호출이 모호합니다\(이전\).  
  
    ```cpp  
    // In previous versions of the compiler, code written in this way would unambiguously call f(int, Args...) template <typename... Args> void f(int, Args...);  // template <int N, typename... Args> void f(const int (&)[N], Args...); int main() { // The compiler now considers this call ambiguous, and issues a compiler error  f({3});  error C2668: 'f' ambiguous call to overloaded function }  
    ```  
  
     예제 1: 오버로드된 함수에 대한 호출이 모호합니다\(이후\).  
  
    ```cpp  
    template <typename... Args> void f(int, Args...);  // template <int N, typename... Args> void f(const int (&)[N], Args...); int main() { // To call f(int, Args...) when there is just one expression in the initializer list, remove the braces from it. f(3); }  
    ```  
  
     이 새로운 동작으로 오버로드 확인에서 기록 후보보다 더 일치되는 추가 후보를 고려하게 되는 경우, 호출이 새 후보로 명확하게 확인되므로 프로그래머가 의도한 것과 다른 프로그램 동작 변경을 초래할 수 있습니다.  
  
     예제 2: 오버로드 확인의 변경\(이전\)  
  
    ```cpp  
    // In previous versions of the compiler, code written in this way would unambiguously call f(S, Args...) struct S { int i; int j; }; template <typename... Args> void f(S, Args...); template <int N, typename... Args> void f(const int *&)[N], Args...); int main() { // The compiler now resolves this call to f(const int (&)[N], Args...) instead  f({1, 2}); }  
    ```  
  
     예제 2: 오버로드 확인의 변경\(이후\)  
  
    ```cpp  
    struct S;  // as before template <typename... Args> void f(S, Args...); template <int N, typename... Args> void f(const int *&)[N], Args...); int main() { // To call f(S, Args...), perform an explicit cast to S on the initializer list. f(S{1, 2}); }  
    ```  
  
-   **switch 문 경고의 복원**  
  
     이전 버전의 컴파일러에서는 `switch` 문과 관련된 기존 경고를 제거했습니다. 이제 이러한 경고가 복원되었습니다. 이제 컴파일러에서 복원된 경고가 발생합니다. 이제 특정 사례\(기본 사례 포함\)와 관련된 경고가 switch 문의 마지막 줄 대신, 잘못된 사례가 포함된 줄에서 발생합니다. 이제 과거와는 다른 줄에서 해당 경고가 발생하므로 이전에 `#pragma warning(disable:####)`을 사용하면 표시되지 않았던 경고가 더 이상 의도한 대로 숨겨지지 않을 수 있습니다. 이러한 경고를 의도한 대로 표시하지 않으려면 `#pragma warning(disable:####)` 지시문을 잠재적으로 잘못된 첫 번째 사례 위의 줄로 이동해야 할 수 있습니다. 다음은 복원된 경고입니다.  
  
 **경고 C4060: switch 문에 'case' 또는 'default' 레이블이 없습니다. 경고 C4061: 열거형 '*flags*'의 switch에 있는 '*bit1*' 열거자는 case 레이블에 의해 명시적으로 처리되지 않습니다. 경고 C4062: 열거형 '*flags*'의 switch에 있는 '*bit1*' 열거자는 처리되지 않습니다. 경고 C4063: case '*bit32*'는 열거형 '*flags*'의 switch에 대한 유효한 값이 아닙니다. 경고 C4064: 불완전한 열거형 '*flags*'의 switch 경고 C4065: switch 문에 'default'가 있으나 'case' 레이블이 없습니다. 경고 C4808: case '*value*'는 '*bool*' 형식의 switch 조건에 대한 유효한 값이 아닙니다. 경고 C4809: switch 문에 중복 'default' 레이블이 있습니다. 가능한 모든 'case' 레이블이 제공됩니다.**     C4063의 예제\(이전\)  
  
    ```cpp  
    class settings { public: enum flags { bit0 = 0x1, bit1 = 0x2, ... }; ... }; int main() { auto val = settings::bit1; switch (val) { case settings::bit0: break; case settings::bit1: break;  case settings::bit0 | settings::bit1:  // warning C4063 break; } };  
    ```  
  
     C4063의 예제\(이후\)  
  
    ```cpp  
    class settings {...};  // as above int main() { // since C++11, use std::underlying_type to determine the underlying type of an enum typedef std::underlying_type<settings::flags>::type flags_t; auto val = settings::bit1; switch (static_cast<flags_t>(val)) { case settings::bit0: break; case settings::bit1: break; case settings::bit0 | settings::bit1:  // ok break; } };  
    ```  
  
     복원된 다른 경고의 예는 해당 설명서에 제공됩니다.  
  
-   **\#include: 경로 이름에 부모 디렉터리 지정자 '..' 사용**\(\/Wall \/WX에만 영향을 줌\)  
  
     이전 버전의 컴파일러에서는`#include` 지시문의 경로 이름에서 부모 디렉터리 지정자\('..'\)의 사용을 검색하지 못했습니다. 이러한 방식으로 작성된 코드는 일반적으로 프로젝트 상대 경로를 부정확하게 사용하여 프로젝트의 외부에 존재하는 헤더를 포함합니다. 이 이전 동작은 프로그램이 프로그래머가 의도한 것과 다른 소스 파일을 포함하여 컴파일되거나 이러한 상대 경로가 다른 빌드 환경으로 이식되지 않는 위험을 초래했습니다. 이제 컴파일러는 이러한 방식으로 작성된 코드를 검색하여 프로그래머에게 알립니다. 그리고 사용하도록 설정된 경우 선택적으로 컴파일러 경고 C4464가 발생합니다.  
  
 **경고 C4464: include에 상대 경로\('..'\)가 포함되었습니다.**     예제\(이전\)  
  
    ```cpp  
    #include "..\headers\C4426.h"  // emits warning C4464  
    ```  
  
     예제\(이후\)  
  
    ```cpp  
    #include "C4426.h"  // add absolute path to 'headers\' to your project's include directories  
    ```  
  
     또한 컴파일러가 특정 진단을 제공하지는 않지만, 프로젝트의 포함 디렉터리를 지정하는 데 부모 디렉터리 지정자\(".."\)를 사용하지 않는 것이 좋습니다.  
  
-   **\#pragma optimize\(\)에서 헤더 파일의 끝을 넘어 확장**\(\/Wall \/WX에만 영향을 줌\)  
  
     이전 버전의 컴파일러에서는 변환 단위 내에 포함된 헤더 파일을 이스케이프하는 최적화 플래그 설정에 대한 변경 내용을 검색하지 못했습니다. 이제 컴파일러는 이러한 방식으로 작성된 코드를 검색하여 프로그래머에게 알립니다. 그리고 사용하도록 설정된 경우 잘못된 `#include`의 위치에서 선택적으로 컴파일러 경고 C4426이 발생합니다. 이 경고는 변경 내용이 명령줄 인수에 의해 컴파일러에 설정된 최적화 플래그와 충돌하는 경우에만 발생합니다.  
  
 **경고 C4426: 헤더를 포함한 후 변경된 최적화 플래그는 \#pragma optimize\(\) 때문일 수 있습니다.**     예제\(이전\)  
  
    ```cpp  
    // C4426.h #pragma optimize("g", off) ... // C4426.h ends // C4426.cpp #include "C4426.h"  // warning C4426  
    ```  
  
     예제\(이후\)  
  
    ```cpp  
    // C4426.h #pragma optimize("g", off) ... #pragma optimize("", on)  // restores optimization flags set via command-line arguments // C4426.h ends // C4426.cpp #include "C4426.h"  
    ```  
  
-   **\#pragma warning\(push\)**과 **\#pragma warning\(pop\)** 불일치\(\/Wall \/WX에만 영향을 줌\)  
  
     이전 버전의 컴파일러는 다른 소스 파일에서 `#pragma warning(push)` 상태 변경이 `#pragma warning(pop)` 상태 변경과 쌍을 이루는 것\(의도되는 경우가 드묾\)을 검색하지 못했습니다. 이 이전 동작으로 프로그램이 프로그래머가 의도한 것과 다르게 설정된 경고 집합으로 컴파일되어 잘못된 자동 런타임 동작이 발생하는 위험이 초래됩니다. 이제 컴파일러는 이러한 방식으로 작성된 코드를 검색하여 프로그래머에게 알립니다. 그리고 사용하도록 설정된 경우 일치하는 `#pragma warning(pop)`의 위치에서 선택적으로 컴파일러 경고 C5031이 발생합니다. 이 경고에는 해당 \#pragma warning\(push\)의 위치를 참조하는 메모가 포함됩니다.  
  
 **경고 C5031: \#pragma warning\(pop\): 다른 파일에서 푸시된 경고 상태 팝업 불일치 가능성 있음**     예제\(이전\)  
  
    ```cpp  
    // C5031_part1.h #pragma warning(push) #pragma warning(disable:####) ... // C5031_part1.h ends without #pragma warning(pop) // C5031_part2.h ... #pragma warning(pop)  // pops a warning state not pushed in this source file ... // C5031_part1.h ends // C5031.cpp #include "C5031_part1.h" // leaves #pragma warning(push) 'dangling' ... #include "C5031_part2.h" // matches 'dangling' #pragma warning(push), resulting in warning C5031 ...   
    ```  
  
     예제\(이후\)  
  
    ```cpp  
    // C5031_part1.h #pragma warning(push) #pragma warning(disable:####) ... #pragma warning(pop)  // pops the warning state pushed in this source file // C5031_part1.h ends without #pragma warning(pop) // C5031_part2.h #pragma warning(push)  // pushes the warning state pushed in this source file #pragma warning(disable:####) ... #pragma warning(pop) // C5031_part1.h ends // C5031.cpp #include "C5031_part1.h" // #pragma warning state changes are self-contained and independent of other source files or their #include order. ... #include "C5031_part2.h" ...   
    ```  
  
     흔하지 않지만 이러한 방식으로 작성된 코드가 때로 의도적인 경우도 있습니다. 이러한 방식으로 작성된 코드는 `#include` 순서의 변경에 민감합니다. 가능한 경우 소스 코드 파일에서 자동으로 포함된 방식으로 경고 상태를 관리하는 것이 좋습니다.  
  
-   **\#pragma warning\(push\) 불일치**\(\/Wall \/WX에만 영향을 줌\)  
  
     이전 버전의 컴파일러는 변환 단위의 끝에서 `#pragma warning(push)` 상태 변경 불일치를 검색하지 못했습니다. 이제 컴파일러는 이러한 방식으로 작성된 코드를 검색하여 프로그래머에게 알립니다. 그리고 사용하도록 설정된 경우 일치하지 않는 \#pragma warning\(push\)의 위치에서 선택적으로 컴파일러 경고 C5032가 발생합니다. 이 경고는 변환 단위에 컴파일 오류가 없는 경우에만 발생합니다.  
  
 **경고 C5032: 해당 \#pragma warning\(pop\)이 없는 \#pragma warning\(push\)이 검색되었습니다.**     예제\(이전\)  
  
    ```cpp  
    // C5032.h #pragma warning(push) #pragma warning(disable:####) ... // C5032.h ends without #pragma warning(pop) // C5032.cpp #include "C5032.h" ... // C5032.cpp ends -- the translation unit is completed without #pragma warning(pop), resulting in warning C5032 on line 1 of C5032.h  
    ```  
  
     예제\(이후\)  
  
    ```cpp  
    // C5032.h #pragma warning(push) #pragma warning(disable:####) ... #pragma warning(pop) // matches #pragma warning (push) on line 1 // C5032.h ends // C5032.cpp #include "C5032.h" ... // C5032.cpp ends -- the translation unit is completed without unmatched #pragma warning(push)  
    ```  
  
-   **개선된 \#pragma warning 상태 추적의 결과로 추가 경고가 발생할 수 있음**  
  
     이전 버전의 컴파일러는 의도된 모든 경고를 발생시키기에는 불충분한 수준으로 \#pragma warning 상태 변경을 추적했습니다. 이 동작으로 프로그래머가 의도한 것과 다른 상황에서 특정 경고가 효과적으로 표시되지 않는 위험이 초래됩니다. 이제 컴파일러는 \#pragma warning 상태\(특히 템플릿 내부의 \#pragma warning 상태 변경과 관련된 내용\)를 더욱 강력하게 추적하며, 선택적으로 새로운 경고 C5031 및 C5032가 발생합니다. 이러한 경고는 프로그래머가 `#pragma warning(push)` 및 `#pragma warning(pop)`의 의도하지 않은 사용을 찾는 데 도움이 됩니다.  
  
     개선된 \#pragma warning 상태 변경 추적의 결과로, 이전에 제대로 표시되지 않은 경고 또는 이전에 잘못 진단된 문제와 관련된 경고가 이제 발생할 수 있습니다.  
  
-   **접근할 수 없는 코드의 개선된 ID**  
  
     C\+\+ 표준 라이브러리의 변경 및 이전 버전의 컴파일러에 비해 향상된 인라인 함수 호출 기능을 통해 컴파일러가 이제 특정 코드에 접근할 수 없음을 증명할 수 있습니다. 이 새로운 동작으로 경고 C4720의 인스턴스가 새로 그리고 더욱 자주 발생할 수 있습니다.  
  
 **경고 C4720: 접근할 수 없는 코드입니다.**     최적화 프로세스에서 더 많은 함수 호출을 인라인하거나 중복 코드를 제거하거나 특정 코드에 접근할 수 없는지 확인할 수 있도록 하므로, 이 경고는 대개 최적화를 사용하면서 컴파일할 경우에만 발생할 수 있습니다. 경고 C4720의 새 인스턴스가 특히 [std::find](assetId:///std::find?qualifyHint=False&autoUpgrade=True)의 사용과 관련하여 try\/catch 블록에서 자주 발생했음을 관찰했습니다.  
  
     예제\(이전\)  
  
    ```cpp  
    try { auto iter = std::find(v.begin(), v.end(), 5); } catch(…) { do_something();  // ok }  
    ```  
  
     예제\(이후\)  
  
    ```cpp  
    try { auto iter = std::find(v.begin(), v.end(), 5); } catch(…) { do_something();  // warning C4702: unreachable code }  
    ```