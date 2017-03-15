---
title: "__nogc | Microsoft Docs"
ms.custom: ""
ms.date: "11/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__nogc_cpp"
  - "__nogc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__nogc 형식 선언"
  - "관리 되지 않는 형식 클래스 [c + +]"
  - "관리 되지 않는 클래스의 선언"
  - "관리되지 않는 클래스"
ms.assetid: 3e7f1b09-0fc3-4a8f-9458-a22f7a38ce45
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# __nogc
> [!NOTE]
>  이 항목은 Managed Extensions for C\+\+ 버전 1에만 적용됩니다. 이 구문은 버전 1 코드를 유지하기 위해서만 사용해야 합니다. 새 구문에서는 형식을 관리되지 않음으로 명시적으로 표시하지 않아도 됩니다.  
  
 관리되지 않는 형식을 명시적으로 선언합니다.  
  
## 구문  
  
```  
  
__nogc   
class-specifier  
__nogc   
struct-specifier  
__nogc  
interface-specifier  
__nogc  
array-specifier  
__nogc  
pointer-specifier  
__nogc  
new  
  
```  
  
## 설명  
 `__nogc` 키워드는 개체가 표준 C\+\+ 힙에 할당되도록 명확하게 지정하기 위해 사용됩니다. 이 키워드는 선택 사항입니다. 클래스 선언 앞에 `__gc` 또는 `__nogc`를 지정하지 않은 경우 기본적으로 `__nogc`로 설정됩니다.  
  
 이 형식의 개체는 표준 C\+\+ 힙에서 할당되고 관리되는 개체의 제한이 적용되지 않는다는 점에서 표준 C\+\+ 개체와 유사합니다.  
  
 `__nogc` 키워드는 \_\_value 형식의 개체가 명시적으로 표준 C\+\+ 힙에 할당될 때 사용할 수도 있습니다.  
  
```  
// keyword__nogc.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__value struct V {   
   int i;  
};  
int main() {  
   V * v = __nogc new V;  
   v->i = 10;  
   delete v;  
}  
```  
  
> [!NOTE]
>  `__nogc` 키워드는 배열 및 포인터 형식에도 적용할 수 있습니다.  
  
 gc 포인터는 `__nogc` 클래스의 멤버일 수 없습니다.`__nogc` 클래스에 값 형식을 포함하는 지침은 [\_\_value](../misc/value.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 관리되지 않는 클래스가 \(`X`\)로 선언되고 개체가 인스턴스화되고 수정됩니다.  
  
```  
// keyword__nogc_2.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__nogc class X {  
public:  
   int i;  
};  
  
int main() {  
   X* x;   // declares an unmanaged pointer of type X  
   x = new X();   // creates unmanaged object of type X on the C++ heap  
   Console::WriteLine(x->i);  
  
   x->i = 4;   // modifies unmanaged object  
   Console::WriteLine(x->i);  
  
   delete x;   // call C++ delete operator to clean up resource  
}  
```  
  
 **48378256 4**