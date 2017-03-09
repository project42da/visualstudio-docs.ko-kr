---
title: "컴파일러 경고(수준 2) CS0253 | Microsoft Docs"
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
  - "CS0253"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0253"
ms.assetid: e02d5dac-c2d9-45ca-9dd3-dda06c96f4d6
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS0253
의도하지 않은 참조 비교가 있을 수 있습니다. 값 비교를 가져오려면 오른쪽을 'type' 형식으로 캐스팅하세요.  
  
 컴파일러가 참조 비교를 수행합니다. 문자열의 값을 비교하려는 경우 식의 오른쪽을 `type`로 캐스팅합니다.  
  
 다음 샘플에서는 CS0253을 생성합니다.  
  
```  
// CS0253.cs // compile with: /W:2 using System; class MyClass { public static void Main() { string s = "11"; object o = s + s; bool c = s == o;   // CS0253 // try the following line instead // bool c = s == (string)o; } }  
```