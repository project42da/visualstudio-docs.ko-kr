---
title: ": Ca1506 클래스 결합 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AvoidExcessiveClassCoupling
- CA1506
helpviewer_keywords:
- AvoidExcessiveClassCoupling
- CA1506
ms.assetid: 9f0943c0-e802-4e3f-8798-2ab8653ddc80
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8192868aa7c5d79039a5e94a2aa13c47ada5d47c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1506-avoid-excessive-class-coupling"></a>CA1506: 클래스 결합을 지나치게 많이 사용하지 마십시오.
|||  
|-|-|  
|TypeName|AvoidExcessiveClassCoupling|  
|CheckId|CA1506|  
|범주|Microsoft.Maintainability|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 형식 또는 메서드는 다양 한 종류와 관련 됩니다.  
  
## <a name="rule-description"></a>규칙 설명  
 이 규칙은 형식 또는 메서드에 들어 있는 고유한 형식 참조의 개수를 계산하여 클래스 결합을 측정합니다.  
  
 형식 및 메서드는 높은 수준의 클래스 결합을 유지 하기 어려울 수 있습니다. 형식 및 낮은 결합 및 높은 응집력 수행 하는 메서드를 보는 것이 좋습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 위반으로이 인해를 해결 하려면 형식 또는 메서드는 결합 된 형식의 수를 줄이기 위해를 다시 디자인 해 보십시오.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 형식 또는 메서드의 크더라도 아직 많은 다른 형식에 대 한 종속성도 불구 하 고 경우에이 경고를 제외 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [유지 관리 경고](../code-quality/maintainability-warnings.md)   
 [관리 코드의 복잡성 및 유지 관리 용이성 측정](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)