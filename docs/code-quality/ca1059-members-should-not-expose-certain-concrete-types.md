---
title: "CA1059: 멤버는 구체적인 특정 형식을 노출 하지 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1059
- MembersShouldNotExposeCertainConcreteTypes
helpviewer_keywords:
- MembersShouldNotExposeCertainConcreteTypes
- CA1059
ms.assetid: 59f61f52-8d6c-49cb-aefb-191910523a3c
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d5b8b4a50ce23a7ed50f2e608334f9b438a0b090
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1059-members-should-not-expose-certain-concrete-types"></a>CA1059: 멤버는 구체적인 특정 형식을 노출하면 안 됩니다.
|||  
|-|-|  
|TypeName|MembersShouldNotExposeCertainConcreteTypes|  
|CheckId|CA1059|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 외부에서 볼 수 있는 멤버는 구체적인 특정 형식 또는 매개 변수 중 하나를 통해 구체적인 특정 형식을 노출 하거나 값을 반환 합니다. 현재,이 규칙 보고 다음 구체적인 형식 노출 합니다.  
  
-   파생 된 형식을 <xref:System.Xml.XmlNode?displayProperty=fullName>합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 구체적인 형식은 완전히 구현되었기 때문에 인스턴스화할 수 있는 형식을 말합니다. 광범위 하 게 멤버의 사용을 허용 하려면 구체적인 형식을 제안 된 인터페이스로 바꾸십시오. 따라서 멤버는 인터페이스를 구현 하는 모든 형식을 받아들일 또는 인터페이스를 구현 하는 형식이 필요한 곳에 사용할 수 있습니다.  
  
 다음 표에서 대상된 구체적인 형식 및 제안 된 대신 사용할 나열합니다.  
  
|구체적인 형식|Replacement|  
|-------------------|-----------------|  
|<xref:System.Xml.XPath.XPathDocument>|<xref:System.Xml.XPath.IXPathNavigable?displayProperty=fullName>.<br /><br /> 인터페이스를 사용 하는 XML 데이터 원본의 특정 구현에서 멤버를 분리 합니다.|  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 구체적인 형식을 제안 된 인터페이스로 변경 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 구체적인 형식에서 제공 하는 특정 기능이 필요한 경우이 규칙에서 메시지를 표시 하지 않으려면 안전 합니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1011: 기본 형식을 매개 변수로 전달해 보십시오.](../code-quality/ca1011-consider-passing-base-types-as-parameters.md)