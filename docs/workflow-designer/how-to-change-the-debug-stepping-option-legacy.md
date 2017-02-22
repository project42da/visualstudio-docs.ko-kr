---
title: "방법: 단계별 디버깅 옵션 변경(레거시) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "분기 단계별 실행"
  - "워크플로 디버깅, 단계별 옵션"
  - "디버깅, 단계별 옵션"
  - "인스턴스 단계별 실행"
  - "한 단계씩 실행, 옵션 변경"
ms.assetid: aedc06af-d58a-44d6-aee4-f397f1f923a0
caps.latest.revision: 5
caps.handback.revision: 5
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# 방법: 단계별 디버깅 옵션 변경(레거시)
이 항목에서는 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]에서 동시 동작이 있는 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 응용 프로그램의 단계별 디버깅 옵션을 변경하는 방법에 대해 설명합니다.레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.  
  
 **ParallelActivity** 또는 **ConditionedActivityGroup**과 같이 동시에 실행되는 레거시 활동을 디버깅할 때 두 옵션 중 하나를 사용하여 코드를 단계별로 실행할 수 있습니다.  
  
 레거시 워크플로 프로젝트에서 단계별 디버깅 옵션을 변경하려면 다음 단계를 따르십시오.  
  
## 절차  
  
#### 단계별 디버깅 옵션을 변경하려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  기존 레거시 워크플로 프로젝트를 열거나 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 하며 동시 활동을 사용하는 새 프로젝트를 만듭니다.  
  
3.  레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 **워크플로** 메뉴에서 **디버그**를 가리킨 다음 **단계별 옵션**을 가리킵니다.  
  
4.  **인스턴스** 또는 **분기**를 선택합니다.  
  
## 참고 항목  
 [레거시 워크플로 디버깅](../workflow-designer/debugging-legacy-workflows.md)   
 [단계별 디버깅 옵션\(레거시\)](../workflow-designer/debug-stepping-options-legacy.md)