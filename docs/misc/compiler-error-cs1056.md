---
title: "컴파일러 오류 CS1056 | Microsoft Docs"
ms.custom: ""
ms.date: "10/02/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1056"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1056"
ms.assetid: bf66d164-ab5b-4181-b93e-a1d29620b4d2
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1056
예기치 않은 'character' 문자입니다.  
  
 C\# 컴파일러가 예기치 않은 문자를 만났기 때문에 현재 처리 중인 토큰을 식별할 수 없습니다. 예를 들어 컴파일러가 식별자를 처리하는 동안 유로 문자를 만나는 경우 식별자를 분류할 수 없습니다. 유로 문자는 문자열 내에서만 유효하고 컴파일러는 문자열을 처리하지 않기 때문입니다.