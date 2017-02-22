---
title: "솔루션의 프로젝트 로드 관리 | Microsoft Docs"
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
  - "솔루션, 프로젝트 로드 관리"
ms.assetid: 097c89d0-f76a-4aaf-ada9-9a778bd179a0
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# 솔루션의 프로젝트 로드 관리
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 솔루션에는 다 수의 프로젝트 포함 될 수 있습니다. 기본 Visual Studio 동작은 솔루션 열릴 때 솔루션의 모든 프로젝트를 로드 하 고 사용자가 프로젝트 모두 로드 작업이 완료 될 때까지 사용할 수 없도록 합니다. 프로젝트 로드 프로세스 2 분 이상 소요 시간:, 로드 되는 프로젝트의 수와 프로젝트의 총 수를 보여 주는 진행률 표시줄이 표시 됩니다. 여러 프로젝트가 포함 된 솔루션에서 작업 하는 동안 사용자가 프로젝트 언로드할 수 있지만이 절차는 몇 가지 단점이: 언로드된 프로젝트, 솔루션 다시 빌드 명령의 일부로 빌드되지 않는 및 형식 IntelliSense 기술 및 닫힌된 프로젝트의 멤버가 표시 되지 않습니다.  
  
 개발자는 솔루션 로드 시간이 줄어들고 솔루션 로드 관리자를 만들어 동작을 로드 하는 프로젝트를 관리 합니다. 솔루션 로드 관리자를 사용 하는 특정 프로젝트나 프로젝트 형식에 대 한 우선 순위를 로드 하는 다른 프로젝트를 설정, 배경 빌드를 시작 하기 전에 프로젝트를 로드 했는지 확인, 다른 백그라운드 작업이 완료 될 때까지 백그라운드 로드 지연 작업을 수행할 수 다른 프로젝트 부하 관리 합니다.  
  
## 우선 순위를 로드 하는 프로젝트  
 Visual Studio는 네 개의 서로 다른 프로젝트 로드 우선 순위를 정의합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority> \(기본값\): 솔루션을 열 때 프로젝트 비동기적으로 로드 됩니다. 언로드된 프로젝트가 이미 솔루션을 연 후이 우선 순위 설정 되 면 하는 경우 다음 유휴 지점에서 프로젝트가 로드 됩니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority>: 프로젝트, 사용자가 속한 모든 프로젝트에 로드 될 때까지 기다릴 필요 없이 로드 된 프로젝트에 액세스할 수 있도록 백그라운드에 로드 된 솔루션을 열 때.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority>: 프로젝트 액세스 될 때 로드 됩니다. 프로젝트 \(솔루션의 사용자 옵션 파일에 유지 된\) 열려 있는 문서 목록에 있기 때문에 솔루션을 열면 프로젝트에 속하는 파일을 열면 솔루션 탐색기에서 프로젝트 노드를 확장할 때 액세스 또는 경우에 다른 프로젝트는 프로젝트에 종속 되어 로드 되 고 있습니다. 이 형식은 프로젝트의 빌드 프로세스를 시작 하기 전에 자동으로 로드 되지 않습니다. 솔루션 로드 관리자는 필요한 모든 프로젝트를 로드 했는지 확인 하는 일을 담당 합니다. 이러한 프로젝트는 전체 솔루션 파일에서 찾기\/바꾸기를 시작 하기 전에 로드 해야 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority>: 프로젝트 로드 되지 않게 하려면 사용자가 명시적으로 요청 하지 않으면 됩니다. 또한이 경우 프로젝트를 명시적으로 로드 되지 않은 경우입니다.  
  
## 솔루션 로드 관리자 만들기  
 개발자가 관리자를 만들 수 솔루션 로드를 구현 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager> 알리고 Visual Studio 솔루션 로드 관리자 활성화 되어 있다고 합니다.  
  
#### 솔루션 로드 관리자를 활성화합니다.  
 Visual Studio에서는 하나의 솔루션 로드 관리자 지정된 시간에 솔루션 로드를 활성화할 때 Visual Studio를 알려 하므로 관리자입니다. 두 번째 솔루션 로드 관리자는 나중에 활성화 되 면 솔루션 부하 관리자의 연결이 끊어집니다.  
  
 가져와야는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution> 서비스와 설정 된 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4> 속성:  
  
