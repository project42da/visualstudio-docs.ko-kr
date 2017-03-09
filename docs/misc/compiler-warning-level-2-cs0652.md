---
title: "컴파일러 경고(수준 2) CS0652 | Microsoft Docs"
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
  - "CS0652"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0652"
ms.assetid: 1ec1cee6-858a-4104-aa15-2668723c6331
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS0652
정수 상수와 비교하는 것은 의미가 없습니다. 상수가 'type' 형식의 범위를 벗어났습니다.  
  
 컴파일러에서 상수가 변수 범위 밖에 있는 변수와 상수 간의 비교를 검색했습니다.  
  
 다음 샘플에서는 CS0652를 생성합니다.  
  
```  
// CS0652.cs // compile with: /W:2 public class Class1 { private static byte i = 0; public static void Main() { short j = 256; if (i == 256)   // CS0652, 256 is out of range for byte i = 0; } }  
```