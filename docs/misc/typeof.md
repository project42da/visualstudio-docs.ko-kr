---
title: "__typeof | Microsoft Docs"
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
  - "__typeof_cpp"
  - "__typeof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__typeof 키워드"
ms.assetid: d71b9603-35d0-4c62-b5b4-90ffc2305a55
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# __typeof
**참고** 이 항목은 Managed Extensions for C\+\+ 버전 1에만 적용됩니다. 이 구문은 버전 1 코드를 유지하기 위해서만 사용해야 합니다. 참조 [typeid](/visual-cpp/windows/typeid-cpp-component-extensions) 동등한 기능을 사용 하 여 새 구문에서에 대 한 내용은 합니다.  
  
 지정된 형식의 **System::Type**을 반환합니다.  
  
```  
  
__typeof(  
typename  
)  
  
```  
  
 다음은 각 문자에 대한 설명입니다.  
  
 *typename*  
 **System::Type** 이름을 원하는 관리되는 형식의 이름입니다. 관리되는 프로그램에서 일부 네이티브 형식은 공용 언어 런타임의 형식으로 별칭이 지정됩니다. 예를 들어 `int`는 **System::Int32**의 별칭입니다.  
  
## 설명  
 **\_\_typeof** 연산자를 사용하면 지정한 형식의 **System::Type** 형식을 가져올 수 있습니다.**\_\_typeof**를 사용하여 사용자 지정 특성 블록에서 **System::Type**의 값을 반환할 수도 있습니다. 사용자 지정 특성을 만드는 방법에 대한 자세한 내용은 [특성](/visual-cpp/windows/attribute)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 사용자 지정 특성\(`AtClass`\)이 \_\_gc 클래스\(`B`\)에 적용됩니다. 그런 다음 사용자 지정 특성의 값이 다음과 같이 **\_\_typeof**를 사용하여 검색됩니다.  
  
```  
// keyword__typeof.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
public __gc class MyClass {};  
  
[attribute(All)]  
__gc class AtClass {  
public:  
   AtClass(Type*) {  
      Console::WriteLine("in Type * constructor");  
   }  
  
   AtClass(String*) {}  
   AtClass(int) {}  
};  
  
[AtClass(__typeof(MyClass))]   // Apply AtClass attribute to class B  
__gc class B {};  
  
int main() {  
   Type * mytype = __typeof(B);  
   Object * myobject __gc[] = mytype -> GetCustomAttributes(true);  
   Console::WriteLine(myobject[0]);  
}  
```  
  
## 출력  
  
```  
in Type * constructor  
AtClass  
```