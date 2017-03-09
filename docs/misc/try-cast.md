---
title: "__try_cast | Microsoft Docs"
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
  - "__try_cast"
  - "__try_cast_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__try_cast 키워드"
  - "캐스팅 실패"
  - "예외, 캐스팅 실패"
  - "캐스팅 실패 예외를 throw합니다."
ms.assetid: e9e5da3a-f5b9-4915-b30a-a432e8574d03
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# __try_cast
**참고** 이 항목은 Managed Extensions for C\+\+ 버전 1에만 적용됩니다. 이 구문은 버전 1 코드를 유지하기 위해서만 사용해야 합니다. 참조 [safe\_cast](/visual-cpp/windows/safe-cast-cpp-component-extensions) 동등한 기능을 사용 하 여 새 구문에서에 대 한 내용은 합니다.  
  
 지정된 캐스트를 수행하거나 캐스트가 실패한 경우 예외를 throw합니다.  
  
## 구문  
  
```  
  
__try_cast <  
 type-id  
 >  
(  
expression   
)  
  
```  
  
## 설명  
 `__try_cast` 키워드\([dynamic\_cast](/visual-cpp/cpp/dynamic-cast-operator)와 동작이 유사함\)는 지정된 캐스팅 연산이 실패할 때마다 자동으로 **System::InvalidCastException** 형식의 예외를 throw하도록 지원합니다.  
  
 응용 프로그램의 테스트 단계 중에 `__try_cast` 키워드를 사용하여 가능한 캐스팅 실패에 대해 자동으로 경고할 수 있습니다.  
  
 Managed Extensions for c \+ \+ 이식 하는 경우 대체 `__try_cast` 사용 하 여 호출 [safe\_cast](/visual-cpp/windows/safe-cast-cpp-component-extensions)합니다.  
  
 `__try_cast`는 값 형식\([\_\_value](../misc/value.md)\)에 대한 포인터의 캐스트에서 작동하지 않습니다. 그 이유는 런타임에 해당 형식을 확인할 수 없기 때문입니다.  
  
## 예제  
 다음 예제에서는 포인터\(`Derived` 형식\)를 다른 포인터\(`MoreDerived` 형식\)로 캐스팅하려고 합니다. 캐스팅에 실패하면 catch 블록에서 catch되어 보고됩니다.  
  
```  
// keyword__try_cast.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__gc struct Base {};   
__gc struct Derived : Base {};  
__gc struct MoreDerived : Derived {};  
  
int main() {  
   Base*bp = new Derived;  
   try {  
       MoreDerived* mdp = __try_cast<MoreDerived*>(bp);  
   }  
   catch(System::InvalidCastException*) {  
       Console::WriteLine("Could not cast 'bp' to MoreDerived*");  
   }  
}  
```  
  
## 출력  
  
```  
Could not cast 'bp' to MoreDerived*  
```