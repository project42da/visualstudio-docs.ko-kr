---
title: "__property | Microsoft Docs"
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
  - "__property_cpp"
  - "__property"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__property 키워드"
  - "관리되는 클래스"
  - "클래스를 관리 하는 속성 [c + +]"
ms.assetid: 235e3574-6882-4c52-8301-270277b9216d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# __property
> [!NOTE]
>  이 항목은 Managed Extensions for C\+\+ 버전 1에만 적용됩니다. 이 구문은 버전 1 코드를 유지하기 위해서만 사용해야 합니다. 참조 [property](/visual-cpp/windows/property-cpp-component-extensions) 동등한 기능을 사용 하 여 새 구문에서에 대 한 내용은 합니다.  
  
 관리되는 클래스의 스칼라 또는 인덱싱된 속성을 선언합니다.  
  
## 구문  
  
```  
  
__property  
function-declarator  
  
```  
  
## 설명  
 `__property` 키워드는 속성의 선언을 제공하고 클래스, 인터페이스 또는 값 형식에 표시될 수 있습니다. 속성은 getter 함수\(읽기 전용\), setter 함수\(쓰기 전용\) 또는 두 가지 모두\(읽기\/쓰기\)를 포함할 수 있습니다.  
  
> [!NOTE]
>  속성 이름은 자신이 포함된 관리되는 클래스의 이름과 일치할 수 없습니다. getter 함수의 반환 형식은 해당 setter 함수의 마지막 매개 변수 형식과 반드시 일치해야 합니다.  
  
## 예제  
 다음 예제에서 스칼라 속성\(`Size`\)은 `MyClass` 선언에 추가됩니다. 속성은 다음과 같이 `get_Size` 및 `set_Size` 함수를 사용하여 암시적으로 설정되고 검색됩니다.  
  
```  
// keyword__property.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__gc class MyClass {  
public:  
   MyClass() : m_size(0) {}  
   __property int get_Size() { return m_size; }  
   __property void set_Size(int value) { m_size = value; }  
   // compiler generates pseudo data member called Size  
protected:  
   int m_size;  
};  
  
int main() {  
   MyClass* class1 = new MyClass;  
   int curValue;  
  
   Console::WriteLine(class1->Size);  
  
   class1->Size = 4;   // calls the set_Size function with value==4  
   Console::WriteLine(class1->Size);  
  
   curValue = class1->Size;   // calls the get_Size function  
   Console::WriteLine(curValue);  
}  
```  
  
## 출력  
  
```  
0  
4  
4  
```