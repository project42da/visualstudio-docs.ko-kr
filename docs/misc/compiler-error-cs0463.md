---
title: "컴파일러 오류 CS0463 | Microsoft Docs"
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
  - "CS0463"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0463"
ms.assetid: 0cb4be4e-86ea-4ade-8817-b17d4cacd4d5
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0463
오류가 발생하여 10진수 상수 식을 계산하지 못했습니다. 'error'  
  
 이 오류는 컴파일 시간에 10진수 상수 식이 오버플로되는 경우에 발생합니다.  
  
 일반적으로 런타임에 오버플로 오류가 발생합니다. 이 경우 컴파일러에서 결과를 계산하고 오버플로가 발생할 것을 알 수 있는 방식으로 상수 식을 정의했습니다.  
  
## 예제  
 다음 코드에서는 CS0463 오류를 생성합니다.  
  
```  
// CS0463.cs using System; class MyClass { public static void Main() { const decimal myDec = 79000000000000000000000000000.0m + 79000000000000000000000000000.0m; // CS0463 Console.WriteLine(myDec.ToString()); } }  
```