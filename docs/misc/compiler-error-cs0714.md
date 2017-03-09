---
title: "컴파일러 오류 CS0714 | Microsoft Docs"
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
  - "CS0714"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0714"
ms.assetid: fbb5dc55-645c-4980-bf4b-3c2f84a3c6cd
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0714
'static type': 정적 클래스는 인터페이스를 구현할 수 없습니다.  
  
 인터페이스는 개체에 비정적 메서드를 정의할 수 있으므로 정적 클래스로 구현되지 않을 수 있습니다. 이 오류를 해결하려면 클래스가 인터페이스를 구현하려고 하지 않아야 합니다.  
  
## 예제  
 다음 샘플에서는 CS0714를 생성합니다.  
  
```  
// CS0714.cs interface I { } public static class C : I  // CS0714 { public static void Main() { } }  
```