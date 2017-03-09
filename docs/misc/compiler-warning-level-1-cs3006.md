---
title: "컴파일러 경고(수준 1) CS3006 | Microsoft Docs"
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
  - "CS3006"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3006"
ms.assetid: efbfd898-e46f-4c3d-91e2-e2da0056b016
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS3006
ref, out 또는 배열 차수만 다른 오버로드된 'method' 메서드는 CLS 규격이 아닙니다.  
  
 메서드는 [ref](/dotnet/csharp/language-reference/keywords/ref) 또는 [out](/dotnet/csharp/language-reference/keywords/out) 매개 변수를 기반으로 오버로드할 수 없으며 CLS\(공용 언어 사양\) 규격이 될 수 없습니다. CLS 규격에 대한 자세한 내용은 [CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3) 및 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)을 참조하세요.  
  
## 예제  
 다음 예제에서는 CS3006을 생성합니다. 이 경고를 해결하려면 어셈블리 수준 특성을 주석으로 처리하거나 메서드 정의 중 하나를 제거합니다.  
  
```  
// CS3006.cs using System; [assembly: CLSCompliant(true)] public class MyClass { public void f(int i) { } public void f(ref int i)   // CS3006 { } public static void Main() { } }  
```