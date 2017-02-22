---
title: "확장 및 도구 창을 사용자 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "사용자 인터페이스, essentials"
  - "표준 도구 창"
ms.assetid: 46b2892e-7b2b-4b3f-83a7-b884f1e114ee
caps.latest.revision: 20
caps.handback.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
---
# 확장 및 도구 창을 사용자 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio에는 여러 다른 종류의 windows에서는 예를 들어 도구 창, 문서 창 및 대화 상자 창을 제공합니다. 속성 창, 출력 창 및 작업 목록 창 등 다른 windows 도구 창의 종류가 있습니다.  
  
## 도구 창  
 Visual Studio 도구 창에는 파일 기반 없는 일반적으로 읽기 전용 창입니다. 이 파일을 읽기 \/ 쓰기 모드에서 표시 하는 문서 창에서 다릅니다.**도구 상자**, **솔루션 탐색기**, **속성** 창 및 **웹 브라우저** 도구 창에 속합니다.  
  
 간단한 도구 창을 만드는 방법을 알아보려면 참조 [도구 창 추가](../extensibility/adding-a-tool-window.md)합니다.  
  
 도구 창에 Visual Studio를 등록 하려면 참조 [등록 하는 도구 창](../extensibility/registering-a-tool-window.md)합니다.  
  
 도구 창에는 단일 인스턴스는 기본적으로, 즉 도구 창의 인스턴스를 하나만 열 수 한 번에 있습니다. 단일 인스턴스 도구 창을 열릴 IDE를 닫을 때까지 열린 유지 됩니다. 단일 인스턴스 도구 창을 닫으면의 표시 유형을 변경 합니다. 만들 수 있습니다도 다중 인스턴스 도구 창을 창의 여러 인스턴스가 동시에 열 수 있습니다. 자세한 내용은 [다중 인스턴스 도구 창 만들기](../extensibility/creating-a-multi-instance-tool-window.md)를 참조하세요.  
  
 도구 창 수 *동적*, 되는지 표시 관련된 UI 컨텍스트에 적용 될 때마다 의미 합니다. 자동 표시 유형을 사용 하 여 IDE에서 windows의 혼잡 함을 줄일 수 있습니다. 자세한 내용은 [동적 도구 창 열기](../extensibility/opening-a-dynamic-tool-window.md)을 참조하세요.  
  
 도구 창을 도킹, 부동 또는 문서 프레임의 탭 수 있습니다. 도구 창 프레임의 IDE에서 제공 하 고 크기, 위치, 도킹 상태 및 기타 영구 속성을 제어 하는 데 사용 됩니다. 도구 창의 내용을 표시 합니다. 기본 크기 및 위치 적용만 도구 창을 처음 열릴 때; 그 후에 도구 창 상태 유지 됩니다.  
  
 도구 창 WPF 사용자 컨트롤을 호스트 하 고 도구 모음을 지원할 수 있습니다. 재정의할 수는 <xref:Microsoft.VisualStudio.Shell.WindowPane.Window%2A> 호스팅된 컨트롤의 핸들을 반환 하는 속성입니다.  
  
 도구 창에 다양 한 기능을 추가할 수 있습니다. 예를 들어 도구 모음을 추가할 수 있습니다: [도구 창에는 도구 모음 추가](../extensibility/adding-a-toolbar-to-a-tool-window.md) 또는 바로 가기 메뉴: [도구 창의 바로 가기 메뉴를 추가합니다.](../extensibility/adding-a-shortcut-menu-in-a-tool-window.md)합니다. 도구 창 안에 있는 항목을 검색할 수 있도록 하는 검색 컨트롤을 추가할 수 있습니다: [도구 창에 검색 추가](../extensibility/adding-search-to-a-tool-window.md)합니다.  
  
 도구 창 이벤트를 구독할 수 있습니다: [이벤트에 가입](../extensibility/subscribing-to-an-event.md)합니다.  
  
## 기존 도구 창을 확장 하는 방법  
 새 도구 창에 대 한 정보를 추가할 수 있습니다 **옵션** 페이지와 새 설정에는 **속성** 페이지, 쓰기는 **작업 목록** 및 **출력** windows입니다. 자세한 내용은 [속성, 작업 목록, 출력 및 옵션 창을 확장합니다.](../extensibility/extending-the-properties-task-list-output-and-options-windows.md) 및 [속성, 작업 목록, 출력 및 옵션 창을 확장합니다.](../extensibility/extending-the-properties-task-list-output-and-options-windows.md)를 참조하세요.  
  
## 모달 대화 상자  
 Visual Studio 확장에서 만들어야 모달 대화 상자에서 파생 하 여 <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow?displayProperty=fullName>, 및 UI의 나머지 부분을 제어할 수 있습니다. 자세한 내용은 다음을 참조 합니다.[만들기 및 관리 모달 대화 상자](../extensibility/creating-and-managing-modal-dialog-boxes.md).  
  
## 참고 항목  
 [확장 도구 창 만들기](../extensibility/creating-an-extension-with-a-tool-window.md)