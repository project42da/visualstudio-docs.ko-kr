---
title: "컴파일러 오류 CS0418 | Microsoft Docs"
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
  - "CS0418"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0418"
ms.assetid: b78fafde-428b-4fa2-a933-c4614760bb71
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0418
'class name': 추상 클래스는 sealed 또는 static이 될 수 없습니다.  
  
 추상 클래스는 파생되지 않은 경우 개체를 만드는 데 사용할 수 없으므로 sealed되는 것이 의미가 없습니다. 추상 클래스는 static이 되어도 의미가 없습니다. 추상 클래스는 해당 추상 클래스를 기본으로 사용할 개체 계층 구조를 지원하도록 디자인되어 있습니다.  
  
## 예제  
 다음 샘플에서는 CS0418을 생성합니다.  
  
```  
// CS0418.cs public abstract sealed class C  // CS0418 { } sealed static class S  // CS0418 { } public class MyClass { public static void Main() { } }  
```