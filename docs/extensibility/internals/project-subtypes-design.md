---
title: "프로젝트 하위 형식 디자인 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "하위 프로젝트 디자인"
ms.assetid: 405488bb-1362-40ed-b0f1-04a57fc98c56
caps.latest.revision: 32
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 32
---
# 프로젝트 하위 형식 디자인
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트 하위 Vspackages를 Microsoft 빌드 엔진에서 \(MSBuild\)를 기준으로 프로젝트를 확장할 수 있습니다.  집계를 사용 하는 구현 된 핵심 관리 하는 프로젝트 시스템의 대부분을 다시 사용할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 는 아직 여전히 특정 시나리오에 대 한 동작을 사용자 지정 합니다.  
  
 다음 항목에서는 기본 설계 및 구현 하는 하위 프로젝트를 자세히 소개합니다.  
  
-   프로젝트 하위 형식 디자인입니다.  
  
-   여러 수준의 집계 합니다.  
  
-   인터페이스를 지원 해야 합니다.  
  
## 프로젝트 하위 형식 디자인  
 프로젝트 하위 형식 초기화 주를 집계 하 여 얻을 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject> 개체입니다.  이 집계는 프로젝트 하위 형식을 재정의 하거나 대부분의 기본 프로젝트의 기능을 향상 시킬 수 있습니다.  프로젝트 하위 속성을 사용 하 여 처리 하는 첫 번째 기회가 가져옵니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>, 명령을 사용 하 여 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>, 프로젝트 관리 항목을 사용 하 고 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>.  프로젝트 하위 형식을 확장할 수도 있습니다.  
  
-   프로젝트 구성 개체입니다.  
  
-   구성 종속성 개체입니다.  
  
-   구성에 관계 없이 찾아보기 개체입니다.  
  
-   프로젝트 자동화 개체입니다.  
  
-   프로젝트 자동화 속성 컬렉션입니다.  
  
 확장성 프로젝트 하위 형식에 대 한 자세한 내용은 [속성 및 프로젝트 하위 형식에 의해 확장 메서드](../../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md).  
  
##### 정책 파일  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 환경에서 정책 파일을 구현 프로젝트 하위 형식에는 기본 프로젝트 시스템을 확장 하는 예제를 제공 합니다.  세공의 정책 파일을 허용의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 솔루션 탐색기에서 포함 하는 기능을 관리 환경  **프로젝트 추가** 대화 상자를  **새 항목 추가** 대화 상자 및 해당  **속성** 대화 상자.  정책 하위 형식을 무시 하 고 이러한 기능을 통해 개선 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg>, `IOleCommandTarget` 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 구현 합니다.  
  
##### 집계 메커니즘  
 환경 프로젝트 하위 집계 메커니즘을 여러 수준의 flavored 프로젝트를 더 이상 flavoring에서 구현 해야 하는 고급 하위 하므로 집계를 지원 합니다.  하위 또한 프로젝트 지원 개체, 같은 형식 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg>, 계층의 여러 수준 있도록 설계 되었습니다.  COM과 COM의 제약 조건에 집계 규칙, 프로젝트 하위 유형 및 기본 프로젝트 협조 내부 하위 형식 또는 기본 프로젝트 메서드 호출을 위임 하 고 참조 횟수를 관리 제대로 참여할 수 있도록 프로그래밍 해야 합니다.  즉, 프로젝트에 대 한 집계를 집계를 지원 하도록 프로그래밍 될 수 있습니다.  
  
 다음 그림에서는 도식을 다중 프로젝트 하위 집계를 보여 줍니다.  
  
 ![Visual Studio 다중 수준 projectflavor 그래픽](../../extensibility/internals/media/vs_multilevelprojectflavor.gif "VS\_MultilevelProjectFlavor")  
여러 수준의 프로젝트 하위 유형  
  
 다중 프로젝트 하위 집계 프로젝트 하위 형식으로 집계 하 고가 고급 프로젝트 하위 형식에 따라 추가로 집계는 기본 프로젝트를 세 가지 수준에서 구성 됩니다.  그림 일부 지원의 일부로 서 제공 하는 인터페이스에 중점을 두고는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 하위 형식 아키텍처 프로젝트입니다.  
  
##### 배포 메커니즘  
 대부분의 기본 프로젝트 시스템에서 프로젝트 하위에서 강화 된 기능 배포 메커니즘입니다.  구성 인터페이스를 구현 하 여 하위 프로젝트 배포 메커니즘에 영향 \(같은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg>\)는 검색에서 Queryinterface를 호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfgProvider>.  프로젝트 하위 형식 및 고급 프로젝트 하위 유형을 모두 추가 다른 구성을 구현 하는 경우에는 기본 프로젝트를 호출 `QueryInterface` 고급 프로젝트 하위 형식에 `IUnknown`.  내부 프로젝트 하위 형식에 대 한 기본 프로젝트를 묻는 구성 구현을 포함 하는 경우 내부 프로젝트 하위 형식에 따라 제공 하는 구현은 고급 프로젝트 하위 형식에 위임 합니다.  집계 수준 상태로 유지 하기 위한 메커니즘으로 프로젝트 하위의 모든 수준을 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> 빌드 기능을 유지 하는 프로젝트 파일에 XML 데이터 관련.  자세한 내용은 [MSBuild 프로젝트 파일에 데이터를 유지](../../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)를 참조하십시오.  <xref:EnvDTE80.IInternalExtenderProvider>extender를 자동화 프로젝트 하위에서 검색 하는 메커니즘으로 구현 됩니다.  
  
 다음 그림은 프로젝트 구성 찾아보기 개체 자동화 extender 구현에 프로젝트 하위 형식에서 사용 되는 기본 프로젝트 시스템을 확장할 수 특히, 주로 설명 합니다.  
  
 ![VS 프로젝트 버전 자동 Extender 그래픽](../../extensibility/internals/media/vs_projectflavorautoextender.png "VS\_ProjectFlavorAutoExtender")  
