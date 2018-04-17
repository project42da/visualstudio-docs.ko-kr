---
title: 'CA1726: 기본 설정된 용어를 사용 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- UsePreferredTerms
- CA1726
helpviewer_keywords:
- UsePreferredTerms
ms.assetid: 642b2acd-3a33-4d1f-b0a7-67073ae73be2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5e37ed041d03e82a63929a7bc525c73ea4062333
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1726-use-preferred-terms"></a>CA1726: 기본 설정 용어를 사용하십시오.
|||  
|-|-|  
|TypeName|UsePreferredTerms|  
|CheckId|CA1726|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경-어셈블리에서 발생 한 경우<br /><br /> 아님-형식 매개 변수에서 발생 한 경우|  
  
## <a name="cause"></a>원인  
 외부에서 볼 수 있는 식별자의 이름에 특정 용어가 포함되어 있는데, 이 용어에는 기본 설정된 대체 용어가 있습니다. 또는 이름 플래그 나 플래그 라는 용어가 포함 되어 있습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 이 규칙을 토큰으로 식별자 구문 분석합니다. 각 토큰 및 각 연속 이중 토큰 조합 및 사용자 지정 사전의 Deprecated 섹션에서 규칙에 있는 용어와 비교 됩니다. 다음 표에서 규칙 및 기본 설정된 대체 기능의에 내장 된 용어를 보여 줍니다.  
  
|사용 되지 않는 용어|기본 설정된 용어|  
|-------------------|--------------------|  
|되지 않습니다.|있고|  
|취소됨|Canceled|  
|수 없음|수 없습니다.|  
|ComPlus|EnterpriseServices|  
|Couldnt|CouldNot|  
|Didnt|DidNot|  
|Doesnt|하지 않습니다|  
|금지|보기가|  
|플래그 또는 플래그|없는 대체 용어가 있습니다. 사용하지 마십시오.|  
|하지 않은|HadNot|  
|되지 않았습니다.|HasNot|  
|하지 않은|HaveNot|  
|인덱스|Indexes|  
|되지 않습니다.|IsNot|  
|로그인|로그온|  
|로그 아웃|로그 오프|  
|Shouldnt|ShouldNot|  
|SignOn|SignIn|  
|비공식 승인|로그 아웃|  
|Wasnt|WasNot|  
|되지 않았습니다.|WereNot|  
|안 됨|WillNot|  
|Wouldnt|WouldNot|  
|쓰기 가능|쓰기 가능|  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 대체 하는 기본 용어와 해당 용어를 대체 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 식별자의 이름을 의도적인 하는 기본 용어 대신 원래 용어와 특히 관련이 하는 경우에이 규칙에서 경고를 표시 합니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [이름 지정 경고](../code-quality/naming-warnings.md)