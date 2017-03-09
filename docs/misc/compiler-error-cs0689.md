---
title: "컴파일러 오류 CS0689 | Microsoft Docs"
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
  - "CS0689"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0689"
ms.assetid: 5c555c2e-8e71-4097-8dbf-52dbafe7bf57
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0689
형식 매개 변수이므로 'identifier'에서 파생될 수 없습니다.  
  
 제네릭 클래스의 인터페이스 또는 기본 클래스는 형식 매개 변수에서 지정될 수 없습니다. 특정 클래스나 인터페이스 또는 특정 제네릭 클래스에서 파생되거나 알 수 없는 형식을 멤버로 포함합니다.  
  
 다음 샘플에서는 CS0689를 생성합니다.  
  
```  
// CS0689.cs class A<T> : T   // CS0689 { }  
```