```c#  
IVsSolution pSolution = GetService(typeof(SVsSolution)) as IVsSolution; object objLoadMgr = this;   //the class that implements IVsSolutionManager pSolution.SetProperty((int)__VSPROPID4.VSPROPID_ActiveSolutionLoadManager, objLoadMgr);  
```  
  
#### IVsSolutionLoadManager 구현  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager.OnBeforeOpenProject%2A> 메서드 솔루션을 여는 프로세스 동안 호출 됩니다. 사용 하면이 메서드를 구현 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManagerSupport> 서비스를 관리 하려는 프로젝트의 형식에 대 한 부하 우선 순위를 설정 합니다. 예를 들어 다음 코드는 C\# 프로젝트 형식을 백그라운드에서 로드를 설정 합니다.  
  
```c#  
Guid guidCSProjectType = new Guid("{FAE04EC0-301F-11d3-BF4B-00C04F79EFBC}"); pSLMgrSupport.SetProjectLoadPriority(guidProjectID, (uint)_VSProjectLoadPriority.PLP_BackgroundLoad);  
```  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager.OnDisconnect%2A> Visual Studio 종료 되 면 또는 다른 패키지 전송 활성 솔루션 로드 관리자를 호출 하 여 하는 경우 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.SetProperty%2A> 와 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4> 속성입니다.  
  
#### 다양 한 종류의 솔루션 로드 관리자를 위한 전략  
 관리 하는 솔루션 유형에 따라 다양 한 방식에서 솔루션 로드 관리자를 구현할 수 있습니다.  
  
 솔루션 로드 관리자 일반적으로 로드 하는 솔루션을 관리 하려는 경우에 VSPackage의 일환으로 구현할 수 있습니다. 추가 하 여 패키지를 자동 로드로 설정 해야는 <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> 값 VSPackage에 <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionOpening_guid>합니다. 다음 솔루션 로드 관리자를 활성화할 수는 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> 메서드.  
  
> [!NOTE]
>  자동 로드 패키지에 대 한 자세한 내용은 참조 [Vspackage를 로드합니다.](../extensibility/loading-vspackages.md)합니다.  
  
 Visual Studio에서 마지막 솔루션 부하 관리자만 활성화할를 인식 하므로 일반적인 솔루션 부하 관리자 자신을 활성화 하기 전에 기존 부하 관리자 인지 여부를 탐지 항상 해야 합니다. 에 대 한 솔루션 서비스에 대해 GetProperty\(\)를 호출 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4> 반환 `null`, 관리자가 없거나 활성 솔루션 로드 합니다. Null 반환 하지 않으면, 솔루션 로드 관리자로 서 개체가 같은지 여부를 확인 합니다.  
  
 VSPackage 솔루션 로드 이벤트를 구독할 수 솔루션 로드 관리자를 사용 하는 몇 가지 유형의 솔루션을 관리 하려는 경우 \(호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AdviseSolutionEvents%2A>\)에 대 한 이벤트 처리기를 사용 하 고 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeOpenSolution%2A> 솔루션 로드 관리자를 활성화 하려면.  
  
 솔루션 로드 관리자만 특정 솔루션을 관리 하려는 경우 솔루션 파일의 일부로 활성화 정보를 유지할 수 있습니다. 이 작업을 수행 하려면 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.WriteSolutionProps%2A> 전 솔루션 섹션입니다.  
  
 특정 솔루션 로드 관리자를 비활성화 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents.OnAfterCloseSolution%2A> 다른 솔루션 로드 관리자와 충돌을 순서 대로 이벤트 처리기입니다.  
  
 전역 프로젝트 부하 우선 순위 \(예를 들어에 설정 된 속성 옵션 페이지\)를 유지 하기 위해에서 솔루션 로드 관리자를 활성화할 수 있습니다만 솔루션 로드 관리자를 필요한 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A> 이벤트 처리기 솔루션 속성의 설정이 유지 한 다음 솔루션 로드 관리자를 비활성화 합니다.  
  
