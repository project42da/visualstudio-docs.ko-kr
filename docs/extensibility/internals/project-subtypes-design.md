---
title: 프로젝트 디자인 하위 유형 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- project subtypes, design
ms.assetid: 405488bb-1362-40ed-b0f1-04a57fc98c56
caps.latest.revision: 32
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 126bee146d1f53233db3c14672f80da4c0d60e9e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="project-subtypes-design"></a>프로젝트 하위 형식 디자인
Microsoft Build Engine (MSBuild)에 따라 프로젝트를 확장 하는 Vspackage를 사용 하는 프로젝트 하위 형식입니다. 집계 사용 하면 대량의에서 구현 되는 핵심 관리 되는 프로젝트 시스템을 다시 사용할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 하면서도 여전히 특정 시나리오에 대 한 동작을 사용자 지정 합니다.  
  
 기본 디자인 및 구현 프로젝트 하위 형식에 설명 하는 다음 항목:  
  
-   프로젝트 하위 형식 디자인 합니다.  
  
-   여러 수준의 집계입니다.  
  
-   인터페이스를 지원합니다.  
  
## <a name="project-subtype-design"></a>프로젝트 하위 형식 디자인  
 프로젝트 하위 형식 초기화 하는 기본 집계 하 여 이루어집니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject> 개체입니다. 이 집계 프로젝트 하위 형식을 재정의 하거나 대부분의 기본 프로젝트의 기능을 향상 시킬 수 있습니다. 프로젝트 하위 형식 속성을 사용 하 여 처리를 첫 번째 기회가 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>를 사용 하 여 명령을 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>, 사용 하 여 프로젝트 항목 관리 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>합니다. 프로젝트 하위 형식 확장할 수도 있습니다.  
  
-   구성 개체를 프로젝션 합니다.  
  
-   구성에 종속 된 개체입니다.  
  
-   구성에 관계 없이 찾아보기 개체입니다.  
  
-   자동화 개체를 프로젝션 합니다.  
  
-   자동화 속성 컬렉션을 프로젝션 합니다.  
  
 확장성 프로젝트 하위 형식에 대 한 자세한 내용은 참조 하십시오. [속성 및 메서드 프로젝트 하위 형식에 의해 확장](../../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)합니다.  
  
##### <a name="policy-files"></a>정책 파일  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 환경 프로젝트 하위 형식 정책 파일의 구현에서 사용 하 여 기본 프로젝트 시스템을 확장 하는 예제를 제공 합니다. 정책 파일의 모양 지정을 사용 하 여 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 솔루션 탐색기에서 솔루션을 포함 하는 기능을 관리 하 여 환경 **프로젝트 추가** 대화 상자, **새 항목 추가** 대화 상자와  **속성** 대화 상자. 정책 하위 유형 재정의 하 고 이러한 기능을 통해 향상 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg>, `IOleCommandTarget` 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 구현 합니다.  
  
##### <a name="aggregation-mechanism"></a>집계 메커니즘  
 환경의 프로젝트 하위 형식 집계 메커니즘에는 추가 flavoring 버전이 지정 된 프로젝트에서 구현 하는 고급 하위 형식 수 있도록 하는 집계의 여러 수준을 지원 합니다. 또한 지원 개체는 프로젝트의 하위 형식, 같은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg>은 여러 수준의 쌓기 수 있도록 설계 되었습니다. COM 및 COM의 제약 조건에 따라 집계 규칙, 프로젝트 하위 형식 및 기본 프로젝트 할 내부 하위 형식 또는 기본 프로젝트 제대로 메서드 호출을 위임 하 고 관리 참조 횟수에 참여할 수 있도록 협조적으로 프로그래밍할 수 . 즉, 집계를 지원 하도록 프로그래밍할 수를 집합체를 허용 하려고 합니다. 프로젝트에 있습니다.  
  
 다음 그림에는 여러 수준의 프로젝트 하위 형식 집계의 표현식 보여 줍니다.  
  
 ![Visual Studio 다중 수준 projectflavor 그래픽](../../extensibility/internals/media/vs_multilevelprojectflavor.gif "VS_MultilevelProjectFlavor")  
다단계 프로젝트 하위 형식  
  
 여러 수준의 프로젝트 하위 형식 집계 프로젝트 하위 형식에서 집계 하는 고급 프로젝트 하위 형식에서 더 이상 집계 되는 기본 프로젝트, 세 가지 수준으로 구성 됩니다. 일부 지원의 일부로 제공 되는 인터페이스에 중점을 두고 그림은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 하위 형식 아키텍처.  
  
##### <a name="deployment-mechanisms"></a>배포 메커니즘  
 속하는 기본 프로젝트 시스템의 많은 프로젝트 하위 형식에서 향상 된 기능에는 배포 메커니즘입니다. 프로젝트 하위 형식 구성 인터페이스를 구현 하 여 배포 메커니즘에 영향을 줍니다 (예: <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg>)에서 QueryInterface를 호출 하 여 검색 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfgProvider>합니다. 기본 프로젝트 프로젝트 하위 형식 및 고급 프로젝트 하위 형식 모두이 다른 구성 구현을 추가 하는 시나리오에서 호출 `QueryInterface` 고급 프로젝트 하위 형식 `IUnknown`합니다. 내부 프로젝트 하위 형식에 대 한 기본 프로젝트를 요청 하는 구성 구현 들어 있는 경우 고급 프로젝트 하위 형식 내부 프로젝트 하위 형식에서 제공 하는 구현에 위임 합니다. 다른 하나의 집계 수준에서 상태를 유지 하는 메커니즘, 프로젝트 하위 형식 수준의 모든 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> 프로젝트 파일에 관련 된 XML 데이터를 비 빌드를 유지 합니다. 자세한 내용은 참조 [MSBuild 프로젝트 파일의 데이터를 유지할 수 있도록](../../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)합니다. <xref:EnvDTE80.IInternalExtenderProvider>automation extender 프로젝트 하위 형식에서 검색 하는 메커니즘으로 구현 됩니다.  
  
 다음 그림에 집중 자동화 extender 구현 프로젝트 구성 찾아보기 개체 특히, 프로젝트 하위 형식에서 기본 프로젝트 시스템을 확장 하는 데 사용 합니다.  
  
 ![VS 프로젝트 버전 자동 Extender 그래픽](../../extensibility/internals/media/vs_projectflavorautoextender.gif "VS_ProjectFlavorAutoExtender")  
