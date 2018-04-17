---
title: 코드 분석 문제 해결 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: 61c7e44d-2780-4df5-9bcb-49e40c1152fc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d50bbe4a5969d0614370e0aa0e1a15455b6a458a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="troubleshooting-code-analysis-issues"></a>코드 분석 문제 해결
이 항목에는 다음 Visual Studio 코드 분석 문제에 대한 문제 해결 정보가 포함되어 있습니다.  
  
-   [Visual Studio 2010 규칙 집합의 변경 내용이 이전 Visual Studio 버전에 반영되지 않음](#ChildRuleSetChangesInPreviousVersions)  
  
##  <a name="ChildRuleSetChangesInPreviousVersions"></a> Visual Studio 2010 규칙 집합의 변경 내용이 이전 Visual Studio 버전에 반영되지 않음  
 자식 규칙 집합이 포함된 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]에서 규칙 집합을 만드는 경우, 자식 규칙 집합의 변경 내용이 이전 버전의 Visual Studio를 사용하는 컴퓨터에서 실행되는 코드 분석에 적용되지 않을 수 있습니다. 이 문제를 해결하려면 자식 규칙 집합을 포함하는 규칙 집합인 부모 규칙 집합을 다시 작성해야 합니다.  
  
1.  [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]에서 부모 규칙 집합을 엽니다.  
  
2.  규칙 추가 또는 제거와 같은 변경을 수행한 후 규칙 집합을 저장합니다.  
  
3.  규칙 집합을 다시 열고, 변경을 취소한 후 다시 저장합니다.  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 품질 분석](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md)   
 [관리 코드 품질 분석](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)   
 [규칙 집합을 사용하여 코드 분석 규칙 그룹화](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)