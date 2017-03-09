---
title: "컴파일러 오류 CS1017 | Microsoft Docs"
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
  - "CS1017"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1017"
ms.assetid: e0902e8a-b042-4711-a8a6-83456a3f88cb
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1017
Catch 절은 try 문의 일반 catch 절 뒤에 올 수 없습니다.  
  
 매개 변수를 사용하지 않는 `catch` 블록은 일련의 `catch` 블록에서 마지막이어야 합니다. 예외에 대한 자세한 내용은 [예외 처리문](/dotnet/csharp/language-reference/keywords/exception-handling-statements)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS1017을 생성합니다.  
  
```  
// CS1017.cs using System; namespace x { public class b : Exception { } public class a { public static void Main() { try { } catch   // CS1017, must be last catch { } catch(b) { throw; } } } }  
```