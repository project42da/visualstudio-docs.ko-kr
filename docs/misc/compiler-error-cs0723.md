---
title: "컴파일러 오류 CS0723 | Microsoft Docs"
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
  - "CS0723"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0723"
ms.assetid: b9f6aebc-e959-407d-8d5c-6a6dcabcfe0f
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0723
'type' 정적 형식의 변수를 선언할 수 없습니다.  
  
 정적 형식의 인스턴스를 만들 수 없습니다.  
  
 다음 샘플에서는 CS0723을 생성합니다.  
  
```  
// CS0723.cs public static class SC { } public class CMain { public static void Main() { SC sc = null;  // CS0723 } }  
```