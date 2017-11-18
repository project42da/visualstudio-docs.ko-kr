---
title: "CA1020: 몇 가지 형식으로 네임 스페이스 하지 마십시오. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
helpviewer_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
ms.assetid: 9cb272f6-a3ff-45af-b35d-70dea620b074
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c09f3fa7855f2dadfce7a22914c4a7010b84f210
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1020-avoid-namespaces-with-few-types"></a>CA1020: 형식이 부족한 네임스페이스를 사용하지 마십시오.
|||  
|-|-|  
|TypeName|AvoidNamespacesWithFewTypes|  
|CheckId|CA1020|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 전역 네임 스페이스 이외의 네임 스페이스에는 5 개 미만의 형식을 포함합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 각 네임 스페이스에 논리적 구성이, 하며 근거가 네임 스페이스에 형식을 한 유효한 이유가 넣을 수 있는지 확인 합니다. 네임 스페이스에는 대부분의 시나리오에서 함께 사용 되는 형식을 포함 해야 합니다. 응용 프로그램을 함께 사용할 수 없는 형식은 별도 네임 스페이스에 있어야 합니다. 예를 들어는 <xref:System.Web.UI> 네임 스페이스에 웹 응용 프로그램에서 사용 되는 형식이 포함 되어 및 <xref:System.Windows.Forms> 네임 스페이스에서 사용 되는 형식을 포함 [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)]-기반 응용 프로그램입니다. 두 네임스페이스에 사용자 인터페이스의 특성을 제어하는 형식이 포함되었더라도 이러한 형식은 동일한 응용 프로그램에서 사용하도록 디자인되지 않았습니다. 따라서 별도의 네임스페이스에 배치됩니다. 기능의 검색 기능을 증가 하기 때문에 주의 네임 스페이스 조직 유용할 수도 있습니다. 네임 스페이스 계층을 검사 하 여 라이브러리 소비자는 기능을 구현 하는 형식을 찾을 수 있어야 합니다.  
  
> [!NOTE]
>  디자인 타임 형식 및 사용 권한을이 지침을 준수 하도록 다른 네임 스페이스에 병합할 수 합니다. 네임 스페이스에서 종료 되어야 하 고 이러한 형식을 포함 하 고 고유한 네임 스페이스가 기본 네임 스페이스 아래의 `.Design` 및 `.Permissions`각각.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하는 하나의 네임 스페이스에 몇 개의 형식을 포함 하는 네임 스페이스를 결합 하려고 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 네임 스페이스에 다른 네임 스페이스의 형식과 함께 사용 되는 형식이 없는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.