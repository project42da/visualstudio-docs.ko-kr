---
title: "컴파일러 오류 CS0713 | Microsoft Docs"
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
  - "CS0713"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0713"
ms.assetid: 27a46765-d982-43ba-909f-9278e26b80d2
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0713
'static type' 정적 클래스는 'type' 형식에서 파생될 수 없습니다. 정적 클래스는 개체에서 파생되어야 합니다.  
  
 허용되는 경우 정적 클래스가 기본 클래스에서 메서드와 비정적 멤버를 상속하게 되어 정적이 아니게 됩니다. 따라서 허용되지 않습니다.  
  
 다음 샘플에서는 CS0713을 생성합니다.  
  
```  
// CS0713.cs public class Base { } public static class Derived : Base  // CS0713 { } public class CMain { public static void Main() { } }  
```