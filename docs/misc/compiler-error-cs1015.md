---
title: "컴파일러 오류 CS1015 | Microsoft Docs"
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
  - "CS1015"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1015"
ms.assetid: 53179feb-e8be-41e0-bb0b-f7879e9fa613
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1015
개체, 문자열 또는 클래스 형식이 필요합니다.  
  
 미리 정의된 데이터 형식을 [catch](/dotnet/csharp/language-reference/keywords/try-catch) 블록으로 전달하려고 했습니다.<xref:System.Exception?displayProperty=fullName>에서 파생된 데이터 형식만 `catch` 블록에 전달할 수 있습니다. 예외에 대한 자세한 내용은 [예외 처리문](/dotnet/csharp/language-reference/keywords/exception-handling-statements)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS1015을 생성합니다.  
  
```  
// CS1015.cs class Sample { static void Main() { try { } catch(int)   // CS1015, int is not derived from System.Exception { } } }  
```