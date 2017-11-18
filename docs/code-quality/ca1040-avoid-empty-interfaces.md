---
title: ": Ca1040 파일을 빈 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1040
- AvoidEmptyInterfaces
helpviewer_keywords:
- AvoidEmptyInterfaces
- CA1040
ms.assetid: 120a741b-5fd1-4836-8453-7857e0cd0380
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7e086ffc1b0166ec17954323b8cf7871fd758ea0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1040-avoid-empty-interfaces"></a>CA1040: 빈 인터페이스를 사용하지 마십시오.
|||  
|-|-|  
|TypeName|AvoidEmptyInterfaces|  
|CheckId|CA1040|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 인터페이스는 멤버를 선언 하지 않거나 두 개 이상의 다른 인터페이스를 구현 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 인터페이스에서는 동작이나 사용 계약을 제공하는 멤버를 정의합니다. 인터페이스에 의해 설명되는 기능은 상속 계층 구조에서 형식이 나타나는 위치에 관계없이 모든 형식에서 사용할 수 있습니다. 형식에서는 인터페이스의 멤버에 대한 구현을 제공하여 인터페이스를 구현합니다. 빈 인터페이스는 멤버를 정의 하지 않습니다. 따라서 구현할 수 있는 계약을 정의 하지 않습니다.  
  
 디자인 빈 포함 되 면 구현이 필요한 형식은 인터페이스, 인터페이스 표식을 또는 형식의 그룹을 식별 하는 방법으로 사용할 것입니다. 이 식별 런타임 시 발생 하 게이를 위해 올바른 방법은 사용자 지정 특성을 사용 하는 것입니다. 존재 여부 또는 특성의 부재 또는 특성의 속성을 사용 하 여 대상 형식을 식별 합니다. 다음 빈 인터페이스를 사용 하는 것이 좋습니다 식별 컴파일 타임에 발생 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 인터페이스를 제거 하거나 멤버를 추가 합니다. 빈 인터페이스는 형식 집합에 레이블을 지정 하를 사용 하는 경우 사용자 지정 특성을 가진 인터페이스를 대체 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 인터페이스는 컴파일 타임에 형식의 집합을 식별 하는 데 사용 되는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 빈 인터페이스를 보여 줍니다.  
  
 [!code-csharp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CSharp/ca1040-avoid-empty-interfaces_1.cs)]
 [!code-cpp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CPP/ca1040-avoid-empty-interfaces_1.cpp)]
 [!code-vb[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/VisualBasic/ca1040-avoid-empty-interfaces_1.vb)]