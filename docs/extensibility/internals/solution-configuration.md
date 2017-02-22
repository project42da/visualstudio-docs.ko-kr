---
title: "솔루션 구성 | Microsoft Docs"
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
  - "솔루션 구성"
ms.assetid: f22cfc75-3e31-4e0d-88a9-3ca99539203b
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 솔루션 구성
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

솔루션 구성을 솔루션 수준 속성을 저장 합니다. 직접 실행의 동작에서 **Start** \(F5\) 키 및 **Build** 명령입니다. 기본적으로 이러한 명령을 빌드하고 디버그 구성을 시작 합니다. 두 명령은 솔루션 구성의 컨텍스트에서 실행 됩니다. 즉, 사용자를 시작 및 설정을 통해 모든 활성 솔루션 구성 된 빌드 f5 키를 예상할 수 있도록 합니다. 빌드 및 실행 하는 데 있어 프로젝트 대신 솔루션에 대 한 최적화 하기 위해 환경을 사용할 수 있습니다.  
  
 표준 Visual Studio 도구 모음 시작 단추 및 솔루션 구성 드롭다운 시작 단추 오른쪽에 포함 되어 있습니다. 이 목록에서는 f5 키를 누를 때 시작 되도록 구성 선택, 자신의 솔루션 구성 만들기 또는 기존 구성을 편집할 수 있습니다.  
  
> [!NOTE]
>  없는 확장성 인터페이스를 만들거나 솔루션 구성 편집 있습니다. 사용 해야 `DTE.SolutionBuilder`합니다. 그러나 솔루션 빌드를 관리 하기 위한 확장성 Api는. 자세한 내용은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager2>을 참조하십시오.  
  
 프로젝트 형식에서 지 원하는 솔루션 구성을 구현 하는 방법을 다음과 같습니다.  
  
-   프로젝트  
  
     현재 솔루션에 있는 프로젝트의 이름을 표시 합니다.  
  
-   구성  
  
     프로젝트 형식에서 지 원하는 구성 목록을 제공 하 고 구현 속성 페이지에 표시 하려면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2>합니다.  
  
     구성 열이 솔루션 구성에서 빌드할 프로젝트 구성의 이름을 표시 하 고 화살표 단추를 클릭할 때 모든 프로젝트 구성에 나열 합니다. 환경 호출의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgNames%2A> 메서드를이 목록 작성 합니다. 하는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgProviderProperty%2A> 메서드 나타냅니다 프로젝트 구성 편집 지원, 새로운 구성 머리글 아래에서 편집 선택도 표시 됩니다. 메서드를 호출 하는 대화 상자를 시작 하는 각 선택이 항목은 `IVsCfgProvider2` 프로젝트의 구성을 편집 하는 인터페이스입니다.  
  
     프로젝트 구성에서 지원 하지 않는 경우 구성 열 없음 표시 되며 비활성화 됩니다.  
  
-   플랫폼  
  
     선택한 프로젝트 구성에 대 한 빌드 및 화살표 단추를 클릭할 때 모든 프로젝트에 대해 사용 가능한 플랫폼을 나열 하는 플랫폼을 표시 합니다. 환경 호출의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetPlatformNames%2A> 메서드를이 목록 작성 합니다. 하는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgProviderProperty%2A> 메서드 나타냅니다 프로젝트 플랫폼 편집 지원, 새로운 플랫폼 머리글 아래에서 편집 선택도 표시 됩니다. 호출 하는 대화 상자를 시작 하는 각 선택이 항목 `IVsCfgProvider2` 방법으로 프로젝트의 사용 가능한 플랫폼을 편집할 수 있습니다.  
  
     프로젝트 플랫폼을 지원 하지 않는 경우 해당 프로젝트에 platform 열 없음 표시 되며 비활성화 됩니다.  
  
-   빌드  
  
     현재 솔루션 구성에 의해 프로젝트가 빌드될 여부를 지정 합니다. 선택 하지 않은 프로젝트는 솔루션 수준의 빌드 명령이 포함 된 모든 프로젝트 종속성 불구 하 고 호출 되는 경우에 빌드되지 않습니다. 빌드할 선택 되지 않은 프로젝트 디버깅, 실행, 패키지 및 솔루션을 배포에 포함 됩니다.  
  
-   배포  
  
     선택한 솔루션 빌드 구성을 사용 하 여 시작 또는 배포 명령을 사용할 때 프로젝트를 배포할 수 있는지 여부를 지정 합니다. 이 필드에 대 한 확인란을 구현 하 여 배포 지 원하는 경우 사용할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> 인터페이스를 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2> 개체입니다.  
  
 새 솔루션 구성을 추가 되 면, 사용자를 작성 하 고 해당 구성을 시작 표준 도구 모음의 솔루션 구성 드롭다운 목록 상자에서 선택할 수 있습니다.  
  
## 참고 항목  
 [구성 옵션 관리](../../extensibility/internals/managing-configuration-options.md)   
 [빌드를 위한 프로젝트 구성](../../extensibility/internals/project-configuration-for-building.md)   
 [프로젝트 구성 개체](../../extensibility/internals/project-configuration-object.md)