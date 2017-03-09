---
title: "컴파일러 경고(수준 1) CS3005 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS3005"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3005"
ms.assetid: 64b687e3-2dbd-45dd-b6da-81f77eb7d6bd
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS3005
대\/소문자만 다른 'identifier' 식별자가 CLS 규격이 아닙니다.  
  
 다른 `public`, `protected` 또는 `protected` `internal` 식별자와 하나 이상 문자의 대\/소문자만 다른 [public](/dotnet/csharp/language-reference/keywords/public), [protected](/dotnet/csharp/language-reference/keywords/protected) 또는 `protected` `internal` 식별자는 CLS\(공용 언어 사양\) 규격이 아닙니다. CLS 규격에 대한 자세한 내용은 [CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3) 및 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)를 참조하세요.  
  
## 예제  
 다음 예제에서는 CS3003이 생성됩니다.  
  
```  
// CS3005.cs using System; [assembly:CLSCompliant(true)] public class a { public static int a1 = 0; public static int A1 = 1;   // CS3005 public static void Main() { Console.WriteLine(a1); Console.WriteLine(A1); } }  
```