---
title: "__abstract | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__abstract_cpp"
  - "__abstract"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "추상 클래스 [c + +]"
  - "__abstract 키워드"
ms.assetid: fc6eee5e-9f07-4438-97f7-f2e124263575
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# __abstract
> [!NOTE]
>  이 항목은 Managed Extensions for C\+\+ 버전 1에만 적용됩니다. 이 구문은 버전 1 코드를 유지하기 위해서만 사용해야 합니다. 참조 [abstract](/visual-cpp/windows/abstract-cpp-component-extensions) 동등한 기능을 사용 하 여 새 구문에서에 대 한 내용은 합니다.  
  
 직접 인스턴스화할 수 없는 관리되는 클래스를 선언합니다.  
  
## 구문  
  
```  
  
__abstract   
class-specifier  
__abstract   
struct-specifier  
  
```  
  
## 설명  
 `__abstract` 키워드는 대상 클래스를 다른 클래스의 기본 클래스로만 사용할 수 있도록 선언합니다. 클래스나 구조체에 `__abstract`를 적용하는 경우 결과가 \_\_gc 클래스나 \_\_gc 구조체임을 의미하지 않습니다.  
  
 [abstract](/visual-cpp/cpp/abstract-classes-cpp) 기본 클래스에 대한 C\+\+ 개념과 달리, `__abstract` 키워드를 사용하는 클래스는 멤버 함수를 정의할 수 있습니다.  
  
> [!NOTE]
>  `__abstract` 키워드는 `__value` 또는 `__sealed` 키워드와 함께 사용할 수 없으며 `__interface` 키워드와 함께 사용하면 중복됩니다.  
  
## 예제  
 다음 코드 예제에서 `Derived` 클래스는 추상 기본 클래스\(`Base`\)에서 파생됩니다. 두 클래스에 대한 인스턴스화가 시도되지만 `Derived`만 성공합니다.  
  
```  
// keyword__abstract.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__abstract __gc class Base {  
   int BaseFunction() {  
      return 0;  
   }  
};  
  
__gc class Derived: public Base {};  
  
int main() {  
   Base* MyBase = new Base();   // C3622 can't BAse is abstract  
   Derived* MyDerived = new Derived();  
}  
```