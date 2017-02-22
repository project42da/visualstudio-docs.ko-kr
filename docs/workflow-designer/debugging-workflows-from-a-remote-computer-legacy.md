---
title: "원격 컴퓨터에서 워크플로 디버깅(레거시) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "워크플로 디버깅, 원격"
  - "디버깅, 원격"
  - "원격 디버깅, 워크플로"
  - "워크플로, 원격 디버깅"
ms.assetid: 44eaec8f-9959-4ae7-a374-670946f933c1
caps.latest.revision: 6
caps.handback.revision: 6
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# 원격 컴퓨터에서 워크플로 디버깅(레거시)
이 항목에서는 레거시 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]를 사용하여 빌드된 원격 레거시 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 응용 프로그램을 디버깅하는 방법에 대해 설명합니다.레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 응용 프로그램이 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.  
  
 [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)]을 설치할 때 구성 요소 설치 옵션 중 하나로 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]용 [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] 디버거를 설치할 수 있습니다.그러면 원격 디버깅 구성 요소가 설치됩니다.이 원격 디버깅 구성 요소는 원격 워크플로 디버깅의 대상 컴퓨터에 설치해야 합니다.  
  
 또한 디버깅을 수행하는 데 사용되는 로컬 컴퓨터의 GAC\(전역 어셈블리 캐시\)에 원격 컴퓨터에서 디버깅할 레거시 워크플로의 워크플로 정의가 포함된 어셈블리를 설치해야 합니다.예를 들어 레거시 워크플로가 원격 컴퓨터 A에서 실행 중이고 로컬 컴퓨터 B에서 디버깅 중인 경우 워크플로 정의는 컴퓨터 B의 GAC에 있어야 합니다.이렇게 하면 디자이너는 컴퓨터 A에서 원격으로 실행되는 워크플로의 워크플로 마크업을 deserialize하고 컴퓨터 B에 표시할 수 있습니다.글로벌 어셈블리 캐시에 대한 자세한 내용은 MSDN Library를 참조하십시오.  
  
 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] 원격 디버깅은 다른 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 구성 요소의 원격 디버깅과 동일하게 작동합니다.자세한 내용은 MSDN Library에서 [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] 원격 디버깅을 참조하십시오.  
  
## 참고 항목  
 [레거시 워크플로 디버깅](../workflow-designer/debugging-legacy-workflows.md)