---
title: "컴파일러 오류 CS0722 | Microsoft Docs"
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
  - "CS0722"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0722"
ms.assetid: 85f6854c-581d-482b-b4b0-1e665d9e3e6f
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0722
'type': 정적 형식은 반환 형식으로 사용할 수 없습니다.  
  
 정적 형식의 인스턴스를 만들 수 없으므로 반환 형식으로서의 정적 형식은 의미가 없습니다.  
  
 다음 샘플에서는 CS0722를 생성합니다.  
  
```  
// CS0722.cs public static class SC { } public class CMain { public SC F()  // CS0722 { return null; } public static void Main() { } }  
```