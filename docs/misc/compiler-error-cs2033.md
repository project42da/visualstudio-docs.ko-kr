---
title: "컴파일러 오류 CS2033 | Microsoft Docs"
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
  - "CS2033"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2033"
ms.assetid: edb5784a-5195-4f72-b73d-d1ec9ed3766e
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS2033
같은 약식 파일 이름을 사용하는 긴 파일 이름이 이미 있으면 약식 파일 이름 'filename'을 만들 수 없습니다.  
  
 이름이 8자보다 긴 C\# 파일을 컴파일합니다. 그런 다음 이름의 처음 6자에 "~1"을 더하는 등 이전 파일 이름의 약식 버전으로 다른 파일을 컴파일합니다. 두 번째 컴파일에서 이 오류가 발생합니다.  
  
 이 오류를 해결하려면 약식 파일 이름을 긴 파일 이름과 충돌하지 않는 이름으로 바꿉니다.