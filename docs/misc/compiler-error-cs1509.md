---
title: "컴파일러 오류 CS1509 | Microsoft Docs"
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
  - "CS1509"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1509"
ms.assetid: 51a475c3-f085-49cb-89b0-c6582b68653f
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1509
참조된 'file' 파일은 어셈블리가 아니므로 대신 '\/addmodule' 옵션을 사용하세요.  
  
 [\/target: module](../Topic/-target:module%20\(C%23%20Compiler%20Options\).md)\(어셈블리 매니페스트 없음\)을 사용한 컴파일에서 생성된 출력 파일\(출력 파일 1\)이 [\/reference](/dotnet/csharp/language-reference/compiler-options/reference-compiler-option)로 지정되었습니다. 그러므로 어셈블리를 현재 프로그램의 어셈블리에 추가하는 대신 출력 파일 1의 메타데이터 정보가 현재 프로그램의 어셈블리에 추가됩니다.