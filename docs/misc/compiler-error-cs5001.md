---
title: "컴파일러 오류 CS5001 | Microsoft Docs"
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
  - "CS5001"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS5001"
ms.assetid: e1e26e75-84e0-47c7-be8a-3c4fd0d6f497
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS5001
'program' 프로그램에는 진입점에 적합한 정적 'Main' 메서드가 포함되어 있지 않습니다.  
  
 이 오류는 올바른 서명이 있는 고정 [Main](/dotnet/csharp/programming-guide/main-and-command-args/main-and-command-line-arguments) 메서드가 실행 파일을 생성하는 코드에서 발견된 경우 발생합니다. 이 오류는 진입점 함수인 `Main`이 소문자 `main`과 같은 잘못된 대\/소문자로 정의된 경우에도 발생할 수 있습니다.  
  
-   `Main`은 고정으로 선언되고 [void](/dotnet/csharp/language-reference/keywords/void) 또는 [int](/dotnet/csharp/language-reference/keywords/int)를 반환해야 하며 매개 변수가 없거나 `string[]` 형식의 매개 변수 중 하나가 있어야 합니다.  
  
## 예제  
 다음 예제에서는 CS5001을 생성합니다.  
  
```  
// CS5001.cs // CS5001 expected public class a { // Uncomment the following line to resolve. // static void Main() {} }  
```  
  
## 참고 항목  
 [Main\(\)과 명령줄 인수](/dotnet/csharp/programming-guide/main-and-command-args/main-and-command-line-arguments)