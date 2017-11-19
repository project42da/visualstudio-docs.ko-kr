---
title: "원격 컴퓨터 (레거시)에서 워크플로 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- workflows, debugging remotely
- debugging workflows, remotely
- remote debugging, workflows
- debugging, remote
ms.assetid: 44eaec8f-9959-4ae7-a374-670946f933c1
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: f6b1f88fcc796cbee0a48fd39da2ad9c4fe1489a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="debugging-workflows-from-a-remote-computer-legacy"></a>원격 컴퓨터에서 워크플로 디버깅(레거시)
이 항목에서는 레거시 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]를 사용하여 빌드된 원격 레거시 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] 응용 프로그램을 디버깅하는 방법에 대해 설명합니다. 레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 응용 프로그램이 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.  
  
 설치 하는 경우 [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)], 구성 요소 설치 옵션 중 하나를 설치 하는 것은 [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] 에 대 한 디버거 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]합니다. 원격 디버깅 구성 요소가 설치됩니다. 이 원격 디버깅 구성 요소는 원격 워크플로 디버깅의 대상 컴퓨터에 설치해야 합니다.  
  
 또한 디버깅을 수행하는 데 사용되는 로컬 컴퓨터의 GAC(전역 어셈블리 캐시)에 원격 컴퓨터에서 디버깅할 레거시 워크플로의 워크플로 정의가 포함된 어셈블리를 설치해야 합니다. 예를 들어 원격 컴퓨터 A에서 실행 중인 레거시 워크플로를 로컬 컴퓨터 B에서 디버깅하는 경우, 워크플로 정의가 컴퓨터 B의 GAC에 있어야 합니다. 그러면 디자이너가 원격 컴퓨터 A에서 실행 중인 워크플로의 워크플로 마크업을 deserialize하고 컴퓨터 B에 표시할 수 있습니다. 전역 어셈블리 캐시에 대한 자세한 내용은 MSDN Library를 참조하십시오.  
  
 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] 원격 디버깅은 다른 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 구성 요소의 원격 디버깅과 동일하게 작동합니다. 자세한 내용은 참조 [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] MSDN Library에서 원격 디버깅 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레거시 워크플로 디버깅](../workflow-designer/debugging-legacy-workflows.md)