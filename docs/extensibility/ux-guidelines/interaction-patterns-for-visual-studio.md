---
title: "Visual Studio에 대 한 상호 작용 패턴 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3643792-b0df-481c-bc35-576f948e04cf
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1e084ace914f65a9e97307f0a70d6c5e2211be55
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="interaction-patterns-for-visual-studio"></a>Visual Studio에 대 한 상호 작용 패턴
## <a name="overview"></a>개요  
 디자인 패턴에는 일반적으로 제약 조건의 비슷한 집합에서 문제를 해결 하려면 특정 상황에서 적용 될 수 있는 디자인의 핵심입니다. 기능 및 시스템 디자이너는 이러한 디자인 패턴을 사용 하 여 시작 점으로 특정 상황에 조정 될 수 있습니다.  
  
 Visual Studio의 새로운 기능을 작성할 때 고려해 야 하는 일반적인 상호 작용 패턴 라이브러리를 있습니다. 이 디자인 패턴에 대 한 두 가지 핵심 컨텍스트가: Visual Studio 클라이언트 (devenv) 및 Visual Studio Online 합니다. 몇 가지 디자인 문제에 대 한 모든 상황에서 잘 작동 하는 어디에서 나 패턴이 있습니다. 그러나 대부분의 경우에서 솔루션 다를 수 있습니다 하 고 클라이언트 응용 프로그램에서 호스트 되는 브라우저 내에서 제공 되는 UI에 대 한 합니다.  
  
### <a name="visual-studio-client-pattern-types"></a>Visual Studio 클라이언트 패턴 유형  
  
|패턴 유형|설명|예제|  
|------------------|-----------------|--------------|  
|**응용 프로그램 수준 패턴**|높은 수준의 패턴 결정 또는 응용 프로그램 컨텍스트를 표시 합니다. 그 안에서 복합 및 컨트롤 패턴을 포함 하 고 응용 프로그램에 공통적으로 적용|-도구 창<br />-문서 창|  
|**복합 패턴**|응용 프로그램 패턴에 걸쳐 있을 수 있는 일반적인 패턴 또는 고유한 구성에서 여러 컨트롤의 구성 인식 가능한 패턴|뷰 전환<br />-목록 작성기<br />-데이터를 표시합니다.<br />-알림<br />유효성 검사<br />모델 선택|  
|**컨트롤 패턴**|하위 수준 방법을 컨트롤에 대 한 구체적인 정보 동작 하 게 예상|-트리 뷰<br />-표 형태 컨트롤 내에서 편집합니다.|  
  
## <a name="application-patterns"></a>응용 프로그램 패턴  
 상위 수준에서 Visual Studio 인터페이스에는 여러 windows, 대화 상자, 명령 및 도구 모음 하나의 IDE 내에서 구성 됩니다. Visual Studio 계층 드라이브 및 상황에 맞는 메뉴를 결정합니다. IDE의 사용자 인터페이스에 주요 통합 점 모두가 문서 windows, 도구 창, 프로젝트, 명령 구조, 텍스트 편집기, 도구 상자, 속성 창 및 도구 > 옵션입니다.  
  
 각각의 IDE의 사용자 인터페이스에 주요 통합 지점에 대 한 기본 사용 패턴 가지가 있습니다.  
  
-   [Visual Studio의 메뉴 및 명령](../../extensibility/ux-guidelines/menus-and-commands-for-visual-studio.md)  
  
-   [Visual Studio의 응용 프로그램 패턴](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md)  
  
    -   [창 상호 작용](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_WindowInteractions)  
  
    -   [도구 창](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_ToolWindows)  
  
    -   [편집기 도움말 표기법](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_DocumentEditorConventions)  
  
    -   [대화 상자](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_Dialogs)  
  
    -   [프로젝트](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_Projects)  
  
## <a name="common-control-patterns"></a>컨트롤의 일반 패턴  
 컨트롤 패턴은 주로 개별 컨트롤에 대 한 동작을 예상 합니다. 일관성은 가장 중요 한 영역입니다.  
  
 Visual Studio에서 가장 일반적인 컨트롤 데스크톱 Windows 지침을 따르십시오. 지침은 Visual Studio 관련 상호 작용 또는 위치를 म 보다 우선 적용 되는 지침 완전히 Visual Studio의 정교한 사용자 요구 사항에 맞게 조정 하기 위해 사용 하는 일반적인 규칙을 추가할 필요는 영역을 포함 합니다.  
  
-   [Visual Studio의 일반 컨트롤 패턴](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md)  
  
    -   [공용 컨트롤](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_CommonControls)  
  
    -   [텍스트 컨트롤](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_TextControls)  
  
    -   [단추, 하이퍼링크](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_ButtonsAndHyperlinks)  
  
## <a name="composite-patterns"></a>복합 패턴  
 사용자가 작업을 수행 하는 방법의 여러 가지가 있습니다. 가능 하면 기능을 모두 상호 작용 및 시각적 디자인에 대 한 이러한 패턴을 사용 하도록 설계 되어야 합니다.  
  
 많은 복합 패턴의 가장 중요 한 일부 Visual Studio 내에서 중일 일관성에 대해 됩니다:  
  
-   [Visual Studio의 복합 패턴](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md)  
  
    -   [개체에 UI 및 보기](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_OnObjectUI)  
  
    -   [모델 선택](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_SelectionModels)  
  
    -   [지 속성 및 설정을 저장 하는](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_PersistenceAndSavingSettings)  
  
    -   [터치식 입력](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_TouchInput)