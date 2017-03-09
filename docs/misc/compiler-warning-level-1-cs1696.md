---
title: "컴파일러 경고(수준 1) CS1696 | Microsoft Docs"
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
  - "CS1696"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1696"
ms.assetid: 69a45988-1aba-4a01-a84e-7ca59f8dde28
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1696
한 줄로 된 주석이나 줄 끝\(EOL\)이 필요합니다.  
  
 컴파일러에서는 전처리기 지시문 뒤에 줄의 끝 종결자나 한 줄 주석이 와야 합니다. 컴파일러가 유효한 전처리기 지시문 처리를 완료했으며 이 구문 제약 조건을 위반하는 항목을 발견했습니다.  
  
## 예제  
 다음 샘플에서는 CS1696을 생성합니다.  
  
```  
// CS1696.cs class Test { public static void Main() { #pragma warning disable 1030;219   // CS1696 #pragma warning disable 1030   // OK } }  
```