---
title: "코드 분석 문제 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 61c7e44d-2780-4df5-9bcb-49e40c1152fc
caps.latest.revision: 5
author: "erickson-doug"
ms.author: "douge"
manager: "douge"
caps.handback.revision: 5
---
# 코드 분석 문제 해결
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목에는 다음과 같은 Visual Studio 코드 분석 문제를 해결하기 위한 정보가 있습니다.  
  
-   [Visual Studio 2010 규칙 집합의 변경 내용이 이전 버전의 Visual Studio에서 반영되지 않음](#ChildRuleSetChangesInPreviousVersions)  
  
##  <a name="ChildRuleSetChangesInPreviousVersions"></a> Visual Studio 2010 규칙 집합의 변경 내용이 이전 버전의 Visual Studio에서 반영되지 않음  
 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]에서 자식 규칙 집합이 포함된 규칙 집합을 만들 경우 이전 버전의 Visual Studio를 사용하는 컴퓨터에서는 자식 규칙 집합에 대한 변경 내용이 코드 분석 실행 시 적용되지 않을 수 있습니다.  이 문제를 해결하려면 해당 자식 규칙 집합이 포함된 규칙 집합인 부모 규칙 집합을 다시 작성해야 합니다.  
  
1.  [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]에서 부모 규칙 집합을 엽니다.  
  
2.  규칙을 추가하거나 제거하는 등의 변경 작업을 수행한 다음 규칙 집합을 저장합니다.  
  
3.  규칙 집합을 다시 열고 변경 내용을 되돌린 다음 규칙 집합을 다시 저장합니다.  
  
## 참고 항목  
 [응용 프로그램 품질 분석](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md)   
 [관리 코드 품질 분석](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)   
 [규칙 집합을 사용하여 코드 분석 규칙 그룹화](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)