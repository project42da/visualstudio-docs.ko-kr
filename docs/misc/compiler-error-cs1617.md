---
title: "컴파일러 오류 CS1617 | Microsoft Docs"
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
  - "CS1617"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1617"
ms.assetid: fd3371ed-39eb-4d3d-b8f5-d96ac0c79398
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1617
\/langversion의 'option' 옵션이 잘못되었습니다. ISO\-1, ISO\-2 또는 Default여야 합니다.  
  
 이 오류는 [\/langversion](/dotnet/csharp/language-reference/compiler-options/langversion-compiler-option) 명령줄 스위치 또는 프로젝트 설정을 사용하지만 유효한 언어 옵션을 지정하지 않는 경우 발생합니다. 이 오류를 해결하려면 명령줄 구문 또는 프로젝트 설정을 확인하고 나열된 옵션 중 하나로 변경합니다.  
  
 예를 들어 `csc /langversion:ISO`를 사용하여 컴파일하면 CS1617 오류가 생성됩니다.