---
title: Visual Studio Shell | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- shell, Visual Studio
- Visual Studio, shell
ms.assetid: cb124ef4-1a6b-4bfe-bfbf-295ef9c07f36
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 71b624cee0e55f95f90a86eac943828bbc26ac97
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="visual-studio-shell"></a>Visual Studio Shell
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] shell에 통합의 주요 에이전트인은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 셸 공통 서비스를 공유 하는 Vspackage를 사용 하도록 설정 하려면 필요한 기능을 제공 합니다. 때문에의 아키텍처 목표 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] , Vspackage의 기본 기능을 vest를 셸에 기본 기능을 제공 하 고 Vspackage의 구성 요소 간 간 통신을 지원 하기 위한 프레임 워크.  
  
## <a name="shell-responsibilities"></a>셸 책임  
 다음과 같은 주요 임무 셸에:  
  
-   (COM 인터페이스를 통해) 사용자 인터페이스 (UI)의 기본 요소를 지원합니다. 여기에 기본 메뉴 및 도구 모음, 문서 창 프레임 또는 다중 문서 MDI (인터페이스) 자식 창 및 도구 창 프레임 및 도킹 지원을 포함 합니다.  
  
-   문서의 지 속성을 조정할 수 있도록 고 여러 가지 방법으로 또는 호환 되지 않는 방법으로 해당 하나의 문서를 열 수 없습니다 보장 하기 위해 실행 중인 실행 중인 문서 테이블 (RDT)에서 현재 열려 있는 모든 문서 목록이 유지 관리 합니다.  
  
-   명령 라우팅 및 명령 처리 인터페이스를 지 원하는 `IOleCommandTarget`합니다.  
  
-   적절 한 시간에 Vspackage를 로드 합니다. 지연 로드 VSPackage는의 셸 성능을 개선 하는 데 필요 합니다.  
  
-   공유 서비스와 같은 특정 관리 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>, 기본 셸 기능을 제공 하 고 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>, 기본적인 창 관리 기능을 제공 하는입니다.  
  
-   솔루션 (.sln) 파일을 관리 합니다. 솔루션 관련된 프로젝트를 Visual c + + 6.0에서 작업 영역 (.dsw) 파일과 마찬가지로 그룹에 포함 됩니다.  
  
-   셸 전체 선택 영역 추적, 컨텍스트 및 통화입니다. 셸에서 다음 유형의 항목을 추적합니다.  
  
    -   현재 프로젝트  
  
    -   현재 프로젝트 항목 또는 현재 ItemID <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>  
  
    -   에 대 한 현재 선택 된 **속성** 창 또는 `SelectionContainer`  
  
    -   Id 또는 CmdUIGuids 명령, 메뉴 및 도구 모음의 표시 유형을 제어 하는 UI 컨텍스트  
  
    -   활성 창, 문서 및 실행 취소 관리자 등의 현재 요소  
  
    -   동적 도움말을 구동 하는 사용자 컨텍스트 특성  
  
 또한 셸 설치 된 Vspackage 및 현재 서비스 간의 통신을 중재합니다. 셸의 핵심 기능을 지원 하 고에 통합 하는 모든 Vspackage를 사용할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 다음 항목을 다음과 같습니다. 이러한 핵심 기능  
  
-   **에 대 한** 대화 상자 및 시작 화면  
  
-   **새로운 기능 및 기존 항목 추가 추가** 대화 상자  
  
-   **클래스 뷰** 창 및 **개체 브라우저**  
  
-   **참조** 대화 상자  
  
-   **문서 개요** 창  
  
-   **동적 도움말** 창  
  
-   **찾을** 및 **바꾸기**  
  
-   **프로젝트 열기** 및 **열려 있는 파일** 대화 상자에 **새로** 메뉴  
  
-   **옵션** 대화 상자에는 **도구** 메뉴  
  
-   **속성** 창  
  
-   **솔루션 탐색기**  
  
-   **작업 목록** 창  
  
-   **도구 상자**  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>   
 [VSPackage](../../extensibility/internals/vspackages.md)