---
title: 코드 분석 체크 인 정책에 대 한 버전 호환성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- version compatibility, code analysis check-in policy
- check-in policies, version compatibility for code analysis
ms.assetid: 1af376e3-3be7-4445-803b-76a858567a5b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 045352555415aaca6e09c25fb93dc464fd7f43fc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="version-compatibility-for-code-analysis-check-in-policies"></a>코드 분석 체크 인 정책에 대한 버전 호환성
코드 분석 체크 인 정책을의 서로 다른 버전을 사용 하 여 작성 하 고 평가 해야 하는 경우 [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)], 방법의 차이점을 알고 있어야 [!INCLUDE[vstsTfsOrcasLong](../code-quality/includes/vststfsorcaslong_md.md)] 및 [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] 체크 인 정책을 평가 합니다.  
  
## <a name="version-compatibility-for-evaluating-check-in-policies"></a>체크 인 정책 평가 위한 버전 호환성  
  
-   코드 분석 체크 인 정책을 평가 하는 경우 [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)]에 존재 하는 모든 규칙 [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] 에 존재 하지 않는 있지만 [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] 무시 됩니다.  
  
-   코드 분석 체크 인 정책을 평가 하는 경우 [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)]에 적용 되는 모든 새로운 규칙 [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] 무시 됩니다.  
  
-   코드 분석 체크 인 정책 규칙 어셈블리를 지정 하는 경우 [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] 인식 하지 않으므로 어셈블리에서 지정 된 모든 규칙을 무시 합니다.  
  
-   코드 분석 체크 인 정책 규칙 어셈블리를 지정 하는 경우는 [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] 인식할 수 없는 메시지가 표시 됩니다.  
  
## <a name="version-compatibility-for-authoring-check-in-policies"></a>체크 인 정책을 작성에 대 한 버전 호환성  
  
-   사용 하 여 코드 분석 체크 인 정책을 만든 경우는 [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] 버전의 [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)]를 사용할 수 없습니다는 [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] 버전의 [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] 수정 합니다. 또한 [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] 정책을 평가할 수 없습니다.  
  
-   사용 하 여 코드 분석 체크 인 정책을 만든 경우 [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] 에 [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)]를 사용할 수 있습니다 [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] 에 [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] 수정한 다음 정책에도 여 평가 [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)]합니다. 정책을 사용 하 여 수정한 후 [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] 에 [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], 사용 하 여 정책을 편집 더 이상 하면 [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] 에서 [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)]합니다. [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)]은 강력한 이름이 일치하지 않는 문제 없이 정책을 평가할 수 있습니다.  
  
-   둘 다에 적용 되는 규칙 설정으로 코드 분석 체크 인 정책을 만들려면 [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] 및 [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)]에 정책을 만들어야 [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)], 필요한 모든 변경 하 고 정책을 저장 합니다. 규칙을 변경에만 존재 하는 경우 [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)]를 수정 하 고 정책에 저장 [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)]합니다.  
  
     정책에 저장 한 후 [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], 더 이상에 존재 하는 규칙에 대 한 설정을 변경할 [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] 만 합니다.