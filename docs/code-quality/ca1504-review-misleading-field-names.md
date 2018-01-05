---
title: "CA1504: 잘못 된 필드 이름을 검토 하십시오. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ReviewMisleadingFieldNames
- CA1504
helpviewer_keywords:
- CA1504
- ReviewMisleadingFieldNames
ms.assetid: 94136ff1-4aaf-4dc2-9170-48c171ab7499
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: dc1317380eab4a63a7c60557fbec258485768885
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1504-review-misleading-field-names"></a>CA1504: 잘못된 필드 이름을 검토하십시오.
|||  
|-|-|  
|TypeName|ReviewMisleadingFieldNames|  
|CheckId|CA1504|  
|범주|Microsoft.Maintainability|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 인스턴스 필드의 이름이의 이름 또는 "s_"로 시작는 `static` (`Shared` 에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) 필드의 "m_"로 시작 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 필드 이름은 "s_"로 시작 하는 많은 사용자가 정적 데이터와 연결 됩니다. 마찬가지로, "m_"로 시작 하는 필드 이름은 (멤버) 인스턴스 데이터와 연결 됩니다. 보다 쉽게 관리 코드의 경우 이름은 일반적으로 사용 되는 규칙을 따라야 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 적절 한 접두사를 사용 하 여 필드를 이름을 바꿉니다. 추가 또는 제거 하 여 현재 접미사와 함께 필드를 확인 또는 `static` 한정자입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.