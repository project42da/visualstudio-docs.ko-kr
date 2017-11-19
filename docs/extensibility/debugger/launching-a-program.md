---
title: "프로그램을 시작 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, launching
- programs, launching
ms.assetid: 6857e9c6-e44a-468a-afa4-f7c4a0b77844
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 29e05c7cef8b7bc8644ccbf7ea542e2f043547a6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="launching-a-program"></a>프로그램을 시작
프로그램을 디버깅 하려는 사용자는 IDE에서 디버거를 실행 하려면 f5 수 있습니다. 이 일련의 IDE의 다시 연결 하거나 연결, 프로그램에 다음과 같이 디버그 엔진 (DE)에 연결 하면 결국 이벤트가 시작 됩니다.  
  
1.  IDE는 먼저 현재 프로젝트는 솔루션의 디버그 설정을 가져올 프로젝트 패키지를 호출 합니다. 설정의 시작 디렉터리, 환경 변수는 프로그램이 실행 되는 포트 및 지정 된 경우 해당 프로그램을 만드는 데 사용할 DE 포함 됩니다. 이러한 설정은 디버그 패키지에 전달 됩니다.  
  
2.  장치가 지정 된 경우는 DE 프로그램을 시작 하려면 운영 체제를 호출 합니다. 프로그램을 실행할로 인해 프로그램의 런타임 환경 로드 됩니다. 예를 들어 프로그램 MSIL로 작성 프로그램을 실행 하려면 공용 언어 런타임에서 호출 됩니다.  
  
     또는  
  
     포트는 DE 지정 되지 않은 경우 프로그램의 런타임 환경을 로드할는 프로그램을 시작 하려면 운영 체제를 호출 합니다.  
  
    > [!NOTE]
    >  프로그램을 실행 하는 장치가 사용 하는 경우 될 동일한 DE는 프로그램에 연결 됩니다.  
  
3.  여부는 DE 또는 포트 시작 프로그램에 따라는 DE 또는 런타임 환경에서 다음 프로그램 설명 또는 노드를 만들고 프로그램이 실행 되는 포트를에 알립니다.  
  
    > [!NOTE]
    >  프로그램 노드는 디버깅할 수 있는 프로그램을 간단 하 게 표시 하기 때문에 런타임 환경에서 프로그램 노드를 만든다는 것이 좋습니다. 전체 DE 방금를 만들어 등록 프로그램 노드를 로드 하지 않아도가 됩니다. DE 디자인 된 경우 IDE만 없습니다 IDE 프로세스를 실행 하는 실제로 실행 되는, 포트에 프로그램 노드를 추가할 수 있는 구성 요소가 있어야 합니다.  
  
 다른 프로그램을 함께 새로 만든된 프로그램 관련 또는 관련 되지 않은, 시작 또는 동일한 IDE에서 디버그 세션 구성에 연결 합니다.  
  
 프로그래밍 방식으로 처음 누를 때 **F5**, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 (연결 된 실행 프로그램의 형식과) 프로젝트 패키지를 호출 하는 디버그 패키지를 통해는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg.DebugLaunch%2A> 메서드는 out 폴더에 <xref:Microsoft.VisualStudio.Shell.Interop.VsDebugTargetInfo2> 솔루션의 현재 프로젝트의 디버그 설정 사용 하 여 구조입니다. 이 구조에 대 한 호출을 통해 디버그 패키지에 다시 전달 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebugger2.LaunchDebugTargets2%2A> 메서드. 디버그 패키지가 다음 디버깅 및 관련 디버그 엔진 되 고 프로그램을 시작 하는 세션 디버그 관리자를 (SDM)를 인스턴스화합니다.  
  
 SDM에 전달 된 인수 중 하나는 프로그램을 시작 하는 데 사용할 DE의 GUID입니다.  
  
 DE GUID 없으면 `GUID_NULL`은 SDM 배치 DE, 만들고 호출 합니다 해당 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) 메서드를 프로그램을 시작 합니다. 예를 들어, 프로그램이 네이티브 코드로 작성 된 경우 `IDebugEngineLaunch2::LaunchSuspended` 아마도 호출 `CreateProcess` 및 `ResumeThread` (Win32 함수) 프로그램을 실행 합니다.  
  
 프로그램을 실행할로 인해 프로그램의 런타임 환경 로드 됩니다. 그런 다음 만듭니다는 DE 또는 런타임 환경 중 하나는 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) 인터페이스를 프로그램에 설명 하 고이 인터페이스를 전달 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) 포트를 프로그램에 알리기 위해 실행 중입니다.  
  
 경우 `GUID_NULL` 전달 되는 포트는 프로그램을 시작 합니다. 프로그램이 실행 되 면 런타임 환경 만듭니다는 `IDebugProgramNode2` 전달 하는 프로그램을 설명 하기 위해 인터페이스 `IDebugPortNotify2::AddProgramNode`합니다. 이 프로그램이 실행 되는 포트를 알립니다. 다음은 SDM 실행 중인 프로그램에 디버그 엔진을 연결합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [포트에 알림](../../extensibility/debugger/notifying-the-port.md)  
 프로그램 시작 되 고 포트 알립니다 후의 상황에 대해 설명 합니다.  
  
 [시작 후 연결](../../extensibility/debugger/attaching-after-a-launch.md)  
 디버그 세션에서 DE 프로그램에 연결할 준비가 되었을 때 문서 수입니다.  
  
## <a name="related-sections"></a>관련 단원  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)  
 프로그램을 시작 하 여 식을 계산 등의 다양 한 디버깅 작업에 대 한 링크를 포함 합니다.