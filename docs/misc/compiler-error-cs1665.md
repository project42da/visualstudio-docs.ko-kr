---
title: "컴파일러 오류 CS1665 | Microsoft Docs"
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
  - "CS1665"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1665"
ms.assetid: 93d4a4af-23c3-4730-a778-77852e41db4d
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1665
고정 크기 버퍼의 길이는 0보다 커야 합니다.  
  
 이 오류는 고정된 크기 버퍼가 0 또는 음수로 선언된 경우 발생합니다. 고정된 크기 버퍼 길이는 양의 정수여야 합니다.  
  
## 예제  
 다음 샘플에서는 CS1665를 생성합니다.  
  
```  
// CS1665.cs // compile with: /unsafe /target:library struct S { public unsafe fixed int A[0];   // CS1665 }  
```