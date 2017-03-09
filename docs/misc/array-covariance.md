---
title: "배열 공 분산 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "배열 [c + +], 공변성 (covariance)"
ms.assetid: 889fdde3-85fe-44d5-bf2d-d3d4aa14e746
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "mithom"
manager: "douge"
---
# 배열 공 분산
직접 또는 간접 기본 클래스 B와 D 참조 클래스를 매개 변수로 받아 D 형식의 배열에 지정할 수는 배열 변수 형식.  
  
```  
// clr_array_covariance.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   // String derives from Object  
   array<Object^>^ oa = gcnew array<String^>(20);  
}  
```  
  
## 설명  
 배열 요소에 할당 하는 할당 호환이 되어야 합니다. 동적 형식의 배열입니다. 호환 되지 않는 형식으로 배열 요소에 대 한 할당 System::ArrayTypeMismatchException를 throw 하면 됩니다.  
  
 배열 공 분산 값 클래스 형식의 배열에 적용 되지 않습니다. 예를 들어 i n t 32의 배열을 변환할 수 없습니다 개체 ^ boxing 통한 배열입니다.  
  
## 예제  
  
```  
// clr_array_covariance2.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct Base { int i; };  
ref struct Derived  : Base {};  
ref struct Derived2 : Base {};  
ref struct Derived3 : Derived {};  
ref struct Other { short s; };  
  
int main() {  
   // Derived* d[] = new Derived*[100];  
   array<Derived^> ^ d = gcnew array<Derived^>(100);  
  
   // ok by array covariance  
   array<Base ^> ^  b = d;  
  
   // invalid  
   // b[0] = new Other;  
  
   // error (runtime exception)  
   // b[1] = gcnew Derived2;  
  
   // error (runtime exception),  
   // must be "at least" a Derived.  
   // b[0] = gcnew Base;  
  
   b[1] = gcnew Derived;  
   b[0] = gcnew Derived3;  
}  
```  
  
## 참고 항목  
 [Arrays](/visual-cpp/windows/arrays-cpp-component-extensions)