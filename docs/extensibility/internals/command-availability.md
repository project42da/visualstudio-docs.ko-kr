---
title: "가용성 명령 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands, context
- menu items, visibility contexts
ms.assetid: c74e3ccf-d771-48c8-a2f9-df323b166784
caps.latest.revision: "34"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 53ab248d9e71d3177cabb8ce522343d37bcabb26
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="command-availability"></a>명령 사용 가능성
Visual Studio 컨텍스트는 사용할 수 있는 명령을 결정 합니다. 컨텍스트는 현재 프로젝트, 현재 편집기, 로드 되는 Vspackage 및 통합된 개발 환경 (IDE)의 다른 측면에 따라 변경 될 수 있습니다.  
  
## <a name="command-contexts"></a>명령 컨텍스트  
 다음 명령은 컨텍스트는 가장 일반적인입니다.  
  
-   **IDE** IDE에서 제공 하는 명령을 항상 사용할 수 있습니다.  
  
-   **VSPackage** Vspackage를 표시 하거나 숨길 주석은 때 정의할 수 있습니다.  
  
-   **프로젝트** 프로젝트 명령이 현재 선택한 프로젝트에 대해서만 나타납니다.  
  
-   **편집기** 하나만 편집기 한 번에 활성화 될 수 있습니다. 활성 편집기에서 명령을 사용할 수 있습니다. 편집기 언어 서비스와 긴밀 하 게 작동합니다. 언어 서비스에 연결된 된 편집기의 컨텍스트에서 해당 명령을 처리 해야 합니다.  
  
-   **파일 유형** 편집기 둘 이상의 형식의 파일을 로드할 수 있습니다. 사용 가능한 명령 파일 형식에 따라 변경할 수 있습니다.  
  
-   **활성 창** 마지막 현재 문서 창 키 바인딩에 대 한 사용자 인터페이스 (UI) 컨텍스트를 설정 합니다. 그러나 내부 웹 브라우저를 유사한 키 바인딩 표가 있는 도구 창의 UI 컨텍스트를 설정할 수도 있습니다. HTML 편집기와 같은 다중 탭 문서 창에 대 한 모든 탭에는 다른 명령 컨텍스트가 GUID입니다. 도구 창을 등록 한 후 항상 이므로에서 사용할 수는 **보기** 메뉴.  
  
-   **UI 컨텍스트** UI 컨텍스트 변수의 값으로 식별 됩니다는 <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT> 클래스, 예를 들어 <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionBuilding> 솔루션을 작성할 때 또는 <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_Debugging> 디버거가 활성화 되어 있습니다. 여러 UI 컨텍스트는 동시에 활성화할 수 있습니다.  
  
## <a name="defining-custom-context-guids"></a>사용자 지정 컨텍스트 Guid를 정의합니다.  
 적절 한 명령 컨텍스트부터 GUID 아직 정의 되지 않은 경우에 VSPackage의 하나를 정의 수 있으며 활성 또는 비활성으로 명령을 표시 유형을 제어 하는 데 필요한 되도록를 프로그래밍할 수 있습니다.  
  
1.  컨텍스트 Guid를 호출 하 여 등록 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCmdUIContextCookie%2A> 메서드.  
  
2.  호출 하 여 컨텍스트 GUID의 상태를 가져오기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> 메서드.  
  
3.  컨텍스트 Guid를를 호출 하 여 켜고 끄려면는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.SetCmdUIContext%2A> 메서드.  
  
    > [!CAUTION]
    >  다른 Vspackage에 종속 될 수 있으므로 VSPackage가 모든 기존 컨텍스트 Guid를 영향을 주지 않는지 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컨텍스트 개체 선택](../../extensibility/internals/selection-context-objects.md)   
 [VSPackage에서 사용자 인터페이스 요소를 추가하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)