프로젝트 하위 자동화 Extender입니다.  
  
 하위 프로젝트의 자동화 개체 모델을 확장 하 여 기본 프로젝트 시스템 추가로 확장할 수 있습니다.  이러한 DTE 자동화 개체의 일부로 정의 되 고 프로젝트 개체를 확장 하는 데 사용 됩니다는 `ProjectItem` 개체 및 해당 `Configuration` 개체입니다.  자세한 내용은 [기본 프로젝트의 개체 모델 확장](../../extensibility/internals/extending-the-object-model-of-the-base-project.md)을 참조하십시오.  
  
## 여러 수준의 집계  
 낮은 수준의 프로젝트 하위 형식을 래핑하는 프로젝트 하위 형식을 구현 방식의 내부 프로젝트 하위 형식을 올바르게 작동할 수 있도록 프로그래밍 해야 합니다.  책임 프로그래밍의 목록은 다음과 같습니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> 내부 하위 형식에 배치 되는 프로젝트 하위 형식의 구현에 위임 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> 내부 프로젝트 하위 형식의 구현을 모두에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.Load%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.Save%2A> 방법입니다.  
  
-   <xref:EnvDTE80.IInternalExtenderProvider> 래퍼 프로젝트 하위 형식 구현에서는 해당 내부 프로젝트 하위에 위임 해야 합니다.  특히, 구현 <xref:EnvDTE80.IInternalExtenderProvider.GetExtenderNames%2A> 이름 문자열 내부 프로젝트 하위에서 가져오고 다음 원하는 확장자로 추가 하 여 문자열을 연결 해야 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfgProvider> 래퍼 프로젝트 하위 형식 구현 해야 인스턴스화의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg> 개체의 내부를 하위 프로젝트와 프로젝트의 기본 프로젝트 구성을 개체 에서만 직접 래퍼 프로젝트 하위 구성 개체가 있는지 알 수 있으므로 개인 대리인으로 채.  외부 프로젝트 하위 형식을 처음에 직접 처리 하기를 원하는 구성 인터페이스를 선택 하 고 나머지의 내부 프로젝트 하위 형식 구현 하 고 위임할 수 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg.get_CfgType%2A>.  
  
## 인터페이스를 지 원하는  
 기본 프로젝트의 구현과 다양 한 측면을 확장 하는 프로젝트 하위 형식에 따라 추가 인터페이스 지원 호출을 위임 합니다.  여기에 다양 한 속성 브라우저가 개체와 프로젝트 구성 개체를 확장 합니다.  이러한 인터페이스를 호출 하 여 검색 된 `QueryInterface` 에서 `punkOuter` \(에 대 한 포인터를 `IUnknown`\) 바깥쪽 프로젝트 하위 집계를 합니다.  
  
|Interface|프로젝트 하위|  
|---------------|-------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg>|프로젝트 하위 형식을으로 수행할 수 있습니다.<br /><br /> -   <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg>에 대한 구현을 제공합니다.<br />-   프로젝트 하위의 자체 구현을 제공 하도록 허용 하 여 디버거에서 시작 제어 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>.<br />-   적절 하 게 처리 하 여 디자인 타임 식 계산이 비활성화는 `DBGLAUNCH_DesignTimeExprEval` 에서 구현 사례 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg.QueryDebugLaunch%2A>.|  
|<xref:EnvDTE80.IInternalExtenderProvider>|프로젝트 하위 형식을으로 수행할 수 있습니다.<br /><br /> -   확장은 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> 프로젝트를 추가 하거나 프로젝트 구성 독립적 속성을 제거 합니다.<br />-   Project 자동화 개체는 확장 \(<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>\) 프로젝트의.<br /><br /> 위의 속성 값에서 결정 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> 열거형입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>|프로젝트 하위 형식을 다시 매핑할 수 있습니다 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg> 프로젝트 구성 찾아보기 개체를 지정 하는 개체입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsBrowseObject>|프로젝트 하위 형식을 다시 매핑할 수 있습니다의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 또는 `VSITEMID` 프로젝트 구성 찾아보기 개체를 지정 된 개체를 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment>|프로젝트 하위를 프로젝트 파일 \(.vbproj 또는.csproj\) 임의의 구조화 된 XML 데이터를 유지할 수 있습니다.  이 데이터는 Msbuild에 표시 되지 않습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage>|프로젝트 하위 형식을으로 수행할 수 있습니다.<br /><br /> -   유지할 새 MSBuild 속성을 추가 합니다.<br />-   Msbuild에서 필요 없는 속성을 제거 합니다.<br />-   MSBuild 속성의 현재 값에 대 한 쿼리.<br />-   MSBuild 속성의 현재 값을 변경 합니다.|  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID2>