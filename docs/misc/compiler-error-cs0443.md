---
title: "컴파일러 오류 CS0443 | Microsoft Docs"
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
  - "CS0443"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0443"
ms.assetid: 8f7f71ff-5eb5-4a1d-80ff-77303472eb8e
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0443
구문 오류입니다. 값이 필요합니다.  
  
 이 오류는 배열 인덱스에 대한 값을 지정하지 않고 배열을 참조하는 경우 발생합니다.  
  
## 예제  
 다음 코드에서는 CS0443을 생성합니다.  
  
```  
// CS0443.cs using System; class MyClass { public static void Main() { int[,] x = new int[1,5]; if (x[] == 5) {} // CS0443 // if (x[0, 0] == 5) {} } }  
```