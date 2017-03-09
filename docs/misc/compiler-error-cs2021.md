---
title: "컴파일러 오류 CS2021 | Microsoft Docs"
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
  - "CS2021"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2021"
ms.assetid: 8379d77e-6586-4e43-9aab-7cdf3ffecf51
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS2021
‘file’ 파일 이름이 너무 길거나 잘못되었습니다.  
  
 C\# 컴파일러에 전달되는 모든 파일 이름은 `_MAX_PATH`\(Windows 헤더 파일에 정의됨\)보다 길지 않아야 합니다. 이 오류는 다음과 같은 경우에 발생합니다.  
  
-   파일 이름\(경로 포함\)이 `_MAX_PATH`보다 긴 경우  
  
-   파일 이름에 잘못된 문자가 들어 있습니다.  
  
-   와일드카드가 허용되지 않는 파일 이름\(예: 리소스 파일 이름\)에 와일드카드가 포함된 경우