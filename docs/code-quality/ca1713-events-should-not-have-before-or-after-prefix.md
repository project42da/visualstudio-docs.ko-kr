---
title: ": 이벤트 ca1713 하지 마십시오 before 또는 after 접두사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- EventsShouldNotHaveBeforeOrAfterPrefix
- CA1713
helpviewer_keywords:
- CA1713
- EventsShouldNotHaveBeforeOrAfterPrefix
ms.assetid: 855772a4-aa9e-410b-88c1-c5fba1ca63da
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c211d2f2cc65c12fd11782058c5e8b8a3aaf47b6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1713-events-should-not-have-before-or-after-prefix"></a>CA1713: 이벤트에 Before 또는 After 접두사를 사용하지 마십시오.
|||  
|-|-|  
|TypeName|EventsShouldNotHaveBeforeOrAfterPrefix|  
|CheckId|CA1713|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 이벤트의 이름 'Before' 또는 'After'로 시작 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 이벤트 이름은 이벤트를 발생 하는 동작을 설명 해야 합니다. 특정 시퀀스에서 발생하는 관련 이벤트의 이름을 지정하려면 현재 또는 과거 시제를 사용하여 동작 시퀀스 내의 상대적인 위치를 나타냅니다. 예를 들어 이벤트 쌍 서버인 발생 하면 리소스를 닫을 때 있습니다 수 이름을 '닫는' 및 'BeforeClose' 및 'AfterClose' 대신 ' 종결'을 지정 합니다.  
  
 명명 규칙은 공통 된 모양을 라이브러리에 대 한 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 필요 하 고 관리 되는 코드를 개발에 대 한 전문 지식이 있는 사용자가 라이브러리를 개발 하는 신뢰성이 향상를 배워야 할 필요성이 줄어듭니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이벤트 이름에서 접두사를 제거 하 고 이름을 변경 하면 현재 또는 과거 시제 동사를 사용 하는 것이 좋습니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.