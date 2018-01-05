---
title: ": 중첩된 형식은 해야 하지 ca1034 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
helpviewer_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
ms.assetid: e9789a2c-2540-42a1-8705-ae7104011194
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: dc35514eab2344c086305ec88435ff8a32285e4f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1034-nested-types-should-not-be-visible"></a>CA1034: 중첩 형식은 노출하지 마십시오.
|||  
|-|-|  
|TypeName|NestedTypesShouldNotBeVisible|  
|CheckId|CA1034|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 외부에서 볼 수 있는 형식이 외부에서 볼 수 있는 형식 선언이 포함 되어 있습니다. 중첩 된 열거형 및 보호 된 형식에는이 규칙에서 제외 됩니다.  
  
## <a name="rule-description"></a>규칙 설명  
 중첩된 형식은 다른 형식의 범위 내에 선언 된 형식이 있습니다. 중첩된 형식은 포함 하는 형식의 private 구현 정보를 캡슐화 하는 데 유용 합니다. 이 용도로 사용할 경우 중첩 형식은 외부에 노출되면 안 됩니다.  
  
 논리적 그룹에 대 한 또는; 이름 충돌을 방지 하기 위해 외부에서 볼 수 있는 중첩된 형식을 사용 하지 마십시오 대신 네임 스페이스를 사용 합니다.  
  
 중첩된 형식은 일부 프로그래머 명확 하 게 이해 하지 않으면 멤버 액세스 가능성의 개념을 포함 합니다.  
  
 Protected 형식은 하위 클래스와 고급 사용자 지정 시나리오에서 중첩 된 형식에 사용할 수 있습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 외부에 노출 하는 중첩된 형식을 의도가 없으면 형식의 액세스 가능성을 변경 합니다. 그렇지 않은 경우 해당 부모에서는 중첩된 형식을 제거 합니다. 중첩의 목적은 중첩된 형식의 분류 하는 계층 구조를 만드는 대신 네임 스페이스를 사용 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.  
  
 [!code-cpp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CPP/ca1034-nested-types-should-not-be-visible_1.cpp)]
 [!code-csharp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CSharp/ca1034-nested-types-should-not-be-visible_1.cs)]
 [!code-vb[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/VisualBasic/ca1034-nested-types-should-not-be-visible_1.vb)]