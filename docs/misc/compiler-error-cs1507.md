---
title: "컴파일러 오류 CS1507 | Microsoft Docs"
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
  - "CS1507"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1507"
ms.assetid: e1be3aba-81dc-4f65-87a4-d3f90b82dc7d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1507
모듈을 빌드하는 동안 'file' 리소스 파일을 링크할 수 없습니다.  
  
 [\/linkresource](/dotnet/csharp/language-reference/compiler-options/linkresource-compiler-option)가 [\/target: module](../Topic/-target:module%20\(C%23%20Compiler%20Options\).md)과 동일한 컴파일에서 사용되었으며 이는 허용되지 않습니다. 예를 들어 다음 옵션은 CS1507을 생성하지 않습니다.  
  
```  
csc /linkresource:rf.resource /target:module in.cs  
```  
  
 그러나 리소스\([\/resource](/dotnet/csharp/language-reference/compiler-options/resource-compiler-option)\)를 포함하는 것은 허용됩니다.