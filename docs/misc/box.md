---
title: "__box | Microsoft Docs"
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
  - "__box"
  - "__box_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__box 키워드"
  - "boxing"
  - "unboxing"
  - "boxing, __box 키워드"
ms.assetid: 935b4a4d-fc45-484c-87c6-d95cfc67cc9d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# __box
> [!NOTE]
>  이 항목은 Managed Extensions for C\+\+ 버전 1에만 적용됩니다. 이 구문은 버전 1 코드를 유지하기 위해서만 사용해야 합니다. 참조 [Boxing](/visual-cpp/windows/boxing-cpp-component-extensions) 동등한 기능을 사용 하 여 새 구문에서에 대 한 내용은 합니다.  
  
 \_\_value 클래스 개체의 관리되는 복사본을 만듭니다.  
  
## 구문  
  
```  
  
__box(  
value-class identifier  
)  
  
```  
  
## 설명  
 `__box` 키워드는 기존의 \_\_value 클래스 개체로 관리되는 개체\(**System::ValueType**에서 파생\)를 만드는 데 사용됩니다.`__box` 키워드가 \_\_value 클래스에 적용되면  
  
-   관리되는 개체가 공용 언어 런타임 힙에 할당됩니다.  
  
-   \_\_Value 클래스 개체의 현재 값이 관리되는 개체에 비트 단위로 복사됩니다.  
  
-   관리되는 새 개체의 주소가 반환됩니다.  
  
 이 프로세스를 boxing이라고 합니다. boxing을 사용하면 관리되는 개체가 **System::Object**에서 간접적으로 상속되므로\(**System::ValueType**이 **System::Object**에서 상속되므로\) 관리되는 개체에 적용되는 제네릭 루틴에 \_\_value 클래스 개체를 사용할 수 있습니다.  
  
> [!NOTE]
>  새로 만든 boxed 개체는 \_\_value 클래스 개체의 복사본입니다. 따라서 boxed 개체의 값을 수정해도 \_\_value 클래스 개체의 내용에 영향을 주지 않습니다.  
  
## 예제  
 다음은 boxing 및 unboxing을 수행하는 예제입니다.  
  
```  
// keyword__box.cpp  
// compile with: /clr:oldSyntax  
#using < mscorlib.dll >  
using namespace System;  
  
int main() {  
  Int32 i = 1;  
  System::Object* obj = __box(i);  
  Int32 j = *dynamic_cast<__box Int32*>(obj);  
}  
```  
  
 다음 예제에서 관리되지 않는 값 형식\(`V`\)이 boxed이며 관리되는 매개 변수로 `Positive` 함수에 전달됩니다.  
  
```  
// keyword__box2.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__value struct V {  
   int i;  
};  
void Positive(Object*) {}   // expects a managed class  
  
int main() {  
   V v={10};   // allocate and initialize  
   Console::WriteLine(v.i);  
  
   // copy to the common language runtime heap  
   __box V* pBoxedV = __box(v);  
   Positive(pBoxedV);   // treat as a managed class  
  
   pBoxedV->i = 20;   // update the boxed version  
   Console::WriteLine(pBoxedV->i);  
}  
```  
  
 **10 20**