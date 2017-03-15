---
title: "CLS 규격 경고 CLS01109 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CLS01109"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS01109"
ms.assetid: 5bfd6fcf-95bb-4f13-8090-5303eebb3c06
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS01109
서명에 나타나는 모든 형식은 CLS 규격을 준수해야 합니다.  
  
 멤버 함수 서명에 나타나는 모든 형식은 CLS 규격을 준수해야 합니다.  
  
 다음 샘플에서는 CLS01109를 생성합니다.  
  
```  
// CLS01109.cpp // compile with: /clr /c [assembly:System::CLSCompliant(true)]; [System::CLSCompliant(false)] public ref class NotCompliantType {}; public ref class MyClass { public: property array< NotCompliantType^ >^ SomeProperty {   // CLS01109 array< NotCompliantType^ >^ get() { return nullptr; } void set(array< NotCompliantType^ >^ v ) { } } };  
```  
  
 해결 방법:  
  
```  
// CLS01109b.cpp // compile with: /clr /LD [assembly:System::CLSCompliant(true)]; public ref class CompliantType {}; public ref class MyClass { public: property array< CompliantType^ >^ SomeProperty { array< CompliantType^ >^ get() { return nullptr; } void set(array< CompliantType^ >^ v ) { } } };  
```