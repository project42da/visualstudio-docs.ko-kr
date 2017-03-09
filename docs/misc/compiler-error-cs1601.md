---
title: "컴파일러 오류 CS1601 | Microsoft Docs"
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
  - "CS1601"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1601"
ms.assetid: 5efa1d2d-c70c-446d-a51f-d23d8a3be22e
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1601
메서드 또는 대리자 매개 변수는 'type' 형식일 수 없습니다.  
  
 .NET Framework 클래스 라이브러리의 일부 유형, 예를 들어 <xref:System.TypedReference>, <xref:System.RuntimeArgumentHandle> 및 <xref:System.ArgIterator>는 잠재적으로 안전하지 않은 작업을 수행하는 데 사용될 수 있기 때문에 [ref](/dotnet/csharp/language-reference/keywords/ref) 또는 [out](/dotnet/csharp/language-reference/keywords/out) 매개 변수로 사용할 수 없습니다.  
  
 다음 샘플에서는 CS1601을 생성합니다.  
  
```  
// CS1601.cs using System; class MyClass { public void Test1 (ref TypedReference t)   // CS1601 { } public void Test2 (out ArgIterator t)   // CS1601 { } }  
```