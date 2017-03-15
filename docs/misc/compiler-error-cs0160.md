---
title: "컴파일러 오류 CS0160 | Microsoft Docs"
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
  - "CS0160"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0160"
ms.assetid: 4ef07061-8ef5-42d9-b043-3f81307d569f
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0160
이전의 catch 절에서 이 형식이나 상위 형식\('type'\)의 예외를 모두 catch합니다.  
  
 일련의 **catch** 문을 파생의 내림차순으로 정렬해야 합니다. 예를 들어 가장 많이 파생된 개체가 첫 번째로 나타나야 합니다.  
  
 자세한 내용은 [예외 처리문](/dotnet/csharp/language-reference/keywords/exception-handling-statements) 및 [예외 및 예외 처리](/dotnet/csharp/programming-guide/exceptions/exceptions-and-exception-handling)를 참조하세요.  
  
 다음 샘플에서는 CS0160을 생성합니다.  
  
```  
// CS0160.cs public class MyClass2 : System.Exception {} public class MyClass { public static void Main() { try {} catch(System.Exception) {}   // Second-most derived; should be second catch catch(MyClass2) {}   // CS0160  Most derived; should be first catch } }  
```