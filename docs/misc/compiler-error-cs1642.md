---
title: "컴파일러 오류 CS1642 | Microsoft Docs"
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
  - "CS1642"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1642"
ms.assetid: 2efeedf1-1839-485d-8b8c-9045df1951f0
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1642
고정 크기 버퍼 필드는 구조체의 멤버로만 사용할 수 있습니다.  
  
 이 오류는 `struct` 대신 `class`의 고정 크기 버퍼 필드를 사용하는 경우에 발생합니다. 이 오류를 해결하려면 `class`를 `struct`로 변경하거나 필드를 일반 배열로 선언합니다.  
  
## 예제  
 다음 샘플에서는 CS1642를 생성합니다.  
  
```  
// CS1642.cs // compile with: /unsafe /target:library unsafe class C { fixed int a[10];   // CS1642 } unsafe struct D { fixed int a[10]; } unsafe class E { public int[] a = null; }  
```