---
title: "CA1821: 빈 종료자를 제거 하세요. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RemoveEmptyFinalizers
- CA1821
helpviewer_keywords: CA1821
ms.assetid: 3f4855a0-e4a0-46e6-923c-4c3b7074048d
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: afe1c05ff76a2b4c37296ef6a534e37a5d1229b6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1821-remove-empty-finalizers"></a>CA1821: 빈 종료자를 제거하십시오.
|||  
|-|-|  
|TypeName|RemoveEmptyFinalizers|  
|CheckId|CA1821|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 한 형식은 비어, 기본 형식 종료자만 호출 하거나 조건부로 내보낸 메서드를 호출 하는 종료자를 구현 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 개체 수명을 추적할 때에는 추가로 성능 오버헤드가 발생하므로 가능한 경우 종료자를 사용하지 마십시오. 가비지 수집기에서는 개체를 수집 하기 전에 종료자를 실행 합니다. 이 두 컬렉션 개체를 수집 하려면 해야 하는 것을 의미 합니다. 빈 종료자 부과 이러한 아무런 장점 없이 오버 헤드가 추가 됩니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 빈 종료자를 제거 합니다. 종료자를 디버깅 해야 하는 경우 전체 종료자를 묶습니다 `#if DEBUG / #endif` 지시문입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서 메시지를 표시 하지 마십시오. 종료 되지 않도록 하지 않으면 성능이 저하 되 고 이점이 없습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 빈 종료자를 제거 해야 하는에 포함 되어야 하는 종료자 `#if DEBUG / #endif` 지시문 및 사용 하는 종료자는 `#if DEBUG / #endif` 지시문 올바르게 합니다.  
  
 [!code-csharp[FxCop.Performance.RemoveEmptyFinalizers#1](../code-quality/codesnippet/CSharp/ca1821-remove-empty-finalizers_1.cs)]