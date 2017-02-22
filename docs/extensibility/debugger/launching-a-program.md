---
title: "프로그램 실행 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "시작 하는 디버그 엔진"
  - "프로그램 시작"
ms.assetid: 6857e9c6-e44a-468a-afa4-f7c4a0b77844
caps.latest.revision: 21
caps.handback.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로그램 실행
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로그램을 디버깅 하려는 사용자에서 IDE 디버거를 실행 하려면 F5 키를 눌러 있습니다.  궁극적으로 IDE를 차례로 연결 되어 있으면, 또는, 다음과 같은 프로그램에 연결한는 디버그 엔진에 \(DE\) 연결에서 발생 한 이벤트를 시작 합니다.  
  
1.  IDE 디버그 설정을 현재 솔루션의 프로젝트를 가져올 수 있는 프로젝트 패키지를 먼저 호출 합니다.  시작 디렉터리, 환경 변수, 프로그램 실행 됩니다 포트 및 지정 된 경우 프로그램을 만드는 데 사용 하는 DE 있습니다.  이러한 설정은 디버그 패키지에 전달 됩니다.  
  
2.  DE DE를 지정 하면 프로그램을 실행 하는 운영 체제를 호출 합니다.  프로그램을 실행의 결과로 프로그램의 런타임 환경에 로드 됩니다.  예를 들어, MSIL에는 프로그램을 작성 하는 경우 프로그램을 실행 하려면 공용 언어 런타임에서 호출 됩니다.  
  
     또는  
  
     포트는 DE를 지정 하지 않으면 프로그램의 런타임 환경에 로드 되는 프로그램을 실행 하는 운영 체제를 호출 합니다.  
  
    > [!NOTE]
    >  프로그램을 실행 하는 DE 사용 하는 경우 동일한 DE 프로그램으로 연결 될 가능성이 있습니다.  
  
3.  여부는 DE 포트나 프로그램을 실행는 DE 또는 런타임 환경 다음 프로그램 설명 노드를 만듭니다 및 따라 프로그램이 실행 되는 포트를 알려 줍니다.  
  
    > [!NOTE]
    >  라이트웨이트 표현 디버깅할 수 있는 프로그램의 프로그램 노드 이기 때문에 런타임 환경 프로그램이 노드를 만들 것을 권장 합니다.  방금 만들고 프로그램 노드 등록 하기 전체 DE를 로드 하지 않아도가 됩니다.  IDE, 하지만 되지 않습니다 IDE의 실행 실제로 실행 되는 DE 설계 되었습니다 경우 프로그램 노드의 포트를 추가할 수 있는 구성 요소는 있어야 합니다.  
  
 새로 만든된 프로그램에서 다른 프로그램을 함께 관련 된 또는 관련 되지 않은, 시작 또는 연결 된 동일한 IDE에서 디버그 세션 작성.  
  
 프로그래밍 방식으로 때 처음 누를  **F5**, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 디버그 패키지를 호출 하는 프로그램이 시작 되 고 해당 형식과 관련 된 프로젝트 패키지 통해는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg.DebugLaunch%2A> 에 작성 하는 방법은 <xref:Microsoft.VisualStudio.Shell.Interop.VsDebugTargetInfo2> 구조 솔루션의 현재 프로젝트 디버그 설정 사용 합니다.  이 구조를 디버그 패키지에 호출을 통해 전달의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebugger2.LaunchDebugTargets2%2A> 메서드가 있습니다.  디버그 패키지를 다음 프로그램 디버그 디버그 및 연관 된 모든 엔진을 시작 합니다. 세션 디버그 매니저를 \(SDM\)를 인스턴스화합니다.  
  
 SDM에 전달 된 인수 중 하나는 프로그램을 실행 하는 데 DE의 GUID입니다.  
  
 DE GUID가 아닌 경우 `GUID_NULL`, SDM은 다음 호출 하는 DE co\-creates는 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) 메서드는 프로그램을 시작 합니다.  예를 들어 프로그램이 네이티브 코드에서 다음 기록 됩니다 `IDebugEngineLaunch2::LaunchSuspended` 호출 됩니다 것입니다 `CreateProcess` 및 `ResumeThread` \(Win32 함수는 프로그램을 실행\).  
  
 프로그램을 실행의 결과로 프로그램의 런타임 환경에 로드 됩니다.  다음의 DE 또는 런타임 환경을 만듭니다는 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) 인터페이스 프로그램을 설명 하 고이 인터페이스에 전달 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) 프로그램을 실행 하는 포트를 알릴 수 있습니다.  
  
 경우 `GUID_NULL` 포트 프로그램을 시작한 다음, 전달 됩니다.  프로그램이 실행 되 면 런타임 환경을 만들고 있는 `IDebugProgramNode2` 인터페이스 프로그램을 설명 하 고 전달 하 `IDebugPortNotify2::AddProgramNode`.  이 프로그램을 실행 하는 포트를 알려 줍니다.  다음은 SDM 디버그 엔진 실행 중인 프로그램에 연결합니다.  
  
## 단원 내용  
 [포트에 게 알리는](../../extensibility/debugger/notifying-the-port.md)  
 프로그램이 시작 되 고 포트 알림을 받습니다 후 수행 되는 작업에 대해 설명 합니다.  
  
 [시작 된 후 연결](../../extensibility/debugger/attaching-after-a-launch.md)  
 디버그 세션 DE의 프로그램에 연결할 준비가 되 면 문서입니다.  
  
## 관련 단원  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)  
 프로그램을 시작 하 고 식을 계산 하는 것과 같은 다양 한 디버깅 작업에 대 한 링크가 포함 되어 있습니다.