---
title: 속성 페이지 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- configuration options, changing properties
- property pages
- property pages, changing configuration options
ms.assetid: b9b3e6e8-1e30-4c89-9862-330265dcf38c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1b08e210a57388d77859600c02c0e6a30a404884
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="property-pages"></a>속성 페이지
사용자가 볼 수 있고 속성 페이지를 사용 하 여 프로젝트 구성에 종속 된 매개 변수와-독립적인 속성을 변경 합니다. A **속성 페이지** 에서 단추를 사용할 수는 **속성** 창 또는 선택된 된 개체의 속성 페이지 보기를 제공 하는 개체에 대 한 솔루션 탐색기 도구 모음입니다. 속성 페이지에는 솔루션 및 프로젝트에 사용할 수 있는 및 환경에 의해 만들어집니다. 그러나도 사용할 수는 구성에 종속 된 속성을 사용 하는 프로젝트 항목에 대 한 사용 가능 합니다. 프로젝트 내에서 파일을 다른 컴파일러 스위치 설정을 올바르게 빌드되려면 필요로 할 때이 기능을 사용할 수도 있습니다.  
  
## <a name="using-property-pages"></a>속성 페이지를 사용 하 여  
 속성 페이지가 표시 되는 이미 하 고 새 선택에 대 한 속성을 표시 하려면 페이지 변경 내용에서 표시 되는 정보 (예를 들어 솔루션에서 프로젝트에), 선택 영역이 변경 합니다. 개체의 속성 페이지를 지 원하는 속성을 속성 페이지 비어 있습니다.  
  
 여러 개체를 선택 하는 경우 선택한 모든 항목에 대 한 속성의 교집합 속성 페이지에 표시 됩니다. 선택한 항목이 구성 종속성 속성을 포함 하지 않으면 경우 및 **속성 페이지** 속성 창에 포커스가 변경, 솔루션 탐색기 도구 모음 단추를 클릭 합니다. 속성 창 및 선택 영역에 관련 된 자세한 내용은 참조 하십시오. [확장 속성](../../extensibility/internals/extending-properties.md)합니다.  
  
 여러 개체에 대 한 속성이 표시 됩니다. 속성 페이지에서 값을 변경 하면을 처음에 서로 다른 것 되었으며 페이지 빈 개별 개체의 속성이 표시 된 경우에 새 값으로 설정 됩니다 모든 개체에 대 한 값.  
  
 두 가지 유형의 없는 **ProjectProperty 페이지** 대화 상자에서 사용할 수 있는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. Visual Basic 프로젝트에 대 한 첫 번째 예를 들어 속성 페이지는 표시 필드 형식을 사용 하 여 다음 스크린 샷에 표시 된 것 처럼. 두 번째는 뒷부분에 나오는 속성이 단원의 페이지 호스트 속성 표에서 속성 창에 있는 것과 유사한 합니다.  
  
 ![Visual Basic 속성 페이지](../../extensibility/internals/media/vsvbproppages.gif "vsVBPropPages")  
프로젝트 속성 페이지 대화 상자 필드 형식과 트리 구조를  
  
 속성 페이지 대화 상자에서 트리 구조를 사용 하 여 기본 제공 되지 않는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>합니다. 환경에 의해 전달 된 수준 이름에 따라는 <xref:Microsoft.VisualStudio.OLE.Interop.ISpecifyPropertyPages> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPropertyPage> 인터페이스, 빌드합니다.  
  
 두 개의 최상위 범주에서 사용할 수 있는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 속성 페이지:  
  
-   공용 속성, 선택한 개체 또는 개체에 대 한 구성에 관계 없이 정보를 표시 합니다. 결과적으로, 공용 속성 하위 범주 중 하나를 선택 하는 경우 구성, 플랫폼 및 Configuration Manager 옵션 대화 상자의 위쪽에 사용할 수 없는 경우  
  
