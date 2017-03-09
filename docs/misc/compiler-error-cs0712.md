---
title: "컴파일러 오류 CS0712 | Microsoft Docs"
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
  - "CS0712"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0712"
ms.assetid: cde64c0c-3953-4563-8c24-8b646230bbb8
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0712
'static class' 정적 클래스의 인스턴스를 만들 수 없습니다.  
  
 정적 클래스의 인스턴스를 만들 수 없습니다. 정적 클래스는 정적 필드 및 메서드를 포함하도록 설계되었지만 인스턴스화할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 CS0712를 생성합니다.  
  
```  
// CS0712.cs public static class SC { } public class CMain { public static void Main() { SC sc = new SC();  // CS0712 } }  
```