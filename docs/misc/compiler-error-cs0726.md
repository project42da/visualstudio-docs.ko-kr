---
title: "컴파일러 오류 CS0726 | Microsoft Docs"
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
  - "CS0726"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0726"
ms.assetid: 9ea5f004-cf25-4e6e-b9e5-6b53e4a7e1ab
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0726
'format specifier'는 올바른 형식 지정자가 아닙니다.  
  
 이 오류는 디버거에서 발생합니다. 디버거 창 중 하나에 변수 이름을 입력하는 경우 뒤에 쉼표와 형식 지정자를 입력할 수 있습니다. 예를 들어 `myInt, h` 또는 `myString,nq`와 같이 입력합니다. 이 오류는 컴파일러에서 [C\#의 형식 지정자](../debugger/format-specifiers-in-csharp.md)를 인식할 수 없는 경우에 발생합니다.