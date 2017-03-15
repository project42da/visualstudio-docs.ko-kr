---
title: "컴파일러 오류 CS0022 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0022"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0022"
ms.assetid: 531c3ed2-0d75-4046-8d57-89f79381af8e
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0022
\[\] 내부의 인덱스 수가 잘못되었습니다. 'number'개가 필요합니다.  
  
 배열 액세스 작업에서 대괄호 안에 잘못된 차원 수를 지정했습니다. 자세한 내용은 [배열](/dotnet/csharp/programming-guide/arrays/index)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0022를 생성합니다.  
  
```  
// CS0022.cs public class MyClass { public static void Main() { int[] a = new int[10]; a[0] = 0;     // single-dimension array a[0,1] = 9;   // CS0022, the array does not have two dimensions } }  
```