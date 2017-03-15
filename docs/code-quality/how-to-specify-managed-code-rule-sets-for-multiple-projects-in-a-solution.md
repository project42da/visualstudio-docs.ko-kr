---
title: "방법: 솔루션의 여러 프로젝트에 대한 관리 코드 규칙 집합 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.codeanalysis.propertypages.solution"
ms.assetid: 92dc3250-a010-4396-b515-f03a0b30cd2a
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 솔루션의 여러 프로젝트에 대한 관리 코드 규칙 집합 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

기본적으로 솔루션의 관리되는 모든 프로젝트에는 Microsoft 최소 권장 규칙 코드 분석 *규칙 집합*이 지정됩니다.  솔루션의 속성 대화 상자에서 솔루션의 프로젝트에 지정된 규칙 집합을 변경할 수 있습니다.  
  
> [!NOTE]
>  기본적으로 프로젝트 코드 분석은 빌드 단계로 실행되지 않습니다.  코드 분석을 빌드 단계로 사용하도록 설정하려면 [방법: 관리 코드 프로젝트에 대한 코드 분석 구성](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)을 참조하십시오.  
  
### 관리되는 코드 솔루션의 여러 프로젝트에 대한 규칙 집합을 지정하려면  
  
1.  [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)]에서  [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], 또는 [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]에서 솔루션을 엽니다.  
  
2.  **분석** 메뉴에서 **솔루션의 코드 분석 구성**을 클릭합니다.  
  
3.  필요한 경우 **공용 속성**을 확장하고 **코드 분석 설정**을 클릭합니다.  
  
4.  하나 이상의 프로젝트에 대한 규칙 집합을 지정할 수 있습니다.  
  
    -   개별 프로젝트에 대한 규칙 집합을 지정하려면 프로젝트 이름을 클릭합니다.  
  
    -   여러 프로젝트에 대한 규칙 집합을 지정하려면 Ctrl 키를 누른 상태로 프로젝트 이름을 클릭합니다.  
  
    -   솔루션의 모든 프로젝트를 지정하려면 Shift 키를 누른 상태로 프로젝트 목록을 클릭합니다.  
  
5.  프로젝트의 **규칙 집합** 필드를 클릭하고 적용할 규칙 집합의 이름을 클릭합니다.