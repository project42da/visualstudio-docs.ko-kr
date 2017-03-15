---
title: "컴파일러 오류 CS0409 | Microsoft Docs"
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
  - "CS0409"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0409"
ms.assetid: 23d86c13-7978-41b7-a087-ffcea52476fa
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0409
제약 조건 절이 'type parameter' 형식 매개 변수에 대해 이미 지정되었습니다. 형식 매개 변수의 모든 제약 조건은 단일 where 절에서 지정되어야 합니다.  
  
 단일 형식 매개 변수에 대해 여러 제약 조건 절\(where 절\)을 찾았습니다. 각 절에 고유 형식 매개 변수가 있도록 불필요한 where 절을 제거하거나 where 절을 수정합니다.  
  
```  
// CS0409.cs interface I { } class C<T1, T2> where T1 : I where T1 : I  // CS0409 – T1 used twice { }  
```