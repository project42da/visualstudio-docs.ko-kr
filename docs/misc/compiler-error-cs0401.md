---
title: "컴파일러 오류 CS0401 | Microsoft Docs"
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
  - "CS0401"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0401"
ms.assetid: 94eac5a8-7344-44d2-9d0c-a9954993603d
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0401
new\(\) 제약 조건은 마지막에 지정해야 합니다.  
  
 여러 제약 조건을 사용하는 경우 new\(\) 제약 조건 앞에 다른 모든 제약 조건을 나열합니다.  
  
## 예제  
 다음 샘플에서는 CS0401을 생성합니다.  
  
```  
// CS0401.cs // compile with: /target:library using System; class C<T> where T : new(), IDisposable {}  // CS0401 class D<T> where T : IDisposable { static void F<U>() where U : new(), IDisposable{}   // CS0401 }  
```