프로젝트 하위 형식 Automation Extender입니다.  
  
 더욱 프로젝트 하위 형식 자동화 개체 모델을 확장 하 여 기본 프로젝트 시스템을 확장할 수 있습니다. 이러한 DTE 자동화 개체의 일부로 정의 되 고 프로젝트 개체를 확장 하는 데 사용 되는 `ProjectItem` 개체 및 `Configuration` 개체입니다. 자세한 내용은 참조 하십시오 [기본 프로젝트의 개체 모델을 확장](../../extensibility/internals/extending-the-object-model-of-the-base-project.md)합니다.  
  
## <a name="multi-level-aggregation"></a>여러 수준의 집계  
 더 낮은 수준 프로젝트 하위 형식에서 래핑하는 프로젝트 하위 형식 구현 제대로 작동 하려면 내부 프로젝트 하위 형식 수 있도록 협조적으로 프로그래밍할 수 있어야 합니다. 책임 프로그래밍의 목록이 포함 되어 있습니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> 를 내부 하위 형식에 배치 되는 프로젝트 하위 형식의 구현 대리자로 위임 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> 내부 프로젝트 하위 형식 모두에 대 한 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.Load%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.Save%2A> 메서드.  
  
-   <xref:EnvDTE80.IInternalExtenderProvider> 를 그 내부 프로젝트 하위 유형이의 래퍼 프로젝트 하위 형식의 구현 대리자로 위임 해야 합니다. 특히, 구현의 <xref:EnvDTE80.IInternalExtenderProvider.GetExtenderNames%2A> 내부 프로젝트 하위 형식에서 이름 문자열을 가져오고 다음 extender로 추가 하려는 문자열을 연결 해야 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfgProvider> 래퍼 프로젝트 하위 구현 인스턴스화해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg> 개체의 내부 하위 프로젝트를 누른 상태 개인 대리자로 하므로 기본 프로젝트의 프로젝트 구성 개체 직접 한다는 사실을 알고 있으면만 래퍼 프로젝트 하위 형식 구성 개체가 있습니다. 외부 프로젝트 하위 형식에서 처음를 직접 처리 하는 구성 인터페이스를 선택 하 고 다음 나머지의 내부 프로젝트 하위 형식 구현에 위임할 수 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg.get_CfgType%2A>합니다.  
  
## <a name="supporting-interfaces"></a>인터페이스를 지원합니다.  
 기본 프로젝트 구현의 다양 한 측면을 확장 하는 프로젝트 하위 형식으로 추가 된 인터페이스를 지원 하기 위해 호출을 위임 합니다. 여기에 프로젝트 구성 개체 및 다양 한 속성 브라우저 개체를 확장 합니다. 이러한 인터페이스를 호출 하 여 검색 됩니다 `QueryInterface` 에 `punkOuter` (에 대 한 포인터는 `IUnknown`)의 가장 바깥쪽 프로젝트 하위 형식 aggregator 합니다.  
  
|인터페이스|프로젝트 하위 형식|  
|---------------|---------------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg>|프로젝트 하위 형식에 허용 됩니다.<br /><br /> -의 구현을 제공 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg>합니다.<br />-프로젝트 하위 형식의 자체 구현을 제공 하도록 허용 하 여 디버거 시작을 제어 합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>합니다.<br />-적절 하 게 처리 하 여 디자인 타임 식 계산이 비활성화는 `DBGLAUNCH_DesignTimeExprEval` 구현에서 사례 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg.QueryDebugLaunch%2A>합니다.|  
|<xref:EnvDTE80.IInternalExtenderProvider>|프로젝트 하위 형식에 허용 됩니다.<br /><br /> 확장 된 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> 추가 하거나 프로젝트의 구성 독립 속성을 제거 하려면 프로젝트의 합니다.<br />--프로젝트 자동화 개체를 확장 하는 중 (<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>) 프로젝트.<br /><br /> 위의 속성 값에서 가져옵니다 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> 열거 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>|프로젝트 하위 형식에 다시 매핑할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg> 프로젝트 구성 찾아보기 개체가 지정한 개체입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsBrowseObject>|프로젝트 하위 형식에 다시 매핑할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 또는 `VSITEMID` 프로젝트 구성 찾아보기 개체가 지정 된 개체입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment>|프로젝트 파일 (.csproj 또는.vbproj)에 임의의 구조화 된 XML 데이터를 유지 하도록 프로젝트 하위 형식을 수 있습니다. 이 데이터 MSBuild로 표시 되지 않습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage>|프로젝트 하위 형식에 허용 됩니다.<br /><br /> -유지 되도록 새 MSBuild 속성을 추가 합니다.<br />-MSBuild에서 불필요 한 속성을 제거 합니다.<br />MSBuild 속성의 현재 값에 대 한 쿼리 합니다.<br />-MSBuild 속성의 현재 값을 변경 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID2>