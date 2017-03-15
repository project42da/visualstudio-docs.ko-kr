---
title: "컴파일러 오류 CS1524 | Microsoft Docs"
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
  - "CS1524"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1524"
ms.assetid: a7b80bbc-a2de-4718-b0f0-4c9526726525
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1524
catch 또는 finally가 필요합니다.  
  
 `try` 블록은 뒤에 `catch` 또는 `finally` 블록이 와야 합니다.  
  
 예외에 대한 자세한 내용은 [예외 처리문](/dotnet/csharp/language-reference/keywords/exception-handling-statements)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS1524를 생성합니다.  
  
```  
// CS1524.cs class x { public static void Main() { try { // Code here } catch { } try { // Code here } finally { } try { // Code here } }     // CS1524, missing catch or finally }  
```