---
title: "방법: ASP.NET 웹 응용 프로그램에 대한 코드 분석 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.codeanalysis.propertypages.asp"
ms.assetid: b3000b31-fd9d-489e-81a2-a4bee49453ba
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: ASP.NET 웹 응용 프로그램에 대한 코드 분석 구성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] 및 [!INCLUDE[vsUltShort](../code-quality/includes/vsultshort_md.md)]에서는 코드 분석 *규칙 집합* 목록의 규칙 집합 중 하나를 선택하여 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램에 적용할 수 있습니다.  기본 규칙 집합은 Microsoft 최소 권장 규칙입니다.  다른 규칙 집합을 선택하여 웹 사이트에 적용할 수도 있습니다.  
  
### ASP.NET 페이지 프레임워크 프로젝트에 대한 규칙 집합을 구성하려면  
  
1.  **솔루션 탐색기**에서 웹 사이트를 선택합니다.  
  
2.  **분석** 메뉴에서 웹 사이트에 대한 **코드 분석 구성**을 클릭합니다.  
  
3.  프로젝트가 둘 이상 포함된 솔루션을 선택한 경우 **구성** 및 **플랫폼** 목록에서 빌드 구성과 대상 운영 체제를 선택합니다.  
  
4.  솔루션의 각 프로젝트에 대해 **규칙 집합** 열을 클릭하고 실행할 규칙 집합의 이름을 클릭합니다.  
  
5.  기본적으로 코드 분석은 솔루션의 모든 프로젝트에 대해 실행됩니다.  특정 프로젝트에 코드 분석을 사용하거나 사용하지 않도록 설정하려면 다음 단계를 수행합니다.  
  
    1.  프로젝트 이름을 마우스 오른쪽 단추로 클릭한 다음 속성을 클릭합니다.  
  
    2.  **코드 분석 사용** 확인란을 선택하거나 선택 취소합니다.  **분석** 메뉴에서 **웹 사이트에 코드 분석 실행**을 클릭하여 코드 분석을 수동으로 실행할 수도 있습니다.  
  
6.  **이 규칙 집합 실행** 드롭다운 목록에서 다음 단계를 수행합니다.  
  
    -   사용할 규칙 집합을 선택합니다.  
  
    -   **\<브라우저\>** 를 선택하여 목록에 없는 기존 사용자 지정 규칙 집합을 지정합니다.  
  
    -   사용자 지정 규칙 집합을 정의합니다.  자세한 내용은 [사용자 지정 규칙 집합 만들기](../code-quality/creating-custom-code-analysis-rule-sets.md)을 참조하십시오.