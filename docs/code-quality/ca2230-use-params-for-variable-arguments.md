---
title: "CA2230: 가변 인수로 params를 사용하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "UseParamsForVariableArguments"
  - "CA2230"
helpviewer_keywords: 
  - "CA2230"
  - "UseParamsForVariableArguments"
ms.assetid: bf98b733-4855-4110-9f16-eba5a9e79421
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2230: 가변 인수로 params를 사용하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|UseParamsForVariableArguments|  
|CheckId|CA2230|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected 형식에 `VarArgs` 호출 규칙을 사용하는 public 또는 protected 메서드가 들어 있습니다.  
  
## 규칙 설명  
 `VarArgs` 호출 규칙은 매개 변수 개수가 가변적인 특정 메서드 정의에 사용됩니다.  `VarArgs` 호출 규칙을 사용하는 메서드는 CLS\(공용 언어 사양\) 규격이 아니며 프로그래밍 언어에 따라 액세스하지 못할 수도 있습니다.  
  
 C\#에서는 메서드의 매개 변수 목록이 `__arglist` 키워드로 끝날 경우 `VarArgs` 호출 규칙이 사용됩니다.  Visual Basic에서는 `VarArgs` 호출 규칙을 지원하지 않으며 Visual C\+\+에서는 줄임표\(`...`\) 표기법을 사용하는 비관리 코드에서만 이 호출 규칙을 사용할 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 C\#에서 이 규칙의 위반 문제를 해결하려면 `__arglist` 대신 [params](/dotnet/csharp/language-reference/keywords/params) 키워드를 사용합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 두 가지 메서드 즉, 규칙을 위반하는 메서드와 규칙을 만족하는 메서드를 보여 줍니다.  
  
 [!code-cs[FxCop.Usage.UseParams#1](../code-quality/codesnippet/CSharp/ca2230-use-params-for-variable-arguments_1.cs)]  
  
## 참고 항목  
 <xref:System.Reflection.CallingConventions?displayProperty=fullName>   
 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)