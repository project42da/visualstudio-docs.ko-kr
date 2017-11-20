---
title: ': Ca1809 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1809
- AvoidExcessiveLocals
helpviewer_keywords:
- AvoidExcessiveLocals
- CA1809
ms.assetid: 5c81ea43-cb49-448f-980f-a1dd9764043c
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0a96616d1ee0f7c63e8f36f56a18f234fa27a173
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1809-avoid-excessive-locals"></a>CA1809: 불필요한 로컬 항목을 사용하지 마십시오.
|||  
|-|-|  
|TypeName|AvoidExcessiveLocals|  
|CheckId|CA1809|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 멤버 중 일부는 컴파일러에서 생성 된 수도 64 개 이상의 지역 변수를 포함 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 으로 참조 되는 메모리에 아닌 프로세서 레지스터에 값을 저장 하는 성능 최적화에 많이 *의 레지스터 등록* 값입니다. 공용 언어 런타임 레지스터에 저장할 수에 대 한 지역 변수를 최대 64 개를 고려합니다. 레지스터 없는 변수를 스택에 배치 되 고 조작 하기 전에 레지스터로 이동 해야 합니다. 있도록 하려면 모든 지역 변수가 레지스터를 64 개로 지역 변수의 개수를 제한 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 64 개 이하의 로컬 변수를 사용 하는 구현을 리팩터링 하십시오.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 성능이 중요 하지 않은 경우 해당 규칙을 사용 하지 않도록 설정 하거나이 규칙에서는 경고를에서 표시 하지 않으려면에 안전 합니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1804: 사용되지 않는 로컬 항목을 제거하십시오.](../code-quality/ca1804-remove-unused-locals.md)