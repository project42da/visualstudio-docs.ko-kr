---
title: "Visual Studio에 대 한 상호 작용 패턴 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a3643792-b0df-481c-bc35-576f948e04cf
caps.latest.revision: 4
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 4
---
# Visual Studio에 대 한 상호 작용 패턴
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

## 개요  
 디자인 패턴에는 일반적으로 제약 조건 집합이 유사한 문제를 해결 하는 특정 상황에 적용할 수 있는 디자인의 핵심 이며 기능 및 시스템 디자이너 시작 자신의 특정 상황에 적용할 수 있는 지점으로 이러한 디자인 패턴을 사용 합니다.  
  
 Visual Studio의 새로운 기능을 작성할 때 고려해 야 하는 일반적인 상호 작용 패턴 라이브러리를 있습니다. 이 디자인 패턴에 대 한 두 가지 핵심 컨텍스트가: Visual Studio 클라이언트 \(devenv\) 및 Visual Studio Online 합니다. 몇 가지 디자인 문제에 대 한 모든 상황에서 잘 작동 하는 어디에서 나 패턴이 있습니다. 그러나 대부분의 경우에서 솔루션 다 수는 브라우저와 클라이언트 응용 프로그램에서 호스트 되는 내에서 제공 되는 UI에 대 한 합니다.  
  
### Visual Studio 클라이언트 패턴 형식  
  
|패턴 유형|설명|예제|  
|-----------|--------|--------|  
|**응용 프로그램 수준 패턴**|결정 또는 응용 프로그램 컨텍스트를 표시 하 고, 그 안에 포함 합성 및 컨트롤 패턴이 포함 된 응용 프로그램에 공통적으로 적용 되는 높은 수준의 패턴|-   도구 창<br />-   문서 창|  
|**복합 패턴**|응용 프로그램 패턴에 걸쳐 있을 수 있는 일반적인 패턴 또는 서로 다른 구성에서 여러 컨트롤의 구성 된 인식 가능한 패턴|-   뷰 전환<br />-   목록 작성기<br />-   데이터 표시<br />-   알림<br />-   유효성 검사<br />-   모델 선택|  
|**컨트롤 패턴**|에 대 한 구체적인 방법을 저수준 컨트롤에 대 한 동작으로 예상 됩니다.|-   트리 뷰<br />-   표 형태 컨트롤 내에서 편집|  
  
## 응용 프로그램 패턴  
 높은 수준에서는 Visual Studio 인터페이스는 여러 창, 대화 상자, 명령 및 단일 IDE에서 도구 모음을 구성합니다. Visual Studio 계층 드라이브 및 상황에 맞는 메뉴를 결정합니다. IDE의 주요 통합 지점 사용자 인터페이스에는 문서 windows, 도구 창, 프로젝트, 명령 구조, 텍스트 편집기, 도구 상자, 속성 창 및 도구 \> 옵션.  
  
 각각의 사용자 인터페이스에서 IDE의 주요 통합 지점에 대 한 기본 사용 패턴은  
  
-   [메뉴와 Visual Studio 명령](../../extensibility/ux-guidelines/menus-and-commands-for-visual-studio.md)  
  
-   [Visual Studio에 대 한 응용 프로그램 패턴](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md)  
  
    -   [창 상호 작용](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_WindowInteractions)  
  
    -   [도구 창](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_ToolWindows)  
  
    -   [편집기 도움말 표기법](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_DocumentEditorConventions)  
  
    -   [대화 상자](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_Dialogs)  
  
    -   [프로젝트](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_Projects)  
  
## 공용 컨트롤 패턴  
 컨트롤 패턴은 주로 개별 컨트롤에 대 한 동작 예상 됩니다. 일관성의 가장 중요 한 영역입니다.  
  
 Visual Studio에서 가장 일반적인 컨트롤 데스크톱 Windows 지침을 따르십시오. 지침 해야 Visual Studio 관련 상호 작용 또는 위치는 우리 교체 지침 전적으로 Visual Studio의 복잡 한 사용자 요구 사항에 맞게 조정 하기 위해 사용 하는 일반적인 규칙을 추가 하는 영역을 포함 합니다.  
  
-   [Visual Studio의 일반 컨트롤 패턴](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md)  
  
    -   [공용 컨트롤](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_CommonControls)  
  
    -   [텍스트 컨트롤](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_TextControls)  
  
    -   [단추, 하이퍼링크](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_ButtonsAndHyperlinks)  
  
## 복합 패턴  
 사용자가 작업을 수행 해야 하는 방법의 여러 가지가 있습니다. 가능한 경우 모두 상호 작용 및 시각적 디자인에 대 한 이러한 패턴을 사용 하 여 기능을 설계 해야 합니다.  
  
 중 가장 중요 한 일부 Visual Studio 내에서 많은 복합 패턴도 하는 동안 일관성 관련 됩니다.  
  
-   [Visual Studio에 대 한 복합 패턴](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md)  
  
    -   [개체에 UI 및 보기](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_OnObjectUI)  
  
    -   [모델 선택](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_SelectionModels)  
  
    -   [지 속성 및 설정 저장](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_PersistenceAndSavingSettings)  
  
    -   [터치식 입력](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_TouchInput)