---
title: "컴파일러 오류 CS0719 | Microsoft Docs"
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
  - "CS0719"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0719"
ms.assetid: 308a1a54-43b9-4970-8206-88e8f76d394e
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0719
'type': 배열 요소는 정적 형식일 수 없습니다.  
  
 배열 요소는 인스턴스이지만 정적 형식의 인스턴스를 만드는 것은 불가능하기 때문에 정적 형식의 배열은 적합하지 않습니다.  
  
 다음 샘플에서는 CS0719를 생성합니다.  
  
```  
// CS0719.cs public static class SC { public static void F() { } } public class CMain { public static void Main() { SC[] sca = new SC[10];  // CS0719 } }  
```