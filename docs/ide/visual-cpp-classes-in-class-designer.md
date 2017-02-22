---
title: "Visual C++ Classes in Class Designer | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.classdesigner.inheritancelinelabel"
helpviewer_keywords: 
  - "Class Designer [Visual Studio], classes"
ms.assetid: 75e56f8c-11ef-42a3-b7ec-3d2cf25c581b
caps.latest.revision: 19
caps.handback.revision: 19
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Visual C++ Classes in Class Designer
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

클래스 디자이너에서는 C\+\+ 클래스가 지원되며 네이티브 C\+\+ 클래스는 상속 관계가 여러 개 있을 수 있다는 점만 제외하고는 Visual Basic 및 Visual C\# 클래스 모양과 동일한 방식으로 시각화됩니다.  클래스 모양을 확장하여 해당 클래스에 있는 추가 필드와 메서드를 표시하거나, 클래스 모양을 축소하여 공간을 절약할 수 있습니다.  
  
> [!NOTE]
>  클래스 디자이너에서는 공용 구조체가 지원되지 않습니다. 공용 구조체는 해당 데이터 멤버 중 가장 큰 데이터 멤버에 필요한 만큼만 메모리가 할당되는 특수한 클래스 형식입니다.  
  
## 단순 상속  
 둘 이상의 클래스를 클래스 다이어그램으로 끌 경우 해당 클래스에 클래스 상속 관계가 있으면 화살표로 클래스가 연결됩니다.  화살표는 기본 클래스의 방향을 가리킵니다.  예를 들어 클래스 다이어그램에 다음 클래스가 표시될 경우 B에서 A를 가리키는 화살표로 연결됩니다.  
  
```  
class A {};  
class B : A {};  
```  
  
 클래스 B만 클래스 다이어그램으로 끌고 B의 클래스 모양을 마우스 오른쪽 단추로 클릭한 다음 **기본 클래스 표시**를 클릭할 수도 있습니다.  이렇게 하면 기본 클래스 A가 표시됩니다.  
  
## 다중 상속  
 클래스 디자이너에서는 다중 클래스 상속 관계의 시각화가 지원됩니다.  *다중 상속*은 파생 클래스에 둘 이상의 기본 클래스 특성이 있는 경우에 사용됩니다.  다중 상속의 예제는 다음과 같습니다.  
  
```  
class Bird {};  
class Swimmer {};  
class Penguin : public Bird, public Swimmer {};  
```  
  
 둘 이상의 클래스를 클래스 다이어그램으로 끌 경우 해당 클래스에 다중 클래스 상속 관계가 있으면 화살표로 클래스가 연결됩니다.  화살표는 기본 클래스의 방향을 가리킵니다.  
  
 클래스 모양을 마우스 오른쪽 단추로 클릭하고 **기본 클래스 표시**를 클릭하면 선택한 클래스의 기본 클래스가 표시됩니다.  
  
