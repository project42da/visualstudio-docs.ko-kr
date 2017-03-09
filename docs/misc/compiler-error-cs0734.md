---
title: "컴파일러 오류 CS0734 | Microsoft Docs"
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
  - "CS0734"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0734"
ms.assetid: 9e1b0e49-bfc3-400c-9fd1-37e3c827e656
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0734
\/moduleassemblyname 옵션은 빌드하는 대상 형식이 'module'인 경우에만 지정할 수 있습니다.  
  
 컴파일러 옵션 **\/moduleassemblyname**은 .netmodule을 빌드할 때만 사용해야 합니다. 자세한 내용은 [\/moduleassemblyname \(Specify Friend Assembly for Module\)](/dotnet/csharp/language-reference/compiler-options/moduleassemblyname-compiler-option)를 참조하세요.  
  
 .netmodule 빌드에 대한 자세한 내용은 [\/target:module \(Create Module to Add to Assembly\)](../Topic/-target:module%20\(C%23%20Compiler%20Options\).md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0734를 생성합니다. 해결하려면 컴파일에 **\/target:module**을 추가합니다.  
  
```  
// CS0734.cs // compile with: /moduleassemblyname:A // CS0734 expected public class Test {}  
```