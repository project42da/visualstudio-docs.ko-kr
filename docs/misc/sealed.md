---
title: "__sealed | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__sealed_cpp"
  - "__sealed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sealed 키워드[C++]"
  - "__sealed 키워드"
ms.assetid: 9e5f778a-4ad8-468d-9c44-783e576fb49b
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# __sealed
> [!NOTE]
>  이 항목은 Managed Extensions for C\+\+ 버전 1에만 적용됩니다. 이 구문은 버전 1 코드를 유지하기 위해서만 사용해야 합니다. 참조 [sealed](/visual-cpp/windows/sealed-cpp-component-extensions) 동등한 기능을 사용 하 여 새 구문에서에 대 한 내용은 합니다.  
  
 메서드가 재정의되거나 클래스가 기본 클래스가 되지 않도록 합니다.  
  
## 구문  
  
```  
  
__sealed   
class-specifier  
__sealed   
struct-specifier  
__sealed   
function-declarator  
  
```  
  
## 설명  
 `__sealed` 키워드는 클래스 메서드를 재정의할 수 없거나 클래스가 기본 클래스가 될 수 없도록 지정합니다.  
  
 `__sealed` 키워드를 사용할 때는 다음 사항에 유의하십시오.  
  
-   `__sealed` 가상 메서드를 재정의할 수 없습니다.  
  
-   비가상 멤버 메서드가 `__sealed`로 표시되면 `__sealed` 한정자가 무시됩니다.  
  
-   `__sealed` 메서드는 순수 메서드일 수 없습니다.  
  
-   **\_\_sealed** 와 함께 사용할 경우에 키워드가 허용 되지 않습니다는 [\_\_interface](/visual-cpp/cpp/interface) 키워드입니다.  
  
 클래스나 구조체를 `__sealed`로 표시하면 클래스를 기본 클래스로 사용할 수 없습니다. 예:  
  
```  
__sealed __gc class A {  
   // ...  
};  
// error: cannot derive from a sealed class  
__gc class B : public A { /* ...*/ };  
```  
  
> [!NOTE]
>  `__sealed` 키워드는 `__abstract` 키워드와 함께 사용할 수 없습니다.  
  
## 예제  
 다음 예제에서는 sealed 가상 메서드\(`f`\)가 선언됩니다.`main()`에서 함수가 재정의되고 컴파일러 오류가 발생합니다.  
  
```  
// keyword__sealed.cpp  
// compile with: /clr:oldSyntax  
  
#using <mscorlib.dll>  
extern "C" int printf_s(const char*, ...);  
  
__gc struct I  
{  
    __sealed virtual void f()  
    {   
        printf_s("I::f()\n");   
    }  
    virtual void g()  
    {  
        printf_s("I::g()\n");  
    }  
};  
  
__gc struct A : I   
{  
    void f() // C3248 sealed function  
    {   
        printf_s("A::f()\n");   
    }     
    void g()  
    {  
        printf_s("A::g()\n");  
    }  
};  
  
int main()  
{  
    A* pA = new A;  
  
    pA->f();  
    pA->g();  
}  
```