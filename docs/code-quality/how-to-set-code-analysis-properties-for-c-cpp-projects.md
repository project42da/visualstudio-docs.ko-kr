---
title: "방법: C/C++ 프로젝트의 코드 분석 속성 설정 | Microsoft Docs"
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
  - "vs.codeanalysis.propertypages.native"
  - "VC.Project.VCCLCompilerTool.EnablePrefast"
  - "VC.Project.VCFxCopTool.EnablePREfast"
  - "VC.Project.VCFxCopTool.IgnoreGeneratedCode"
helpviewer_keywords: 
  - "C/C++ 코드 분석 속성"
  - "코드 분석 속성"
  - "속성, C/C++ 코드 분석"
  - "속성, 코드 분석"
ms.assetid: 7af52097-6d44-4785-9b9f-43b7a7d447d7
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 방법: C/C++ 프로젝트의 코드 분석 속성 설정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

코드 분석 도구에서 프로젝트의 각 구성에 있는 코드를 분석하는 데 사용하는 규칙을 구성할 수 있습니다.  또한 타사 도구를 사용하여 프로젝트에 생성하거나 추가한 코드의 경고를 코드 분석에서 무시하도록 할 수도 있습니다.  
  
## 코드 분석 속성 페이지  
 **코드 분석** 속성 페이지에는 프로젝트에 대한 모든 코드 분석 구성 설정이 포함되어 있습니다.  **솔루션 탐색기**에서 프로젝트의 코드 분석 속성 페이지를 열려면 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  그런 다음 **구성 속성**을 확장하고 **코드 분석** 탭을 선택합니다.  
  
## 프로젝트 구성 및 플랫폼  
 **구성** 목록 및 **플랫폼** 목록을 사용하면 프로젝트 구성 및 플랫폼 조합에 따라 각기 다른 코드 분석 설정을 적용할 수 있습니다.  예를 들어 코드 분석에서 프로젝트에 디버그 빌드용으로 하나의 규칙 집합을 적용하고 릴리스 빌드용으로는 다른 규칙 집합을 적용하도록 할 수 있습니다.  
  
## 코드 분석 사용  
 **빌드할 때 C\/C\+\+에 코드 분석 사용**을 선택하여 프로젝트에 코드 분석을 사용할지 여부를 결정할 수 있습니다.  **구성** 목록과 함께 사용할 경우, 예를 들면 디버그 빌드에는 코드 분석을 사용하지 않고 릴리스 빌드에는 코드 분석을 사용하도록 결정할 수 있습니다.  
  
 프로젝트에 관리 코드가 들어 있는 경우에는 **빌드에 코드 분석 사용**을 선택하여 코드 분석을 사용할지 여부를 결정할 수 있습니다.  
  
 코드 분석은 코드 품질을 향상시키고 일반적으로 발생할 수 있는 실수를 방지하기 위해 만들어졌습니다.  그러므로 코드 분석을 사용하지 않을지 여부는 신중히 결정해야 합니다.  일반적으로 프로젝트에 적용하지 않을 규칙 집합이나 개별 규칙은 사용하지 않는 것이 더 좋습니다.  
  
## 생성된 코드  
 개발자는 응용 프로그램을 빠르게 개발하기 위해 도구를 사용하는 경우가 많습니다.  이러한 도구를 통해 프로젝트에 추가되는 코드가 생성될 수 있습니다.  생성된 코드에서 코드 분석을 통해 발견한 규칙 위반 내용을 확인할 수 있지만  코드를 유지 관리하지 않으려는 경우에는 이러한 내용을 확인하지 않을 수도 있습니다.  
  
 **일반** 속성 페이지의 **생성된 코드 결과 표시 안 함** 확인란을 사용하여 타사 도구에서 생성된 관리 코드의 코드 분석 경고를 표시할지 여부를 선택할 수 있습니다.  
  
## 규칙 집합  
 프로젝트에 관리 코드가 들어 있는 경우 **이 규칙 집합 실행** 목록에서 규칙 집합을 선택하여 코드 분석 시 적용할 규칙을 선택할 수 있습니다.  
  
## 참고 항목  
 [관리 코드 품질 분석](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)   
 [C\/C\+\+용 코드 분석 경고](../code-quality/code-analysis-for-c-cpp-warnings.md)