---
title: "컴파일러 경고(수준 1) CS3013 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS3013"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3013"
ms.assetid: 00b3bbe1-f2a0-465c-be0e-1af700c5753d
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS3013
추가된 모듈은 어셈블리와 일치하도록 CLSCompliant 특성으로 표시되어야 합니다.  
  
 [\/target:module](../Topic/-target:module%20\(C%23%20Compiler%20Options\).md) 컴파일러 옵션으로 컴파일된 모듈이 [\/addmodule](/dotnet/csharp/language-reference/compiler-options/addmodule-compiler-option)을 사용한 컴파일에 추가되었습니다. 그러나 모듈의 CLS\(공용 언어 사양\) 규격이 현재 컴파일의 CLS 상태와 맞지 않습니다.  
  
 CLS 규격은 모듈 특성으로 표시됩니다. 예를 들어 `[module:CLSCompliant(true)]`는 모듈이 CLS 규격임을 나타내고, `[module:CLSCompliant(false)]`는 모듈이 CLS 규격이 아님을 나타냅니다. 기본값은 `[module:CLSCompliant(false)]`입니다. CLS에 대한 자세한 내용은 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)를 참조하세요.