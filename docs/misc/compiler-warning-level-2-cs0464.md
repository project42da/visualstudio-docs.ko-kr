---
title: "컴파일러 경고(수준 2) CS0464 | Microsoft Docs"
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
  - "CS0464"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0464"
ms.assetid: 3dff97d4-e1f6-4a71-91e2-68cffc38d49a
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS0464
'type' 형식의 null과 비교하면 결과는 항상 'false'입니다.  
  
 이 경고는 null 허용 변수와 null을 비교하고 비교가 `==` 또는 `!=`가 아닌 경우에 생성됩니다. 이 오류를 해결하려면 `null`의 값을 확인하려는 것이 맞는지 확인합니다.`i == null` 등의 비교는 true 또는 false일 수 있습니다.`i > null` 등의 비교는 항상 false입니다.  
  
## 예제  
 다음 샘플에서는 CS0464를 생성합니다.  
  
```  
// CS0464.cs class MyClass { public static void Main() { int? i = 0; if (i < null) ;   // CS0464 i++; } }  
```