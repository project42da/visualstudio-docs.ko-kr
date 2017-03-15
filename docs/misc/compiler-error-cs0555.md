---
title: "컴파일러 오류 CS0555 | Microsoft Docs"
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
  - "CS0555"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0555"
ms.assetid: e4b2f890-98b4-4578-b1de-ebaafc8b3da2
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0555
사용자 정의 연산자는 바깥쪽 형식의 개체를 가져와서 바깥쪽 형식의 개체로 변환할 수 없습니다.  
  
 바깥쪽의 클래스 값으로의 사용자 정의 변환은 허용되지 않습니다. 이러한 연산자는 필요하지 않습니다.  
  
 다음 샘플에서는 CS0555를 생성합니다.  
  
```  
// CS0555.cs public class MyClass { // delete the following operator to resolve this CS0555 public static implicit operator MyClass(MyClass aa)   // CS0555 { return new MyClass(); } public static void Main() { } }  
```