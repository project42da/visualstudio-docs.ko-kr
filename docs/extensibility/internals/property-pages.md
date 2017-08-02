---
title: "속성 페이지 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "속성을 변경 하는 구성 옵션"
  - "속성 페이지"
  - "구성 옵션을 변경 하는 속성 페이지"
ms.assetid: b9b3e6e8-1e30-4c89-9862-330265dcf38c
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 속성 페이지
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

표시 하 고 속성 페이지를 사용 하 여 프로젝트 구성에 종속 및 독립 속성을 변경할 수 있습니다.  A  **속성 페이지** 단추에서 사용할 수 있는  **속성** 창 또는 선택한 개체의 속성 페이지 보기를 제공 하는 개체에 대 한 솔루션 탐색기 도구 모음에서 합니다.  속성 페이지를 만들고 솔루션 및 프로젝트를 사용할 수 있습니다.  그러나 또한 수 있습니다, 사용 가능 하 게 하는 프로젝트 항목 구성 종속성 속성을 사용 합니다.  프로젝트 내에서 파일 올바르게 빌드되는 것으로 다른 컴파일러 스위치가 설정 해야 할 경우이 기능을 사용할 수 있습니다.  
  
## 속성 페이지를 사용 하 여  
 속성 페이지가 표시 됩니다 \(예를 들어, 프로젝트에 솔루션\)에서 선택 영역을 변경할 경우 정보 페이지에 새 선택 영역에 대 한 속성을 표시 하려면 변경 내용 표시.  속성 페이지는 속성 페이지를 지 원하는 개체에 속성이 있는 경우 비어 있습니다.  
  
 여러 객체가 선택 된 경우 선택된 된 모든 항목에 대 한 속성의 교차 속성 페이지를 표시 합니다.  선택한 항목 구성 종속 속성을 포함 하지 경우 및 해당  **속성 페이지** 솔루션 탐색기 도구 모음에서 단추를 클릭 하 고 포커스를 속성 창으로 변경 합니다.  속성 창 및 선택에 관한 자세한 내용은 참조 하십시오. [속성 확장](../../extensibility/internals/extending-properties.md).  
  
 속성 페이지에서 값을 변경할 경우 여러 개체에 대 한 속성이 표시 됩니다 모든 개체에 대 한 값을 새 값으로 처음부터 다릅니다 하 고 개별 개체의 속성에 표시 된 경우 페이지는 비워 둘 수 없습니다 경우에 설정 됩니다.  
  
 두 가지 유형의  **프로젝트속성 페이지** 대화 상자에서 사용할 수 있는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  Visual Basic 프로젝트의 첫 번째에서 예를 들어, 속성 페이지 필드 형식을 사용 하 여 다음 스크린샷에서 볼 수 있는 것 처럼 표시 됩니다.  둘째, 나중에이 섹션에서이 속성 페이지 호스트 속성 표의 속성 창에서 찾을 수와 마찬가지로 표시.  
  
 ![Visual Basic 속성 페이지](~/extensibility/internals/media/vsvbproppages.gif "vsVBPropPages")  
프로젝트 속성 페이지 대화 상자와 필드 형식 및 트리 구조  
  
 속성 페이지 대화 상자에서 트리 구조를 사용 하 여 기본 제공 되지 않습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>.  에 의해 전달 된 수준 이름 기반 환경에서의 <xref:Microsoft.VisualStudio.OLE.Interop.ISpecifyPropertyPages> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPropertyPage> 인터페이스를 빌드할 때.  
  
 사용할 수 있는 두 개의 최상위 범주 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 속성 페이지:  
  
-   공용 속성, 선택된 된 개체를 개체의 구성에 관계 없이 정보를 표시 합니다.  따라서 구성, 플랫폼과 구성 관리자 옵션이 대화 상자 상단에 가로로 공용 속성 하위 범주 중 하나를 선택 하면 사용할 수 없습니다.  
  
