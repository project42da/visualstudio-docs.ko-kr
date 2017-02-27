---
title: "코드 분석 규칙 집합 참조 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "코드 분석, 규칙 집합"
ms.assetid: 5874e854-e298-4d2e-bbe4-95e899d22587
caps.latest.revision: 43
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 43
---
# 코드 분석 규칙 집합 참조
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], 또는 [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]에서 관리 코드 프로젝트에 대한 코드 분석을 할때는 기본 제공 *규칙 집합* 목록이 제공됩니다.  표준 규칙 집합 중 하나를 사용 하거나 또는 프로젝트 요구 사항에 맞게 규칙을 사용자 지정할 수 있습니다.  
  
## 사용 가능한 규칙 집합  
 아래의 표는 기본 규칙 집합을 제공합니다.  
  
|||  
|-|-|  
|[모든 규칙 규칙 집합](../code-quality/all-rules-rule-set.md)|이 규칙 집합에는 모든 규칙이 포함되어 있습니다.  이 규칙 집합을 실행하면 많은 수의 경고가 보고될 수 있습니다.  이 규칙 집합을 사용하여 코드에 있는 모든 문제의 포괄적인 그림을 가져오십시오.  이렇게 하면 프로젝트에 대해 실행하기에 가장 적합한 보다 중점적인 규칙 집합을 판단하는 데 도움이 됩니다.|  
|[관리 코드에 대한 기본 수정 규칙 규칙 집합](../code-quality/basic-correctness-rules-rule-set-for-managed-code.md)|이러한 규칙은 프레임워크 API 사용 중 발생하는 논리 오류 및 일반적인 실수에 초점을 맞춥니다.  최소 권장 규칙에서 보고되는 경고 목록을 확장하려면 이 규칙 집합을 포함하십시오.|  
|[관리 코드에 대한 기본 디자인 지침 규칙 규칙 집합](../code-quality/basic-design-guideline-rules-rule-set-for-managed-code.md)|이러한 규칙은 유용한 정보를 적용하여 코드를 이해하고 사용하기 쉽게 만드는 데 초점을 맞춥니다.  프로젝트에 라이브러리 코드가 있거나 코드를 쉽게 유지 관리하기 위해 유용한 정보를 적용하려는 경우 이 규칙 집합을 포함하십시오.|  
|[관리 코드에 대한 확장 수정 규칙 규칙 집합](../code-quality/extended-correctness-rules-rule-set-for-managed-code.md)|이러한 규칙은 기본 수정 규칙을 확장하여 보고되는 논리 및 프레임워크 사용 오류를 최대화합니다.  COM Interop 및 모바일 응용 프로그램 같은 특정 시나리오에 강조 사항이 추가됩니다.  이러한 시나리오 중 하나가 프로젝트에 적용되거나 프로젝트에서 추가 문제를 찾으려는 경우 이 규칙 집합을 포함해 보십시오.|  
|[관리 코드에 대한 확장 디자인 지침 규칙 규칙 집합](../code-quality/extended-design-guidelines-rules-rule-set-for-managed-code.md)|이러한 규칙은 기본 디자인 지침 규칙을 확장하여 보고되는 유용성 및 유지 관리 문제를 최대화합니다.  명명 지침에 주안점을 둡니다.  프로젝트에 라이브러리 코드가 있거나 유지 관리 가능한 코드를 작성하는 데 가장 높은 표준을 적용하려는 경우 이 규칙 집합을 포함해 보십시오.|  
|[관리 코드에 대한 전역화 규칙 규칙 집합](../code-quality/globalization-rules-rule-set-for-managed-code.md)|이러한 규칙은 응용 프로그램의 데이터가 다른 언어, 로캘 및 문화권에서 사용될 때 올바로 표시되지 않는 문제에 초점을 맞춥니다.  응용 프로그램이 지역화되거나 전역화되는 경우 이 규칙 집합을 포함하십시오.|  
|[관리 코드에 대한 관리 최소 규칙 규칙 집합](../code-quality/managed-minimun-rules-rule-set-for-managed-code.md)|이러한 규칙은 코드 분석에서 가장 정확하게 확인하는 코드의 가장 중요한 문제에 초점을 맞춥니다.  이러한 규칙은 수가 적으며 제한된 Visual Studio 버전에서만 실행할 수 있습니다.  다른 Visual Studio 버전에서는 MinimumRecommendedRules.ruleset을 사용하십시오.|  
|[관리 코드에 대한 관리 권장 규칙 규칙 집합](../code-quality/managed-recommended-rules-rule-set-for-managed-code.md)|이러한 규칙은 잠재적 보안 허점, 응용 프로그램 충돌 및 기타 중요한 논리 및 디자인 오류를 포함한 코드의 가장 중요한 문제에 초점을 맞춥니다.  프로젝트에 대해 만드는 모든 사용자 지정 규칙 집합에 이 규칙 집합을 포함해야 합니다.|  
|[혼합 최소 규칙 규칙 집합](../code-quality/mixed-minimum-rules-rule-set.md)|이러한 규칙은 잠재적 보안 허점 및 응용 프로그램 충돌을 포함하여 공용 언어 런타임을 지원하는 C\+\+ 프로젝트의 가장 중요한 문제에 초점을 맞춥니다.  공용 언어 런타임을 지원하는 C\+\+ 프로젝트에 대해 만드는 모든 사용자 지정 규칙 집합에 이 규칙 집합을 포함해야 합니다.|  
|[혼합 권장 규칙 규칙 집합](../code-quality/mixed-recommended-rules-rule-set.md)|이러한 규칙은 잠재적 보안 허점, 응용 프로그램 충돌 및 기타 중요한 논리 및 디자인 오류를 포함하여 공용 언어 런타임을 지원하는 C\+\+ 프로젝트의 가장 일반적으로 중요한 문제에 초점을 맞춥니다.  공용 언어 런타임을 지원하는 C\+\+ 프로젝트에 대해 만드는 모든 사용자 지정 규칙 집합에 이 규칙 집합을 포함해야 합니다.  이 규칙 집합은 Visual Studio Professional 이상 버전에서 구성하도록 디자인되었습니다.|  
|[네이티브 최소 규칙 규칙 집합](../code-quality/native-minimum-rules-rule-set.md)|이러한 규칙은 잠재적 보안 허점 및 응용 프로그램 충돌을 포함하여 네이티브 코드의 가장 중요한 문제에 초점을 맞춥니다.  네이티브 프로젝트에 대해 만드는 모든 사용자 지정 규칙 집합에 이 규칙 집합을 포함해야 합니다.|  
|[네이티브 권장 규칙 규칙 집합](../code-quality/native-recommended-rules-rule-set.md)|이러한 규칙은 잠재적 보안 허점 및 응용 프로그램 충돌을 포함하여 네이티브 코드의 가장 중요하고 일반적인 문제에 초점을 맞춥니다.  네이티브 프로젝트에 대해 만드는 모든 사용자 지정 규칙 집합에 이 규칙 집합을 포함해야 합니다.  이 규칙 집합은 Visual Studio Professional 이상 버전에서 사용하도록 디자인되었습니다.|  
|[관리 코드에 대한 보안 규칙 규칙 집합](../code-quality/security-rules-rule-set-for-managed-code.md)|이 규칙 집합에는 모든 Microsoft 보안 규칙이 포함되어 있습니다.  보고되는 잠재적 보안 문제의 수를 최대화하려면 이 규칙 집합을 포함하십시오.|