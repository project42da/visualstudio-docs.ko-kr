---
title: "관리 코드에 대한 코드 분석 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.projectpropertypages.codeanalysis"
helpviewer_keywords: 
  - "코드 분석, 관리 코드"
  - "관리 코드, 코드 분석"
ms.assetid: 12ec0dab-46a4-43d8-984a-440730ef37a9
caps.latest.revision: 35
caps.handback.revision: 35
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 관리 코드에 대한 코드 분석 개요
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

관리 코드에 대한 코드 분석에서는 관리되는 어셈블리를 분석하고, Microsoft .NET Framework 디자인 지침에 설정된 프로그래밍 및 디자인 규칙의 위반과 같은 어셈블리 관련 정보를 보고합니다.  
  
 분석 도구는 분석하는 동안 수행하는 검사를 경고 메시지로 나타냅니다.  경고 메시지는 관련 프로그래밍 및 디자인 문제를 식별하며 가능한 경우 문제 해결 방법에 대한 정보를 제공합니다.  
  
## IDE\(통합 개발 환경\) 통합  
 개발자는 프로젝트에 대한 코드 분석을 자동으로 실행하거나 수동으로 실행할 수 있습니다.  
  
 프로젝트를 빌드할 때마다 코드 분석을 실행하려면 프로젝트의 속성 페이지에서 **빌드에 코드 분석 사용\(CODE\_ANALYSIS 상수 정의\)**을 선택합니다.  자세한 내용은 [방법: 자동 코드 분석 사용 설정 및 해제](../Topic/How%20to:%20Enable%20and%20Disable%20Automatic%20Code%20Analysis%20for%20Managed%20Code.md)을 참조하십시오.  
  
 프로젝트에 대해 수동으로 코드 분석을 실행하려면 **분석** 메뉴에서 *ProjectName***에 대해 코드 분석 실행**을 클릭합니다.  자세한 내용은 [방법: 자동 코드 분석 사용 설정 및 해제](../Topic/How%20to:%20Enable%20and%20Disable%20Automatic%20Code%20Analysis%20for%20Managed%20Code.md)을 참조하십시오.  
  
## 규칙 집합  
 관리 코드에 대한 코드 분석 규칙은 *규칙 집합*으로 그룹화됩니다.  Microsoft 표준 규칙 집합 중 하나를 사용하거나, 특정 요구 사항에 맞게 사용자 지정 규칙 집합을 만들 수 있습니다.  자세한 내용은 [규칙 집합을 사용하여 코드 분석 규칙 그룹화](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)을 참조하십시오.  
  
## ISS  
 경고가 적용되지 않는 것으로 표시하면 유용한 경우가 많습니다.  이렇게 하면 경고를 조사한 다음 이를 표시하지 않거나 무시하도록 설정했다는 것을 개발자와 나중에 이 코드를 검토할 수 있는 다른 사람에게 알릴 수 있습니다.  
  
 경고 ISS는 사용자 지정 특성을 통해 구현됩니다.  경고를 표시하지 않으려면 다음 예제와 같이 소스 코드에 `SuppressMessage` 특성을 추가합니다.  
  
 `[System.Diagnosis.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]`  
  
 `Public class MyClass`  
  
 `{`  
  
 `// code`  
  
 `}`  
  
 자세한 내용은 [SuppressMessage 특성을 사용하여 경고 표시 안 함](../code-quality/suppress-warnings-by-using-the-suppressmessage-attribute.md)을 참조하십시오.  
  
## 체크 인 정책의 일부로 코드 분석 실행  
 조직에서 반드시 특정 정책에 따라 체크 인을 수행하려는 경우  특히 다음 정책을 따르는지 확인할 수 있습니다.  
  
-   체크 인할 코드에 빌드 오류가 없습니다.  
  
-   최신 빌드의 일부로 코드 분석을 실행합니다.  
  
 체크 인 정책을 지정하여 위 사항을 확인할 수 있습니다.  자세한 내용은 [팀 프로젝트 체크 인 정책을 사용하여 코드 품질 향상](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)을 참조하십시오.  
  
## 팀 빌드 통합  
 빌드 시스템의 통합된 기능을 사용하여 빌드 프로세스의 일부로 분석 도구를 실행할 수 있습니다.  자세한 내용은 [응용 프로그램 빌드](../Topic/Build%20the%20application.md)을 참조하십시오.  
  
## 참고 항목  
 [규칙 집합을 사용하여 코드 분석 규칙 그룹화](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)   
 [방법: 자동 코드 분석 사용 설정 및 해제](../Topic/How%20to:%20Enable%20and%20Disable%20Automatic%20Code%20Analysis%20for%20Managed%20Code.md)