---
title: "명령 사용 가능성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "명령, 컨텍스트"
  - "메뉴 항목, 표시 유형 컨텍스트"
ms.assetid: c74e3ccf-d771-48c8-a2f9-df323b166784
caps.latest.revision: 34
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 34
---
# 명령 사용 가능성
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Visual Studio 컨텍스트는 사용할 수 있는 명령을 결정 합니다. 컨텍스트는 현재 프로젝트, 현재 편집기, 로드 되는 VSPackages 및 통합된 개발 환경 \(IDE\)의 다른 측면에 따라 변경 될 수 있습니다.  
  
## 명령 컨텍스트  
 다음 명령은 컨텍스트는 가장 일반적입니다.  
  
-   **IDE** 명령이 IDE에 의해 제공 되는 항상 사용할 수 있습니다.  
  
-   **VSPackage** Vspackage 수 정의 경우 명령을 표시 하거나 숨길 수 있습니다.  
  
-   **프로젝트** 명령이 현재 선택한 프로젝트에만 표시 합니다.  
  
-   **편집기** 한 번에 하나만 편집기 활성화 될 수 있습니다. 활성 편집기에서 명령을 사용할 수 있습니다. 편집기는 언어 서비스와 긴밀 하 게 작동합니다. 언어 서비스에 연결된 된 편집기의 컨텍스트에서 해당 명령을 처리 해야 합니다.  
  
-   **파일 유형** 편집기는 둘 이상의 형식의 파일을 로드할 수 있습니다. 사용 가능한 명령 파일 형식에 따라 변경할 수 있습니다.  
  
-   **활성 창** 마지막 활성 문서 창에 대 한 키 바인딩 사용자 인터페이스 \(UI\) 컨텍스트를 설정 합니다. 그러나 내부 웹 브라우저를 유사한 키 바인딩 테이블이 있는 도구 창 UI 컨텍스트를 설정할 수도 수 있습니다. HTML 편집기와 같은 다중 탭 문서 창에 대 한 모든 탭에는 다른 명령 컨텍스트가 GUID입니다. 도구 창을 등록 한 후 항상 사용 가능에 **보기** 메뉴.  
  
-   **UI 컨텍스트의** UI 컨텍스트에서의 값으로 식별 됩니다는 <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT> 클래스, 예를 들어 <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionBuilding> 솔루션을 구축 하는 경우 또는 <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_Debugging> 디버거 활성 상태일 때. 여러 UI 컨텍스트 동시에 활성화 될 수 있습니다.  
  
## 사용자 지정 컨텍스트 Guid를 정의합니다.  
 적절 한 명령 컨텍스트 GUID 아직 정의 되지 않은 경우 VSPackage에서 하나를 정의할 수 있으며 활성 또는 비활성 명령의 표시 유형을 제어 하려면 필요에 따라 되도록를 프로그래밍할 수 있습니다.  
  
1.  컨텍스트 Guid를 호출 하 여 등록 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCmdUIContextCookie%2A> 메서드.  
  
2.  호출 하 여 컨텍스트 GUID의 상태를 가져오기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> 메서드.  
  
3.  호출 하 여 컨텍스트 Guid를 켜거나 끄는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.SetCmdUIContext%2A> 메서드.  
  
    > [!CAUTION]
    >  VSPackage 영향을 주지 않습니다 모든 기존 컨텍스트 guid가 다른 Vspackage에 종속 될 수 있으므로 있는지 확인 합니다.  
  
## 참고 항목  
 [컨텍스트 개체 선택](../../extensibility/internals/selection-context-objects.md)   
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)