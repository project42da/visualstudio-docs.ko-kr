---
title: "컴파일러 오류 CS0404 | Microsoft Docs"
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
  - "CS0404"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0404"
ms.assetid: 60bef49e-e0b7-4e9e-aab3-7afc20a19cb8
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0404
예기치 않은 '\<'입니다. 특성은 제네릭이 될 수 없습니다.  
  
 제네릭 형식 매개 변수가 특성에서 허용되지 않습니다. 형식 매개 변수 및 꺾쇠 괄호를 제거합니다.  
  
 다음 샘플에서는 CS0404를 생성합니다.  
  
```  
// CS0404.cs [MyAttrib<int>]  // CS0404 class C { public static void Main() { } }  
```