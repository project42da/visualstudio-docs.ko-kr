---
title: "방법: 단계별 디버깅 옵션 (레거시) 변경 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- branch stepping
- debugging, stepping options
- debugging workflows, stepping options
- stepping, changing options
- instance stepping
ms.assetid: aedc06af-d58a-44d6-aee4-f397f1f923a0
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: ff11186c82102230ec939c0c9b1c5aba69df7f3f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-change-the-debug-stepping-option-legacy"></a>방법: 단계별 디버깅 옵션 변경(레거시)
이 항목에서는 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]에서 동시 동작이 있는 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] 응용 프로그램의 단계별 디버깅 옵션을 변경하는 방법에 대해 설명합니다. 레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.  
  
 와 같은 동시에 실행 되는 레거시 활동을 디버깅할 때 **ParallelActivity** 또는 **ConditionedActivityGroup**, 두 옵션 중 하나를 사용 하 여 코드를 단계별로 실행할 수 있습니다.  
  
 레거시 워크플로 프로젝트에서 단계별 디버깅 옵션을 변경하려면 다음 단계를 따르세요.  
  
## <a name="procedures"></a>절차  
  
#### <a name="to-change-the-debug-stepping-option"></a>디버그 단계별 옵션을 변경하려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  기존 레거시 워크플로 프로젝트를 열거나 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 하며 동시 활동을 사용하는 새 프로젝트를 만듭니다.  
  
3.  에 **워크플로** 레거시의 메뉴 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], 가리킨 **디버그**를 차례로 **단계별 실행 옵션**합니다.  
  
4.  선택 **인스턴스** 또는 **분기**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레거시 워크플로 디버깅](../workflow-designer/debugging-legacy-workflows.md)   
 [단계별 디버깅 옵션(레거시)](../workflow-designer/debug-stepping-options-legacy.md)