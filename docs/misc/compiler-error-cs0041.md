---
title: "컴파일러 오류 CS0041 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0041"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0041"
ms.assetid: 80dbfe00-8cdb-4275-9574-8a215c7139d6
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0041
'type'의 정규화된 이름이 너무 길어서 디버그 정보에 사용할 수 없습니다. '\/debug' 옵션 없이 컴파일합니다.  
  
 이 오류는 [\/debug](/dotnet/csharp/language-reference/compiler-options/debug-compiler-option) 컴파일러 옵션을 사용하는 경우에 발생할 수 있습니다. 이 오류가 발생하면 bin 디렉터리에서 PDB 파일을 삭제하고 다시 컴파일합니다. 그래도 이 오류가 발생하면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 복구하거나 다시 설치해야 할 수도 있습니다.