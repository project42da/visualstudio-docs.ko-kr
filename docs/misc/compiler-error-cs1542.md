---
title: "컴파일러 오류 CS1542 | Microsoft Docs"
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
  - "CS1542"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1542"
ms.assetid: d7f60aa2-6645-472c-ac12-fa57a09fbd87
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1542
'dll'은 이미 어셈블리이므로 이 어셈블리에 추가할 수 없습니다. 대신 '\/R' 옵션을 사용합니다.  
  
 [\/addmodule](/dotnet/csharp/language-reference/compiler-options/addmodule-compiler-option) 컴파일러 옵션으로 참조된 파일이 [\/target:module](../Topic/-target:module%20\(C%23%20Compiler%20Options\).md)로 작성되지 않았습니다. [\/reference](/dotnet/csharp/language-reference/compiler-options/reference-compiler-option)를 사용하여 이 컴파일의 파일을 참조하세요.