---
title: "컴파일러 오류 CS1562 | Microsoft Docs"
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
  - "CS1562"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1562"
ms.assetid: fbadbcc6-9cf2-4af6-b372-fd4e4da4402e
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1562
소스 없는 출력의 경우 \/out 옵션을 지정해야 합니다.  
  
 컴파일하여 출력 파일을 만들 수 있으나 출력 파일의 이름을 암시하는 입력으로 사용하는 소스 코드 파일이 없습니다. 예를 들어 메타데이터 또는 리소스 전용 파일을 컴파일하려고 할 수 있습니다.  
  
 출력 파일 이름을 지정하려면 [\/out](/dotnet/csharp/language-reference/compiler-options/out-compiler-option) 컴파일러 옵션을 사용합니다.