-   구성 속성, 디버깅, 최적화, 및 빌드 매개 변수를 해당 솔루션 또는 프로젝트와 관련 된 구성 종속성 정보가 있는.  
  
 추가 최상위 범주를 만들 수는 없지만 나의 구현에 표시 하도록 선택할 수 있습니다 `IVsPropertyPage`.  예를 들어, 개체를 표시 하는 구성 독립적 속성 없는 경우의 공용 속성 범주를 표시 하지 않도록 선택할 수 있습니다.  경우 일반적인 속성을 표시 `ISpecifyPropertyPages` 찾아보기 개체의 항목 및 구성 속성을 구현할 때 구현 됩니다 `ISpecifyPropertyPages` 구성 개체에 \(개체 구현 `IVsCfg`, `IVsProjectCfg`, 및 인터페이스 관련\).  
  
 최상위 범주 아래에 표시 된 각 항목은 별도 속성 페이지를 나타냅니다.  범주 및 하위 범주 항목 사용할 수 있는 대화 상자에서를 구현에서 결정 `ISpecifyPropertyPages` 및 `IVsPropertyPage`.  
  
 `IDispatch`개체 속성 페이지 구현에 표시 되는 속성을 가진 항목에서 선택 항목 컨테이너에 대 한 `ISpecifyPropertyPages` 클래스 Id의 목록을 열거 합니다.  클래스 Id 변수에 전달 `ISpecifyPropertyPages` 속성 페이지 인스턴스화하려면 사용 되 고 있습니다.  클래스 Id의 목록에도 전달 된 `IVsPropertyPage` 대화 상자 왼쪽의 트리 구조를 만들 수 있습니다.  속성 페이지 다음 암호 정보를 백업 하는 `IDispatch` 을 구현 하는 개체 `ISpecifyPropertyPages` 및 각 페이지에 대 한 정보로 채웁니다.  
  
 찾아보기 개체의 속성을 사용 하 여 검색 된 `IDispatch` 선택 컨테이너의 각 개체에 대 한.  
  
 구현 `Help::DisplayTopicFromF1Keyword` 하면 Vspackage를 도움말 단추에 대 한 기능을 제공 합니다.  
  
 자세한 내용은 참조 하십시오. `IDispatch` 및 `ISpecifyPropertyPages`MSDN 라이브러리에서입니다.  
  
 속성 페이지의 두 번째 종류 샘플 호스트에서 다음 스크린 샷에서 처럼 속성 모눈의 폼을 표시.  
  
 ![VC 속성 페이지](~/extensibility/internals/media/vsvcproppages.gif "vsVCPropPages")  
속성 표 형태 창에 속성 페이지 대화 상자  
  
 인터페이스 `IVSMDPropertyBrowser` 및 `IVSMDPropertyGrid` \(vsmanaged.h에서 선언\) 만들고 속성 표 창 또는 대화 상자를 채우는 데 사용 됩니다.  
  
 프로젝트의 아키텍처를 훨씬 이전 버전에서 변경 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  특히, 어떤 프로젝트에 대 한 개념이 활성화 되어 변경 되었습니다.  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 현재 프로젝트의 개념이 없습니다.  이전 개발 환경에서 활성 프로젝트 컨텍스트에 관계 없이 프로젝트를 빌드 및 배포 명령을 기본 것입니다.  이제 솔루션을 제어 하 고 arbitrates 빌드 및 배포 명령을 어떤 프로젝트에 적용 됩니다.  
  
 어떤 이전에 현재 프로젝트 되었습니다 이제 세 가지 방법 중 하나에 캡처됩니다.  
  
-   시작 프로젝트  
  
     하나 이상의 사용자가 f5 키를 누르거나 빌드 메뉴에서 실행을 선택 하면 시작 됩니다 솔루션의 속성 페이지에서 프로젝트를 지정할 수 있습니다.  이 이름 솔루션 탐색기에서 굵은 글꼴로 표시 됩니다 있다는 점에서 이전 활성 프로젝트와 비슷한 방식으로 작동 합니다.  
  
     시작 프로젝트 자동화 모델에서 속성으로 호출 하 여 검색할 수 있는 `DTE.Solution.SolutionBuild.StartupProjects`.  있는 Vspackage를 호출 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager2.get_StartupProject%2A> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager2.get_StartupProject%2A> 방법입니다.  `IVsSolutionBuildManager`서비스에서 사용할 수 있습니다 `QueryService` sid\_svssolutionbuildmanager에 있습니다.  자세한 내용은 [프로젝트 구성 개체](../../extensibility/internals/project-configuration-object.md) 및 [솔루션 구성](../../extensibility/internals/solution-configuration.md)을 참조하십시오.  
  
-   활성 솔루션 빌드 구성  
  
     [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]자동화 모델을 구현 하 여 사용할 수 있는 활성 솔루션 구성에 있는 `DTE.Solution.SolutionBuild.ActiveConfiguration`.  솔루션 구성 \(각 프로젝트 여러 구성 이름이 서로 다른 여러 플랫폼에서 있을 수 있습니다\) 솔루션의 각 프로젝트에 대해 프로젝트 구성을 포함 하는 컬렉션입니다.  솔루션의 속성 페이지에 관한 자세한 내용은 참조 하십시오. [솔루션 구성](../../extensibility/internals/solution-configuration.md).  
  
-   현재 선택한 프로젝트  
  
     구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCurrentSelection%2A> 항목을 선택 하 고 프로젝트 항목을 프로젝트 계층 구조를 검색 하는 방법입니다.  DTE에서 사용 하는 `SelectedItems.SelectedItem.Project` 및 `SelectedItems.SelectedItem.ProjectItem` 방법.  예제 코드의 핵심에 해당 머리글 아래는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 문서입니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPropertyPage>   
 [구성 옵션 관리](../../extensibility/internals/managing-configuration-options.md)   
 [프로젝트 구성 개체](../../extensibility/internals/project-configuration-object.md)   
 [솔루션 구성](../../extensibility/internals/solution-configuration.md)