> [!NOTE]
>  C\+\+ 코드의 경우 **파생 클래스 표시** 명령이 지원되지 않습니다.  클래스 뷰로 이동하고 형식 노드, **파생 형식** 하위 폴더를 차례로 확장한 다음 파행 클래스 형식을 클래스 다이어그램으로 끌면 파생 클래스를 표시할 수 있습니다.  
  
 다중 클래스 상속에 대한 자세한 내용은 [\(NOTINBUILD\) Multiple Inheritance](http://msdn.microsoft.com/ko-kr/3b74185e-2beb-4e29-8684-441e51d2a2ca) 및 [다중 기본 클래스](/visual-cpp/cpp/multiple-base-classes)를 참조하십시오.  
  
## 추상 클래스  
 클래스 디자이너는 추상 클래스\("추상 기본 클래스"라고도 함\)를 지원합니다.  인스턴스화 대상이 아니지만 다른 클래스를 파생하는 데 사용할 수 있는 클래스가 있습니다.  이 문서의 앞부분에 있는 "다중 상속"의 예제를 사용하면 `Bird` 클래스를 다음과 같이 개별 개체로 인스턴스화할 수 있습니다.  
  
```  
int main()  
{  
   Bird sparrow;  
   Bird crow;  
   Bird eagle;  
}  
```  
  
 그러나 `Swimmer` 클래스를 개별 개체로 인스턴스화하지 않을 수도 있습니다.  이 클래스에서 `Penguin`, `Whale` 및 `Fish` 등의 다른 동물 형식 클래스를 파생하기만 할 수 있습니다.  이 경우 `Swimmer` 클래스를 추상 기본 클래스로 선언합니다.  
  
 추상 클래스를 선언하려면 `abstract` 키워드를 사용합니다.  abstract로 표시된 멤버나 추상 클래스에 포함된 멤버는 가상 멤버이며, 추상 클래스에서 파생되는 클래스는 이러한 멤버를 구현해야 합니다.  
  
```  
class Swimmer abstract  
{  
   virtual void swim();  
   void dive();  
};  
```  
  
 최소한 하나의 순수 가상 함수를 포함시켜 클래스를 추상 클래스로 선언할 수도 있습니다.  
  
```  
class Swimmer  
{  
   virtual void swim() = 0;  
   void dive();  
};  
```  
  
 클래스 다이어그램에 이러한 선언을 표시하면 클래스 이름 `Swimmer`와 해당 순수 가상 함수 `swim`이 **추상 클래스**라는 표시와 함께 추상 클래스 모양에 기울임꼴로 표시됩니다.  추상 클래스 형식 모양은 테두리가 점선이라는 사실을 제외하고는 일반 클래스의 모양과 같습니다.  
  
 추상 기본 클래스에서 파생된 클래스는 기본 클래스의 각 순수 가상 함수를 재정의해야 합니다. 그렇지 않으면 파생 클래스를 인스턴스화할 수 없습니다.  예를 들어 `Swimmer` 클래스에서 `Fish` 클래스를 파생한 경우 `Fish`는 `swim` 메서드를 재정의해야 합니다.  
  
```  
class Fish : public Swimmer  
{  
   void swim(int speed);  
};  
  
int main()  
{  
   Fish guppy;  
}  
```  
  
 클래스 다이어그램에 이 코드를 표시하면 `Fish`에서 `Swimmer`로 상속 선이 그려집니다.  
  
## 익명 클래스  
 클래스 디자이너에서는 익명 클래스가 지원됩니다.  *익명 클래스 형식*은 식별자 없이 선언된 클래스입니다.  익명 클래스는 생성자나 소멸자를 가질 수 없고 함수에 인수로 전달될 수 없으며 함수의 반환 값으로 반환될 수 없습니다.  다음 예제와 같이 익명 클래스를 사용하여 클래스 이름을 형식 정의 이름으로 바꿀 수 있습니다.  
  
```  
typedef struct  
{  
    unsigned x;  
    unsigned y;  
} POINT;  
```  
  
 구조체가 익명일 수도 있습니다.  클래스 디자이너에서 익명 클래스 및 구조체는 각 형식과 동일하게 표시됩니다.  익명 클래스 및 구조체를 선언하고 표시할 수는 있지만 지정한 태그 이름이 클래스 디자이너에서는 사용되지 않습니다.  클래스 디자이너에서는 클래스 뷰에서 생성한 이름이 사용됩니다.  클래스 또는 구조체는 클래스 뷰 및 클래스 디자이너에 **\_\_unnamed**라는 요소로 나타납니다.  
  
 익명 클래스에 대한 자세한 내용은 [익명 클래스 형식](/visual-cpp/cpp/anonymous-class-types)를 참조하십시오.  
  
## 템플릿 클래스  
 클래스 디자이너에서는 템플릿 클래스의 시각화가 지원됩니다.  또한 중첩된 선언이 지원됩니다.  다음 표에서는 몇 가지 일반적인 선언을 보여 줍니다.  
  
|코드 요소|클래스 디자이너 뷰|  
|-----------|----------------|  
|`template <class T>`<br /><br /> `class A {};`|`A<T>`<br /><br /> 템플릿 클래스|  
|`template <class T, class U>`<br /><br /> `class A {};`|`A<T, U>`<br /><br /> 템플릿 클래스|  
|`template <class T, int i>`<br /><br /> `class A {};`|`A<T, i>`<br /><br /> 템플릿 클래스|  
|`template <class T, template <class K> class U>`<br /><br /> `class A {};`|`A<T, U>`<br /><br /> 템플릿 클래스|  
  
 다음 표에서는 부분 특수화의 몇 가지 예제를 보여 줍니다.  
  
|코드 요소|클래스 디자이너 뷰|  
|-----------|----------------|  
|`template<class T, class U>`<br /><br /> `class A {};`|`A<T, U>`<br /><br /> 템플릿 클래스|  
|`template<class T>`<br /><br /> `class A<T, T> {};`|`A<T, T>`<br /><br /> 템플릿 클래스|  
|`template <class T>`<br /><br /> `class A<T, int> {};`|`A<T, int>`<br /><br /> 템플릿 클래스|  
|`template <class T1, class T2>`<br /><br /> `class A<T1*, T2*> {};`|`A<T1*, T2*>`<br /><br /> 템플릿 클래스|  
  
 다음 표에서는 부분 특수화의 몇 가지 상속 예제를 보여 줍니다.  
  
|코드 요소|클래스 디자이너 뷰|  
|-----------|----------------|  
|`template <class T, class U>`<br /><br /> `class A {};`<br /><br /> `template <class TC>`<br /><br /> `class A<T, int> {};`<br /><br /> `class B : A<int, float>`<br /><br /> `{};`<br /><br /> `class C : A<int, int>`<br /><br /> `{};`|`A<T, U>`<br /><br /> 템플릿 클래스<br /><br /> `B`<br /><br /> 클래스<br /><br /> \(클래스 A를 가리킴\)<br /><br /> `C`<br /><br /> 클래스<br /><br /> \(클래스 A를 가리킴\)|  
  
 다음 표에서는 부분 특수화 템플릿 함수의 몇 가지 예제를 보여 줍니다.  
  
|코드 요소|클래스 디자이너 뷰|  
|-----------|----------------|  
|`class A`<br /><br /> `{`<br /><br /> `template <class T, class U>`<br /><br /> `void func(T a, U b);`<br /><br /> `template <class T>`<br /><br /> `void func(T a, int b);`<br /><br /> `};`|`A`<br /><br /> func\<T, U\> \(\+ 1 overload\)|  
|`template <class T1>`<br /><br /> `class A {`<br /><br /> `template <class T2>`<br /><br /> `class B {};`<br /><br /> `};`<br /><br /> `template<> template<>`<br /><br /> `class A<type>::B<type> {};`|`A<T1>`<br /><br /> 템플릿 클래스<br /><br /> `B<T2>`<br /><br /> 템플릿 클래스<br /><br /> \(클래스 B는 **중첩 형식** 아래의 클래스 A에 포함됨\)|  
|`template <class T>`<br /><br /> `class C {};`<br /><br /> `class A : C<int> {};`|`A`<br /><br /> 클래스<br /><br /> \-\> C\<int\><br /><br /> `C<T>`<br /><br /> 템플릿 클래스|  
  
 다음 표에서는 템플릿 상속의 몇 가지 예제를 보여 줍니다.  
  
|코드 요소|클래스 디자이너 뷰|  
|-----------|----------------|  
|`template <class T>`<br /><br /> `class C {};`<br /><br /> `template<>`<br /><br /> `class C<int> {`<br /><br /> `class B {};`<br /><br /> `}`<br /><br /> `class A : C<int>::B {};`|`A`<br /><br /> 클래스<br /><br /> \-\>B<br /><br /> `C<int>`<br /><br /> 클래스<br /><br /> \(클래스 B는 **중첩 형식** 아래의 클래스 C에 포함됨\)<br /><br /> `C<T>`<br /><br /> 템플릿 클래스|  
  
 다음 표에서는 정식 특수 클래스 연결의 몇 가지 예제를 보여 줍니다.  
  
|코드 요소|클래스 디자이너 뷰|  
|-----------|----------------|  
|`template <class T>`<br /><br /> `class C {};`<br /><br /> `template<>`<br /><br /> `class C<int> {};`<br /><br /> `class A : C<int> {};`<br /><br /> `class D : C<float> {};`|`A`<br /><br /> 클래스<br /><br /> \-\>C\<int\><br /><br /> `C<int>`<br /><br /> 클래스<br /><br /> `C<T>`<br /><br /> 템플릿 클래스<br /><br /> `D`<br /><br /> 클래스<br /><br /> \-\>C\<float\>|  
|`class B {`<br /><br /> `template <class T>`<br /><br /> `T min (const T &a, const T &b);`<br /><br /> `};`|`B`<br /><br /> min \<T\>|  
  
## 참고 항목  
 [Working with Visual C\+\+ Code \(Class Designer\)](../ide/working-with-visual-cpp-code-class-designer.md)   
 [클래스 및 구조체](/visual-cpp/cpp/classes-and-structs-cpp)   
 [익명 클래스 형식](/visual-cpp/cpp/anonymous-class-types)   
 [\(NOTINBUILD\) Multiple Inheritance](http://msdn.microsoft.com/ko-kr/3b74185e-2beb-4e29-8684-441e51d2a2ca)   
 [다중 기본 클래스](/visual-cpp/cpp/multiple-base-classes)   
 [템플릿](/visual-cpp/cpp/templates-cpp)