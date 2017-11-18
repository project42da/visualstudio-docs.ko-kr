---
title: ": Ca1501 파일을 상 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1501
- AvoidExcessiveInheritance
helpviewer_keywords:
- AvoidExcessiveInheritance
- CA1501
ms.assetid: 9e934746-1a4d-492a-91e4-085201abafa4
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3c09a3367985613072944c5f74f0c708a149da15
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1501-avoid-excessive-inheritance"></a>CA1501: 상속성을 너무 많이 사용하지 마십시오.
|||  
|-|-|  
|TypeName|AvoidExcessiveInheritance|  
|CheckId|CA1501|  
|범주|Microsoft.Maintainability|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 형식이 상속 계층 구조에서 네 단계보다 아래에 있습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 여러 번 중첩된 형식 계층 구조는 추적하고, 이해하고, 유지 관리하기가 어렵습니다. 이 규칙에는 동일한 모듈에는 계층에 분석을 제한합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 상속 계층 구조에서는 비교적 위에 있는 기본 형식에서 형식을 파생 또는 중간 기본 형식 중 일부를 제거 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서 경고를 표시 하지 않아도 안전 합니다. 그러나 코드 유지 관리 하기 어려울 수 있습니다. 즉, 기본 형식의 표시 여부에 따라이 규칙이 위반 해결 만들 수 주요 변경 내용 note 합니다. 예를 들어 공용 기본 형식을 제거 주요 변경 내용입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.  
  
 [!code-csharp[FxCop.Maintainability.ExcessiveInheritance#1](../code-quality/codesnippet/CSharp/ca1501-avoid-excessive-inheritance_1.cs)]
 [!code-vb[FxCop.Maintainability.ExcessiveInheritance#1](../code-quality/codesnippet/VisualBasic/ca1501-avoid-excessive-inheritance_1.vb)]