## 솔루션 로드 이벤트를 처리합니다.  
 솔루션 로드 이벤트를 구독 하려면 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AdviseSolutionEvents%2A> 솔루션 로드 관리자를 활성화 하면 됩니다. 구현 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents>, 우선 순위를 로드 하는 다른 프로젝트와 관련 된 이벤트에 응답할 수 있습니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeOpenSolution%2A>:이 솔루션 열리기 전에 발생 합니다. 솔루션의 프로젝트에 대 한 우선 순위를 로드 하 여 프로젝트를 변경 하려면 사용할 수 있습니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeBackgroundSolutionLoadBegins%2A>:이 솔루션은 완전히 로드 한 후 시작 하기 전에 백그라운드 로드 프로젝트 다시 발생 합니다. 예를 들어 사용자에 액세스할 수 있는 부하 우선 순위는 LoadIfNeeded, 프로젝트 또는 솔루션 로드 관리자 변경 했을 수 프로젝트 부하 우선 순위를 BackgroundLoad는 해당 프로젝트의 백그라운드 로드를 시작 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnAfterBackgroundSolutionLoadComplete%2A>:이 발생 솔루션을 처음에 완전히 로드 된 후 솔루션 부하 관리자가 있는지 여부. 그는 또한 백그라운드 로드 또는 요청 시 로드 솔루션 완전히 로드 될 때마다 발생 합니다. 같은 시간에 <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExistsAndFullyLoaded_guid> 다시 활성화 됩니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnQueryBackgroundLoadProjectBatch%2A>:이 프로젝트 \(또는 프로젝트\)의 로드 하기 전에 발생 합니다. 프로젝트 로드 되기 전에 다른 백그라운드 프로세스가 완료 되도록 설정 `pfShouldDelayLoadToNextIdle` 를 **true**합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeLoadProjectBatch%2A>:이 프로젝트의 일괄 처리 로드 되려고 할 때 발생 합니다. 경우 `fIsBackgroundIdleBatch` 가 true 인 경우 백그라운드;에서 데이터를 로드 하는 프로젝트는 `fIsBackgroundIdleBatch` 은 프로젝트를 로드 한 사용자 요청의 결과로 동기적으로 예를 들어 사용자 솔루션 탐색기에서 보류 중인 프로젝트를 확장 하는 경우는 false입니다. 그렇지 않으면 수행 되도록 해야 하는 비용이 많이 드는 작업을 수행 하려면이 옵션을 구현할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnAfterOpenProject%2A>합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnAfterLoadProjectBatch%2A>:이 프로젝트의 일괄 처리 로드 된 후에 발생 합니다.  
  
## 검색 및 관리 솔루션 및 프로젝트 로드  
 프로젝트 및 솔루션의 부하 상태를 감지 하기 위해 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.GetProperty%2A> 다음 값을 사용 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>: `var` 반환 `true` 솔루션 및 해당 프로젝트가 모두 로드 된 경우, 그렇지 않으면 `false`합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>: `var` 반환 `true` 경우 프로젝트의 일괄 처리는 현재 되 고 백그라운드에 로드, 그렇지 않으면 `false`합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>: `var` 반환 `true` 경우 프로젝트의 일괄 처리는 현재 로드 하 고 동기적으로 사용자 명령 또는 다른 명시적 로드의 결과로 그렇지 않으면 `false`합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID2>: `var` 반환 `true` 솔루션 종결 된 경우 현재 되 고, 그렇지 않으면 `false`합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>: `var` 반환 `true` 솔루션 현재을 여는 그렇지 않은 경우 `false`합니다.  
  
 다음 방법 중 하나를 호출 하 여 프로젝트 및 솔루션 로드 되었음을 \(에 관계 없이 프로젝트 부하 우선 순위\)을 보장할 수도 있습니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureSolutionIsLoaded%2A>: 메서드가 반환 되기 전에 로드 하 여 솔루션에 프로젝트를 강제로이 메서드를 호출 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureProjectIsLoaded%2A>:이 메서드를 호출에서 프로젝트를 강제로 `guidProject` 메서드가 반환 되기 전에 로드 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureProjectsAreLoaded%2A>:이 메서드를 호출에서 프로젝트를 강제로 `guidProjectID` 메서드가 반환 되기 전에 로드 합니다.  
  
> [!NOTE]
>  . 기본적으로는 요구 하는 프로젝트에만 로드 및 백그라운드 로드 우선 순위 로드 되 면 이지만 if는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSBSLFLAGS> 플래그는 메서드에 전달, 명시적으로 로드 하는 것으로 표시 된 것을 제외한 모든 프로젝트를 로드 됩니다.