-   솔루션 또는 프로젝트에 대 한 디버깅, 최적화 및 빌드 매개 변수와 관련 된 하는 구성에 종속 된 정보가 들어 있는 구성 속성입니다.  
  
 추가 최상위 범주를 만들 수는 없지만 구현에서 둘 중 하나를 표시 하지 않도록 선택할 수 `IVsPropertyPage`합니다. 예를 들어 하지 않은 경우 모든 구성에 관계 없이 속성을 개체에 대 한 표시를 공용 속성 범주를 표시 하지 않도록 선택할 수 있습니다. 경우에 공용 속성을 표시 `ISpecifyPropertyPages` 구현할 때 항목의 찾아보기 개체 및 구성 속성에서 구현 됩니다 `ISpecifyPropertyPages` 구성 개체에 (구현 하는 개체 `IVsCfg`, `IVsProjectCfg`, 및 관련 인터페이스)입니다.  
  
 최상위 범주 아래에 표시 된 각 범주에는 별도 속성 페이지를 나타냅니다. Category 및 subcategory 사용할 수 있는 항목 대화 상자에서의 구현에 따라 결정 됩니다 `ISpecifyPropertyPages` 및 `IVsPropertyPage`합니다.  
  
 `IDispatch` 속성 페이지 구현에 대해 표시할 속성을 가진 선택 항목 컨테이너의 항목에 대 한 개체 `ISpecifyPropertyPages` 클래스 Id의 목록을 열거할 수 있습니다. 클래스 Id를 변수로 전달 된 `ISpecifyPropertyPages` 및 속성 페이지를 인스턴스화하는 데 사용 됩니다. 클래스 Id의 목록에 전달 됩니다 `IVsPropertyPage` 대화 상자의 왼쪽의 트리 구조를 생성 합니다. 속성 페이지 다음 패스 정보로 다시는 `IDispatch` 구현 하는 개체 `ISpecifyPropertyPages` 하 고 각 페이지에 대 한 정보로 채워집니다.  
  
 사용 하 여 찾아보기 개체의 속성이 검색 `IDispatch` 선택 컨테이너에 있는 각 개체에 대 한 합니다.  
  
 구현 `Help::DisplayTopicFromF1Keyword` VSPackage의 도움말 단추에 대 한 기능을 제공 합니다.  
  
 자세한 내용은 참조 하십시오. `IDispatch` 및 `ISpecifyPropertyPages`MSDN 라이브러리에서.  
  
 두 번째 유형의 속성 페이지에에서 표시 샘플 호스트 속성 표 형태의 다음 스크린샷에 표시 된 것 처럼.  
  
 ![VC 속성 페이지](../../extensibility/internals/media/vsvcproppages.gif "vsVCPropPages")  
속성 그리드와 속성 페이지 대화 상자  
  
 인터페이스 `IVSMDPropertyBrowser` 및 `IVSMDPropertyGrid` (vsmanaged.h에서 선언 됨)를 만들고 대화 상자 또는 창 내에서 속성 그리드를 채울 하는 데 사용 됩니다.  
  
 프로젝트의 아키텍처는 이전 버전의에서 크게 변경 되었습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 특히 어떤 프로젝트의 개념은 활성 변경 되었습니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 현재 프로젝트의 개념이 없습니다. 와 이전 개발 환경에서는 현재 프로젝트 컨텍스트에 관계 없이 프로젝트를 빌드하고 배포 명령을 기본적으로 했습니다. 이제 솔루션 제어를 구축 하 고 배포 명령을 arbitrates 되는 프로젝트에 적용 합니다.  
  
 활성 프로젝트가 이전에 였습니까 필드가 이제 세 가지 방법 중 하나에 캡처됩니다.  
  
-   시작 프로젝트  
  
     프로젝트 또는 F5 키를 누르거나 빌드 메뉴에서 실행을 선택할 때 시작 될 솔루션의 속성 페이지에서 프로젝트를 지정할 수 있습니다. 굵은 글꼴로 이름을 솔루션 탐색기에 표시 되도록 의미에서 오래 된 활성 프로젝트에 분산 됩니다.  
  
     호출 하 여 자동화 모델의 속성으로 시작 프로젝트를 검색할 수 있습니다 `DTE.Solution.SolutionBuild.StartupProjects`합니다. 호출 vspackage에서는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager2.get_StartupProject%2A> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager2.get_StartupProject%2A> 메서드. `IVsSolutionBuildManager` 사용 하 여 서비스로 사용할 수 `QueryService` SID_SVsSolutionBuildManager에 있습니다. 자세한 내용은 참조 [프로젝트 구성 개체](../../extensibility/internals/project-configuration-object.md) 및 [솔루션 구성](../../extensibility/internals/solution-configuration.md)합니다.  
  
-   활성 솔루션 빌드 구성  
  
     [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 구현 하 여 자동화 모델에서 사용할 수 있는 활성 솔루션 구성에 `DTE.Solution.SolutionBuild.ActiveConfiguration`합니다. 솔루션 구성은 (각 프로젝트 들어 여러 구성이 서로 다른 이름으로 여러 플랫폼에서 있을 수 있습니다) 솔루션의 각 프로젝트에 대 한 하나의 프로젝트 구성을 포함 하는 컬렉션. 솔루션의 속성 페이지와 관련 된 자세한 내용은 참조 하십시오. [솔루션 구성](../../extensibility/internals/solution-configuration.md)합니다.  
  
-   현재 선택 된 프로젝트  
  
     구현 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCurrentSelection%2A> 프로젝트 계층 구조 및 프로젝트 항목 또는 선택 된 항목을 검색 하는 메서드입니다. DTE를에서 사용 된 `SelectedItems.SelectedItem.Project` 및 `SelectedItems.SelectedItem.ProjectItem` 메서드. 코어에서 이러한 머리글 아래 샘플 코드는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 문서.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPropertyPage>   
 [구성 옵션을 관리](../../extensibility/internals/managing-configuration-options.md)   
 [프로젝트 구성 개체](../../extensibility/internals/project-configuration-object.md)   
 [솔루션 구성](../../extensibility/internals/solution-configuration.md)