---
title: "CA2228: 릴리스되지 않은 리소스 형식을 제공 하지 마십시오 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 959d88751ff250e54f6a3f89f0b4b0554add96d1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228: 릴리스되지 않은 리소스 형식을 제공하지 마십시오.
|||  
|-|-|  
|TypeName|DoNotShipUnreleasedResourceFormats|  
|CheckId|CA2228|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 리소스 파일의 버전을 사용 하 여 빌드된는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 는 현재 지원 되지 않습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 시험판 버전을 사용 하 여 빌드된 리소스 파일은 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 지원 되는 버전의.NET Framework에서 사용할 수 있습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 지원 되는 버전을 사용 하 여 리소스를 작성은 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]k.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.