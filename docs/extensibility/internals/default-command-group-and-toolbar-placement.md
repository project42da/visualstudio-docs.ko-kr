---
title: "기본 명령, 그룹 및 도구 모음 배치 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "기본 그룹 명령 [Visual Studio]"
  - "도구 모음 [Visual Studio] 기본값"
  - "기본 편집기 명령 [Visual Studio]"
  - "명령 그룹"
  - "기본 IDE 명령 [Visual Studio]"
  - "기본 제품 명령 [Visual Studio]"
ms.assetid: 35342110-d639-4577-8367-00b21dcc6f07
caps.latest.revision: 30
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 30
---
# 기본 명령, 그룹 및 도구 모음 배치
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

제품 일관성 및 안정성에 대 한 UI 기본적으로 특정 명령 그룹을 표시 하 고 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령과 명령 그룹에 대 한 정의 제공 합니다. Vspackage 표준 명령 및 명령 그룹에도 사용할 수 있습니다.  
  
 기본 명령 그룹은 세 가지 범주로 구분: IDE 명령과 제품 명령, 편집기 명령입니다.  
  
## 기본 IDE 명령  
 기본 IDE 도구 모음에 포함 된 모든 제품에서 공유 하는 명령이 포함 되어 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 여기에 같은 일반 프로젝트 작업에 관한 명령이 포함 된 **저장** 명령 및 **항목 추가** 명령입니다. Vspackage를 추가 하지 않거나 예외적으로이 도구 모음에서 뺄 해야: 제품 또는 VSPackage 새 도구 창을 추가 하는 경우 창에 추가할 사용 가능한 도구 창의 목록에는 **보기** 메뉴. 새 제품 또는 Vspackage 자신의 도구 모음을 추가할 수 있습니다.  
  
## 기본 제품 명령  
 각 제품에는 자체 기본 도구 모음 포함 하는 것이 중요 고 자주 사용 되는 명령을 사용 하 여 IDE를 제공할 수 있습니다. 그러나 기존 메뉴 및 가능한 경우 도구 모음을 사용 하 고 필요에 따라 다른 작업 관련 도구 모음과 보완 하는 것이 좋습니다 합니다.  
  
 도구 모음에 대 한 우선 순위 필드의 행 위치를 결정합니다. 우선 순위 0에서는 도구 모음 메뉴 모음 아래에 세 번째 행 \(행 3\)에 \(1 행\)와 **표준** 도구 모음 \(행 2\). 따라서 다른 도구 모음으로 행에 표시 \(될 수 있습니다 우선 순위 \+ 3\). 공간이; 있으면 다음 도구 모음 같은 행에 배치 됩니다. 그렇지 않으면 다음 행으로 이동 자동으로 됩니다.  
  
## 기본 편집기 명령  
 VSPackage 사용자 지정 편집기를 제공 하는 가장 중요 한 포함 된 해당 편집기에서 자주 사용 하는 명령을 기본 도구 모음을 제공 해야 합니다. 편집기 도구 모음 편집기가 활성 상태일 때 편집기가 활성화 숨겨야 때 표시 됩니다. 이러한 가시성 제어 되는 `VisibilityConstraints Element` .vsct 파일입니다.  
  
 편집기 도구 모음 IDE 및 제품 도구 모음 아래 배치 되어야 합니다.  
  
## 참고 항목  
 [IDE 정의 명령, 메뉴 및 그룹](../../extensibility/internals/ide-defined-commands-menus-and-groups.md)   
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)