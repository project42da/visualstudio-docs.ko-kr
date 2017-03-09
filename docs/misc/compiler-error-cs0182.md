---
title: "컴파일러 오류 CS0182 | Microsoft Docs"
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
  - "CS0182"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0182"
ms.assetid: a9e97bb8-f06e-499f-aadf-26abc2082f98
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0182
특성 인수는 특성 매개 변수 형식의 배열 생성 식, 상수 식 또는 typeof 식이어야 합니다.  
  
 특성과 함께 사용할 수 있는 인수 종류에는 특정 제한이 적용됩니다. 오류 메시지에 지정된 제한 외에 다음 형식은 특성 인수로 사용할 수 없습니다.  
  
-   [sbyte](/dotnet/csharp/language-reference/keywords/sbyte)  
  
-   [ushort](/dotnet/csharp/language-reference/keywords/ushort)  
  
-   [uint](/dotnet/csharp/language-reference/keywords/uint)  
  
-   [ulong](/dotnet/csharp/language-reference/keywords/ulong)  
  
-   [decimal](/dotnet/csharp/language-reference/keywords/decimal)  
  
 자세한 내용은 [빌드에 없음: 전역 특성\(C\# 프로그래밍 가이드\)](http://msdn.microsoft.com/ko-kr/7c6c41f8-f0d5-4345-8987-3d91f9bae136)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0182를 생성합니다.  
  
```  
// CS0182.cs public class MyClass { static string s = "Test"; [System.Diagnostics.ConditionalAttribute(s)]   // CS0182 // try the following line instead // [System.Diagnostics.ConditionalAttribute("Test")] void NonConstantArgumentToConditional() { } public static void Main() { } }  
```