---
title: "CA1800: 불필요하게 캐스팅하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1800"
  - "DoNotCastUnnecessarily"
helpviewer_keywords: 
  - "DoNotCastUnnecessarily"
  - "CA1800"
ms.assetid: b79a010a-6627-421e-8955-6007e32fa808
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1800: 불필요하게 캐스팅하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotCastUnnecessarily|  
|CheckId|CA1800|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 메서드가 인수 또는 지역 변수 중 하나에 대해 중복 캐스팅을 수행합니다.  이 규칙에 따라 완벽하게 분석하려면 테스트한 어셈블리가 디버깅 정보를 사용하여 빌드되고 관련 프로그램 데이터베이스 파일\(.pdb\)을 사용할 수 있어야 합니다.  
  
## 규칙 설명  
 중복 캐스팅을 수행하면 성능이 저하됩니다. 특히 간단한 반복 문에서 캐스팅이 수행될 때 더욱 그러합니다.  명시적인 중복 캐스트 연산의 경우에는 캐스팅 결과를 지역 변수에 저장하고 중복 캐스트 연산 대신 지역 변수를 사용합니다.  
  
 실제 캐스팅을 수행하기 전에 캐스팅이 성공할지 여부를 C\#의 `is` 연산자를 사용하여 테스트할 경우 `as` 연산자의 결과를 대신 테스트할 것을 고려해 보십시오.  이렇게 하면 `is` 연산자로 수행되는 암시적 캐스트 연산 없이 같은 기능이 제공됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 캐스트 연산 횟수를 최소화하도록 메서드 구현을 수정합니다.  
  
## 경고를 표시하지 않는 경우  
 성능 문제가 중요하지 않을 경우에는 이 규칙에서 경고를 표시하지 않거나 규칙을 완전히 무시해도 안전합니다.  
  
## 예제  
 다음 예제에서는 C\#의 `is` 연산자를 사용하여 규칙을 위반하는 메서드를 보여 줍니다.  두 번째 메서드에서는 `is` 연산자를 `as` 연산자의 결과에 대한 테스트로 바꿔 규칙을 만족시킵니다. 이렇게 하면 반복 당 캐스트 연산 횟수가 두 번에서 한 번으로 줄어듭니다.  
  
 [!code-cs[FxCop.Performance.UnnecessaryCastsAsIs#1](../code-quality/codesnippet/CSharp/ca1800-do-not-cast-unnecessarily_1.cs)]  
  
## 예제  
 다음 예제에서는 중복되는 명시적 캐스팅이 여러 개 있어 규칙을 위반하는 `start_Click` 메서드와 지역 변수에 캐스팅을 저장하여 규칙을 만족하는 `reset_Click` 메서드를 보여 줍니다.  
  
 [!code-vb[FxCop.Performance.UnnecessaryCasts#1](../code-quality/codesnippet/VisualBasic/ca1800-do-not-cast-unnecessarily_2.vb)]
 [!code-cs[FxCop.Performance.UnnecessaryCasts#1](../code-quality/codesnippet/CSharp/ca1800-do-not-cast-unnecessarily_2.cs)]  
  
## 참고 항목  
 [as](/dotnet/csharp/language-reference/keywords/as)   
 [is](/dotnet/csharp/language-reference/keywords/is)