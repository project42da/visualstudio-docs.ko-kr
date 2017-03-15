---
title: "컴파일러 경고(수준 1) CS3002 | Microsoft Docs"
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
  - "CS3002"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3002"
ms.assetid: 34f19735-76d2-4d78-bd52-45989a86fca4
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS3002
'method'의 반환 형식이 CLS 규격이 아닙니다.  
  
 [public](/dotnet/csharp/language-reference/keywords/public), [protected](/dotnet/csharp/language-reference/keywords/protected) 또는 `protected``internal` 메서드는 형식이 CLS\(공용 언어 사양\) 규격인 값을 반환해야 합니다. CLS 규격에 대한 자세한 내용은 [CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3) 및 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)를 참조하세요.  
  
## 예제  
 다음 예제에서는 CS3002를 생성합니다.  
  
```  
// CS3002.cs [assembly:System.CLSCompliant(true)] public class a { public ushort bad()   // CS3002, public method { ushort a; a = ushort.MaxValue; return a; } private ushort OK()   // OK, private method { ushort a; a = ushort.MaxValue; return a; } public static void Main() { } }  
```