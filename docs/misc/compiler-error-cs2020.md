---
title: "컴파일러 오류 CS2020 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS2020"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2020"
ms.assetid: b2db7a05-5965-4a9b-86c3-0c4792b29a6c
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS2020
첫째 입력 파일 집합만 'module' 이외의 대상을 빌드할 수 있습니다.  
  
 다중 출력 컴파일에서 [\/target:exe](../Topic/-target:exe%20\(C%23%20Compiler%20Options\).md), [\/target:winexe](../Topic/-target:winexe%20\(C%23%20Compiler%20Options\).md) 또는 [\/target:library](../Topic/-target:library%20\(C%23%20Compiler%20Options\).md)를 사용하여 첫 번째 출력 파일을 빌드해야 합니다.[\/target:module](../Topic/-target:module%20\(C%23%20Compiler%20Options\).md)을 사용하여 모든 후속 출력 파일을 빌드해야 합니다.