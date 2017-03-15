---
title: "컴파일러 오류 CS1641 | Microsoft Docs"
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
  - "CS1641"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1641"
ms.assetid: ba6eab47-c28b-4531-b6a0-6d538b236d19
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1641
고정 크기 버퍼 필드에는 필드 이름 뒤에 배열 크기 지정자를 사용해야 합니다.  
  
 정규 배열과 달리 고정 크기 버퍼에서는 선언 지점에서 상수 크기를 지정해야 합니다. 이 오류를 해결하려면 양의 정수 리터럴 또는 상수 양의 정수를 추가하고 식별자 뒤에 대괄호를 넣습니다.  
  
 다음 샘플에서는 CS1641을 생성합니다.  
  
```  
// CS1641.cs // compile with: /unsafe /target:library unsafe struct S { fixed int [] a;  // CS1641 // OK fixed int b [10]; const int c = 10; fixed int d [c]; }  
```