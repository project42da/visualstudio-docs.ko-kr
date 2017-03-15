---
title: "컴파일러 오류 CS0727 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0727"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0727"
ms.assetid: 54bfb87e-d759-4310-a8ab-02dccd06337c
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0727
잘못된 서식 지정자  
  
 이 오류는 디버거에서 발생합니다. 디버거 창 중 하나에 변수 이름을 입력하는 경우 뒤에 쉼표와 형식 지정자를 입력할 수 있습니다. 예를 들어 myInt, h; 또는 myString,nq입니다. 이 오류는 입력한 내용을 컴파일러에서 완전히 구문 분석할 수 없는 경우에 발생합니다. 이 오류를 해결하려면 변수 이름을 다시 입력하고 필요에 따라 쉼표와 [올바른 형식 지정자](../debugger/format-specifiers-in-csharp.md)를 입력합니다.