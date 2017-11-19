---
title: "기본 명령, 그룹 및 도구 모음 배치 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands [Visual Studio], default groups
- toolbars [Visual Studio], default
- commands [Visual Studio], default editor
- command groups
- commands [Visual Studio], default IDE
- commands [Visual Studio], default product
ms.assetid: 35342110-d639-4577-8367-00b21dcc6f07
caps.latest.revision: "30"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c5f1ec42408e4fd7d33d9445ae09252fae8d03db
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="default-command-group-and-toolbar-placement"></a>기본 명령, 그룹 및 도구 모음 배치
제품 통일성 및 안정성에 대 한 UI 기본적으로 특정 명령 그룹을 표시 하 고 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령과 명령 그룹에 대 한 정의 제공 합니다. 표준 명령 및 명령 그룹 Vspackage를 사용할 수도 있습니다.  
  
 기본 명령 그룹은 다음 세 가지 범주로: IDE 명령, 제품 명령 및 편집기 명령입니다.  
  
## <a name="default-ide-commands"></a>기본 IDE 명령  
 기본 IDE 도구 모음에 포함 된 모든 제품에서 공유 하는 명령이 포함 되어 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 와 같은 일반 프로젝트 작업에 관한 명령이 여기에 **저장** 명령 및 **항목 추가** 명령입니다. Vspackage 추가 하거나 예외적으로이 도구 모음에서 뺄 해야 하지: 제품 또는 VSPackage는 새 도구 창을 추가 하는 경우에 사용 가능한 도구 창의 목록에 추가할 해야 창 고 **보기** 메뉴. 새로운 제품 또는 Vspackage가 자신의 도구 모음을 추가할 수 있습니다.  
  
## <a name="default-product-commands"></a>기본 제품 명령  
 각 제품에는 중요 한 포함 된 자주 사용 되는 명령을 자체 기본 도구 모음을 사용 하 여 IDE를 제공할 수 있습니다. 그러나 기존 메뉴와 가능한 경우 도구 모음을 사용 하 고 필요에 따라 다른 작업 관련 도구 모음으로 보완 하는 것이 좋습니다 합니다.  
  
 도구 모음에 대 한 우선 순위 필드의 행 위치를 결정합니다. 우선 순위 0에서는 도구 모음 메뉴 모음 아래에 세 번째 행 (행 3)에 (1 행) 및 **표준** 도구 모음 (행 2). 따라서 다른 도구 모음으로 행에 표시 (우선 순위 + 3). 다음 도구 모음; 공간이 있는 경우 같은 행에 배치 됩니다. 그렇지 않은 경우 다음 행으로은 자동으로 이동 됩니다.  
  
## <a name="default-editor-commands"></a>기본 편집기 명령  
 사용자 지정 편집기를 제공 하는 VSPackage를 포함 하는 가장 중요 한 고 해당 편집기에서 자주 사용 하는 명령을 기본 도구 모음을 제공 해야 합니다. 편집기 도구 모음 편집기가 활성 상태일 때 편집기가 활성화 숨겨야 때 표시 됩니다. 이 표시 유형이 제어 되는 `VisibilityConstraints Element` .vsct 파일의 합니다.  
  
 제품 및 IDE의 도구 모음 아래 편집기 도구 모음을 배치 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDE 정의 명령, 메뉴 및 그룹](../../extensibility/internals/ide-defined-commands-menus-and-groups.md)   
 [VSPackage에서 사용자 인터페이스 요소를 추가하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)