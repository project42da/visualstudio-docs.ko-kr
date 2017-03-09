---
title: "컴파일러 오류 CS1527 | Microsoft Docs"
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
  - "CS1527"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1527"
ms.assetid: a0d52130-d6da-41bb-b153-8e96cbb7e316
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1527
네임스페이스에 정의된 요소는 명시적으로 private, protected 또는 protected internal로 선언할 수 없습니다.  
  
 네임스페이스의 형식 선언에 [public](/dotnet/csharp/language-reference/keywords/public) 또는 [internal](/dotnet/csharp/language-reference/keywords/internal) 액세스를 사용할 수 없습니다. 접근성을 지정하지 않을 경우 **internal**이 기본값입니다.  
  
 다음 샘플에서는 CS1527을 생성합니다.  
  
```  
// CS1527.cs namespace Sample { private class C1 {};             // CS1527 protected class C2 {};           // CS1527 protected internal class C3 {};  // CS1527 }  
```  
  
 프로그램 코드에서 네임스페이스를 명시적으로 선언하지 않을 경우 모든 형식 선언이 전역 네임스페이스 내에 암시적으로 배치되므로 다음 예제에서는 CS1527을 생성합니다.  
  
```  
//cs1527_2.cs using System; protected class C4{} private struct S1{}  
```  
  
## 참고 항목  
 [네임스페이스](/dotnet/csharp/programming-guide/namespaces/index)   
 [전역](/dotnet/csharp/language-reference/keywords/global)   
 [:: 연산자](../Topic/::%20Operator%20\(C%23%20Reference\).md)   
 [액세스 가능 도메인](/dotnet/csharp/language-reference/keywords/accessibility-domain)   
 [액세스 한정자](/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)