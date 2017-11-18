---
title: "코드 분석 문제 해결 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61c7e44d-2780-4df5-9bcb-49e40c1152fc
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6e552570eb48b9210b366ebbfe157fe656ab3fe0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="troubleshooting-code-analysis-issues"></a>코드 분석 문제 해결
이 항목에는 다음 Visual Studio 코드 분석 문제에 대 한 문제 해결 정보가 있습니다.  
  
-   [Visual Studio 2010 규칙 집합 되지 않는다 이전 Visual Studio 버전에 반영의 변경 내용](#ChildRuleSetChangesInPreviousVersions)  
  
##  <a name="ChildRuleSetChangesInPreviousVersions"></a>Visual Studio 2010 규칙 집합 되지 않는다 이전 Visual Studio 버전에 반영의 변경 내용  
 규칙 집합을 만들 때 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] 자식 규칙 집합을 포함 하 되, 자식 규칙 집합에 대 한 변경 코드 분석 실행을 이전 버전의 Visual Studio를 사용 하는 컴퓨터에 적용 될 수 있습니다. 이 문제를 해결 하려면 다시 부모 규칙 집합은 자식 규칙 집합을 포함 하는 규칙 집합을 작성 해야 합니다.  
  
1.  부모 규칙 집합을 엽니다 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]합니다.  
  
2.  추가 하거나 제거 하는 규칙 등을 변경 하 고 규칙 집합을 저장 합니다.  
  
3.  규칙 집합을 다시 열고, 반대로 변경 하 고 규칙 집합을 다시을 저장 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 품질 분석](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md)   
 [관리 코드 품질 분석](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)   
 [규칙 집합을 사용하여 코드 분석 규칙 그룹화](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)