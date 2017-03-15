---
title: "컴파일러 오류 CS0721 | Microsoft Docs"
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
  - "CS0721"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0721"
ms.assetid: 7ab8591d-df8a-440c-80d6-61b438a935fd
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0721
'type': 정적 형식은 매개 변수로 사용할 수 없습니다.  
  
 정적 형식은 매개 변수로 의미가 없습니다. 정적 형식 인스턴스를 만들 수 없으므로 인스턴스를 매개 변수로 전달할 수 없습니다.  
  
 다음 샘플에서는 CS0721을 생성합니다.  
  
```  
// CS0721.cs public static class SC { } public class CMain { public void F(SC sc)  // CS0721 { } public static void Main() { } }  
```