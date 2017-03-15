---
title: "컴파일러 오류 CS2016 | Microsoft Docs"
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
  - "CS2016"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2016"
ms.assetid: 69f77502-f726-4856-ac87-e556eeb67349
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS2016
'codepage' 코드 페이지가 잘못되었거나 설치되지 않았습니다.  
  
 [\/codepage](/dotnet/csharp/language-reference/compiler-options/codepage-compiler-option) 컴파일러 옵션에 잘못된 값이 전달되었습니다.  
  
 다음 샘플에서는 CS2016을 생성합니다.  
  
```  
// CS2016.cs // compile with: /codepage:x // CS2016 expected class MyClass { public static void Main() { } }  
```