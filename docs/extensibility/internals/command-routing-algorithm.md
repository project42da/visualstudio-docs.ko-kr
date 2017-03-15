---
title: "명령 라우팅 알고리즘 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "명령 라우팅"
  - "명령 라우팅"
ms.assetid: 998b616b-bd08-45cb-845f-808efb8c33bc
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# 명령 라우팅 알고리즘
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Visual Studio에서 명령은 여러 가지 다양 한 구성 요소에 의해 처리 됩니다. 명령은 가장 바깥쪽 \(라고도 글로벌\) 컨텍스트를 현재 선택한 내용에 기반 하는 가장 안쪽의 컨텍스트에서 라우팅됩니다. 자세한 내용은 [가용성](../../extensibility/internals/command-availability.md)을 참조하세요.  
  
## 명령 확인 순서  
 명령에서는 다음과 같은 수준의 명령 컨텍스트를 통해 전달 됩니다.  
  
1.  추가 기능: 환경 먼저 모든 추가 기능에 있는 명령을 제공 합니다.  
  
2.  우선 순위 명령: 이러한 명령을 사용 하 여 등록 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterPriorityCommandTarget>합니다. Visual Studio의 모든 명령에 대해 이라고 하며 등록 된 순서 대로 호출 됩니다.  
  
3.  상황에 맞는 메뉴 명령을: 상황에 맞는 메뉴에 있는 명령이 먼저 일반적인 라우팅으로 상황에 맞는 메뉴 고 그 후 제공 되는 명령 대상으로 제공 됩니다.  
  
4.  도구 모음 명령 대상 설정: 이러한 명령 대상을 호출 하는 경우 등록 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell4.SetupToolbar2%2A>합니다.`pCmdTarget` 매개 변수 수 `null`합니다. 없는 경우 `null`, 이 명령 대상 업데이트를 설정 하는 도구 모음에 있는 모든 명령에 사용 됩니다. 셸 작업은 도구 모음을 설정 하는 경우 창 프레임으로 전달 하기는 `pCmdTarget` 명령 창 프레임을 통해 도구 모음 흐름에 대 한 모든 업데이트에도 있도록 때 포커스가 합니다.  
  
5.  도구 창: 일반적으로 구현 하는 windows의 도구는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> 인터페이스를 구현 해야는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스 도구 창이 활성 창인지 때 Visual Studio 명령 대상을 얻을 수 있도록 합니다. 그러나 도구 창에 있는 경우 포커스가 **프로젝트** 창에서 다음 명령으로 라우팅되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 인터페이스 선택 된 항목의 공통 부모입니다. 이 옵션을이 선택 여러 프로젝트에 연결 되어 있으면 명령으로 라우팅됩니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution> 계층 구조입니다.<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 인터페이스 포함는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A> 에서 해당 명령에 유사 하는 메서드는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스입니다.  
  
6.  문서 창: 명령에 있는 경우 RouteToDocs 플래그가.vsct 파일에서 설정, Visual Studio 찾습니다 문서 보기 개체 중 하나에 대해 명령 대상의 인스턴스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> 인터페이스 또는 문서 개체의 인스턴스 \(일반적으로 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> 인터페이스 또는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 인터페이스\)입니다. Visual Studio에 명령을 전달 문서 뷰 개체 명령을 지원 하지 않으면는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 반환 되는 인터페이스입니다. \(이 문서 데이터 개체에 대 한 선택적 인터페이스입니다.\)  
  
7.  현재 계층: 현재 계층 액티브 문서 창이 나에서 선택 되어 있는 계층 구조를 담당 하는 프로젝트 수 **솔루션 탐색기**합니다. Visual Studio 찾습니다는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 현재, 또는 활성 상태인 계층에서 구현 되는 인터페이스입니다. 계층 구조는 계층 구조는 프로젝트 항목의 문서 창에 포커스가 있는 경우에 활성화 될 때마다 사용할 수 있는 명령을 지원 해야 합니다. 그러나 경우에만 적용 되는 명령 **솔루션 탐색기** 에 포커스를 사용 하 여 지원 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 인터페이스와 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>메서드.  
  
     **잘라내기**, **복사**, **붙여넣기**, **삭제**, **이름 바꾸기**, **Enter**, 및 **DoubleClick** 명령에는 특별 한 처리가 필요 합니다. 처리 하는 방법에 대 한 내용은 **삭제** 및 **제거** 계층에 대 한 명령 참조는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDeleteHandler> 인터페이스입니다.  
  
8.  Global: 앞에서 언급 한 컨텍스트에서 명령을 처리 하지 않은, Visual Studio 시도 구현 하는 명령을 담당 하는 VSPackage를 라우팅하는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스입니다. VSPackage 이미 로드 되지 않은, 하는 경우 로드 되지 않은 Visual Studio에서 호출 하는 경우는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드. VSPackage 경우에만 로드 되는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> 메서드를 호출 합니다.  
  
## 참고 항목  
 [명령 디자인](../../extensibility/internals/command-design.md)