---
title: "CA2123: 재정의 링크 요청과 같아야 따르는 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2123
- OverrideLinkDemandsShouldBeIdenticalToBase
helpviewer_keywords:
- OverrideLinkDemandsShouldBeIdenticalToBase
- CA2123
ms.assetid: 4538ecd5-fc6f-4480-ab00-90b2ce4730db
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3181e791d95f0268fd60654e8ceedb8fa394f7a0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2123-override-link-demands-should-be-identical-to-base"></a>CA2123: 재정의 링크 요청은 기본 형식의 링크 요청과 같아야 합니다.
|||  
|-|-|  
|TypeName|OverrideLinkDemandsShouldBeIdenticalToBase|  
|CheckId|CA2123|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 공용 형식에서 public 또는 protected 메서드가 메서드를 재정의 하거나 인터페이스를 구현 있고 동일한 갖지 않는 [링크 요청](/dotnet/framework/misc/link-demands) 인터페이스 또는 가상 메서드.  
  
## <a name="rule-description"></a>규칙 설명  
 이 규칙에서는 메서드를 다른 형식의 인터페이스이거나 가상 메서드인 기본 메서드에 일치시킨 다음 각각에 대해 링크 요청을 비교합니다. 메서드 또는 기본 메서드가 링크 요청이 있는 경우 하지 않으면 위반이 보고 됩니다.  
  
 이 규칙이 위반 되 면 악의적인 호출자가 보안 되지 않은 메서드를 호출 하 여 링크 요청을 우회할 수 있습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 재정의 메서드 또는 구현에 동일한 링크 요청을 적용 합니다. 없는 경우에 전체 demand로이 메서드를 표시 하거나 특성을 완전히 제거 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는이 규칙의 다양 한 위반을 보여 줍니다.  
  
 [!code-csharp[FxCop.Security.OverridesAndSecurity#1](../code-quality/codesnippet/CSharp/ca2123-override-link-demands-should-be-identical-to-base_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)   
 [링크 요구](/dotnet/framework/misc/link-demands)