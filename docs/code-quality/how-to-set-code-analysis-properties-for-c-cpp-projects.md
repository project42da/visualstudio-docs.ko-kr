---
title: "방법: C/c + + 프로젝트에 대 한 코드 분석 속성 설정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codeanalysis.propertypages.native
- VC.Project.VCCLCompilerTool.EnablePrefast
- VC.Project.VCFxCopTool.EnablePREfast
- VC.Project.VCFxCopTool.IgnoreGeneratedCode
helpviewer_keywords:
- properties, C/C++ Code Analysis
- properties, Code Analysis
- code analysis properties
- C/C++ code analysis properties
ms.assetid: 7af52097-6d44-4785-9b9f-43b7a7d447d7
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b2ad22eccb561bf58ee845d58268620aad778a20
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="how-to-set-code-analysis-properties-for-cc-projects"></a>방법: C/C++ 프로젝트의 코드 분석 속성 설정
코드 분석 도구는 프로젝트의 각 구성에 대 한 코드 분석을 사용 하 여 규칙을 구성할 수 있습니다. 또한를 생성 하거나 타사 도구를 통해 프로젝트에 추가 하는 코드에서 발생 한 경고를 표시 하지 않는 코드 분석을 유도할 수 있습니다.  
  
## <a name="code-analysis-property-page"></a>코드 분석 속성 페이지  
 **코드 분석** 속성 페이지에는 프로젝트에 대 한 모든 코드 분석 구성 설정이 포함 되어 있습니다. 프로젝트의 코드 분석 속성 페이지를 열려면 **솔루션 탐색기**, 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다. 다음으로 확장 하 고 **구성 속성** 선택 하 고는 **코드 분석** 탭 합니다.  
  
## <a name="project-configuration-and-platform"></a>프로젝트 구성 및 플랫폼  
 **구성** 목록 및 **플랫폼** 다양 한 프로젝트 구성 및 플랫폼 조합에 서로 다른 코드 분석 설정을 적용할 수 있습니다. 예를 들어 디버그에 대 한 프로젝트에 규칙의 집합을 적용 하는 코드 분석을 빌드하고 빌드 릴리스에 대 한 다른 집합을 지정할 수 있습니다.  
  
## <a name="enabling-code-analysis"></a>코드 분석 사용  
 선택 하 여 프로젝트에 대 한 코드 분석을 사용할지 여부를 결정할 수 있습니다 **코드 분석에 대 한 C/c + + 사용 빌드에**합니다. 와 함께에서 **구성** 목록 경우, 예를 들어 하도록 결정할 수 디버그 및 릴리스 빌드에 사용에 대 한 코드 분석을 사용 하지 않도록 설정 합니다.  
  
 프로젝트가 관리 코드를 포함 하는 경우를 선택 하 여 코드 분석을 사용할지 여부를 결정할 수 있습니다 **빌드에 코드 분석 사용**합니다.  
  
 코드 분석은 코드의 품질을 개선 하 고 일반적인 문제를 피할 수 있도록 설계 되었습니다. 따라서를 신중히 고려해 야 코드 분석의 비활성화 여부. 규칙 집합을 사용 하지 않도록 설정 하는 것이 좋습니다 하거나 원하지 않는 개별 규칙 프로젝트에 적용 합니다.  
  
## <a name="generated-code"></a>생성된 코드  
 자주 개발자는 도구를 사용 하 여 응용 프로그램을 신속 하 게 개발할 수 있도록 지원 합니다. 이러한 도구에는 프로젝트에 추가 된 코드를 생성할 수 있습니다. 코드 분석에서 생성 된 코드에서 검색 하는 규칙 위반 보려는 수 있습니다. 그러나 코드를 유지 관리 하지 않을 경우 참조 하지 않을 수 있습니다.  
  
 **생성 된 코드 결과 표시 안 함** 확인란은 **일반** 속성 페이지-타사 도구에서 생성 되는 관리 코드에서 코드 분석 경고를 표시 하려는 여부를 선택할 수 있습니다 .  
  
## <a name="rule-sets"></a>규칙 집합  
 프로젝트가 관리 코드를 포함 하는 경우 코드 분석에서에서 규칙 집합을 선택 하 여 적용할 규칙을 선택할 수 있습니다는 **이 규칙 집합 실행** 목록입니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리 코드 품질 분석](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)   
 [C/C++용 코드 분석 경고](../code-quality/code-analysis-for-c-cpp-warnings.md)