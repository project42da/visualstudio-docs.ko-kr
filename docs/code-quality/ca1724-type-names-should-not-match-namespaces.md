---
title: 'CA1724: 형식 이름은 네임스페이스와 달라야 합니다.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c1f9e13f8e02712ba4d0a0a492a9a6588f7a8a5e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724: 형식 이름은 네임스페이스와 달라야 합니다.
|||
|-|-|
|TypeName|TypeNamesShouldNotMatchNamespaces|
|CheckId|CA1724|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 형식 이름이 일치는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 대/소문자 구분 비교에서 네임 스페이스 이름입니다.

## <a name="rule-description"></a>규칙 설명
 형식 이름은 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 클래스 라이브러리에 정의된 네임스페이스의 이름과 같아서는 안 됩니다. 이 규칙을 위반하면 라이브러리의 유용성이 저하될 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이름을 일치 하지 않는 형식 이름을 선택 된 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 클래스 라이브러리 네임 스페이스입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 새로운 개발의 경우 알려져 있지 않습니다에 대 한이 규칙에서 경고를 표시 해야 하는 시나리오가 발생 합니다. 경고를 억제 하기 전에 신중히 어떻게 라이브러리는 사용자가 혼동을 줄 수는 일치 하는 이름으로 고려 합니다. 제공 되는 라이브러리에는이 규칙에서 경고를 표시 해야 할 수 있습니다.