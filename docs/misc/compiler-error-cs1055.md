---
title: "컴파일러 오류 CS1055 | Microsoft Docs"
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
  - "CS1055"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1055"
ms.assetid: a93cb577-95fc-490a-97c4-2f366409f2c3
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1055
add 또는 remove 접근자가 필요합니다.  
  
 [event](/dotnet/csharp/language-reference/keywords/event)가 필드로 선언되지 않은 경우 **add** 및 **remove** 접근자 함수를 모두 정의해야 합니다.  
  
 다음 샘플에서는 CS1055를 생성합니다.  
  
```  
// CS1055.cs delegate void del(); class Test { public event del MyEvent { int i;   // CS1055 // uncomment accessors and delete previous line to resolve // add // { //    MyEvent += value; // } // remove // { //    MyEvent -= value; // } } public static void Main() { } }  
```