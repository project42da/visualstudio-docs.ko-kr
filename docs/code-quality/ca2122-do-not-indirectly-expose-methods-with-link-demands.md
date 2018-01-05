---
title: "CA2122: 링크 요청이 있는 메서드를 간접적으로 노출 하지 마십시오 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2122
- DoNotIndirectlyExposeMethodsWithLinkDemands
helpviewer_keywords:
- DoNotIndirectlyExposeMethodsWithLinkDemands
- CA2122
ms.assetid: 3eda58e7-c6ec-41c3-8112-ae0841109c6a
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: fc1d8c2ea663862e44b3092b0e2b8489eff3df6f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2122-do-not-indirectly-expose-methods-with-link-demands"></a>CA2122: 링크 요청이 있는 메서드를 간접적으로 노출하지 마십시오.
|||  
|-|-|  
|TypeName|DoNotIndirectlyExposeMethodsWithLinkDemands|  
|CheckId|CA2122|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 Public 또는 protected 멤버에는 [링크 요청](/dotnet/framework/misc/link-demands) 보안 검사를 수행 하지 않는 멤버에서 호출 됩니다.  
  
## <a name="rule-description"></a>규칙 설명  
 링크 요청은 직접 실행 호출자의 권한만 검사합니다. 구성원 인 경우 `X` 호출자 및 호출 보호 되는 코드 링크 요청에 의해 호출자가 필요한 권한을 사용할 수 없는 보안 요청을 사용 하면 `X` 보호 된 멤버에 액세스 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 보안 추가 [데이터 및 모델링](/dotnet/framework/data/index) 또는 링크 요청 된 멤버를 더 이상는 링크 요청으로 보호 되는 멤버 보안 되지 않은 액세스를 제공할 수 없습니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를에서 표시 하지 않으려면,는 코드 권한을 부여 하지 않습니다 호출자에 게 작업이 나 악용에서 사용할 수 있는 리소스에 액세스할 수 있는지 확인 해야 합니다.  
  
## <a name="example"></a>예  
 다음 예에서는 규칙을 위반 하는 라이브러리와 라이브러리의 약점을 보여 주는 응용 프로그램을 보여 줍니다. 예제 라이브러리 함께 규칙을 위반 하는 두 메서드를 제공 합니다. `EnvironmentSetting` 메서드를 환경 변수에 대 한 무제한 액세스를 위한 링크 요청에 의해 보안 됩니다. `DomainInformation` 메서드 호출 되기 전에 호출자의 보안 요청을 만들면 `EnvironmentSetting`합니다.  
  
 [!code-csharp[FxCop.Security.UnsecuredDoNotCall#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_1.cs)]  
  
## <a name="example"></a>예  
 다음 응용 프로그램은 보안 되지 않은 라이브러리 멤버를 호출합니다.  
  
 [!code-csharp[FxCop.Security.TestUnsecuredDoNot1#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_2.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
 **보안 되지 않은 멤버의 값: seattle.corp.contoso.com**   
## <a name="see-also"></a>참고 항목  
 [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)   
 [링크 요구](/dotnet/framework/misc/link-demands)   
 [데이터 및 모델링](/dotnet/framework/data/index)