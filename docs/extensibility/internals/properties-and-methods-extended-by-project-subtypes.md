---
title: "속성 및 프로젝트 하위 형식에 의해 확장 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 하위 형식, 확장 메서드"
  - "프로젝트 하위 형식, 확장 속성"
ms.assetid: 2b9833bf-8551-4ae1-93db-197ba645c65e
caps.latest.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 17
---
# 속성 및 프로젝트 하위 형식에 의해 확장 메서드
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트 하위 많은 힘이 기본 프로젝트의 통합자로 만들어진 때문에 프로젝트의 동작에 영향을 미칠 수 있습니다.  이 섹션에서는 확장 하거나 프로젝트 하위 형식에서 수정할 수 있는 기능 중 일부를 요약 합니다.  
  
## 집계에서 얻은 기능  
 다음 표에서 여러 집계 기본 프로젝트에서 재정의 하려면 하위 프로젝트를 사용 하는 방법을 요약 합니다.  
  
|집계를 재정의 하는 방법|프로젝트 하위|  
|-------------------|-------------|  
|From <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>:<br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.SetProperty%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetGuidProperty%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.SetGuidProperty%2A>|프로젝트 하위 형식을으로 수 있습니다.<br /><br /> -   이름과 프로젝트 노드 아이콘을 변경 합니다.<br />-   프로젝트를 완전히 무시 `Browse` 개체입니다.<br />-   프로젝트 이름을 변경할 수 있는지 여부를 제어 합니다.<br />-   정렬 순서를 제어 합니다.<br />-   동적 도움말에 대 한 사용자 컨텍스트를 제어 합니다.|  
|From <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject>:<br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.GetItemContext%2A>|프로젝트 하위를 디자이너 및 편집기 상황에 맞는 서비스 제공을 제어할 수 있습니다.|  
|From <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>:<br /><br /> <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A><br /><br /> <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>|프로젝트 하위 형식을으로 수 있습니다.<br /><br /> -   명령에 대 한 프로젝트 명령 라우팅에 참여 합니다.<br />-   추가, 제거 또는 앰비언트 명령을 프로젝트 및 솔루션 탐색기 활성 명령을 모두 사용 하지 않도록 설정 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>|프로젝트 하위에서 사용자에 게 표시를 필터링 할 수 있는  **새 항목 추가** 대화 상자.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGeneratorFactory>|프로젝트 하위 형식을으로 수 있습니다.<br /><br /> -   파일 확장명에 지정 된 기본 생성기를 확인 합니다.<br />-   사람이 읽을 수 있는 생성기 이름을 COM 개체에 매핑하십시오.|  
  
## 프로젝트 하위 형식에서 사용 되는 속성  
 환경 및 기본 프로젝트 시스템 등록 정보에서 사용할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID> 및 <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2> 프로젝트 하위 프로젝트 시스템의 다양 한 기능을 제어할 수 있도록 다음 표에 자세하게 나와 있는 열거형입니다.  
  
|VSHPROPID 속성|프로젝트 하위|  
|------------------|-------------|  
|`AddItemTemplatesGuid`|프로젝트 하위의 내용을 제어할 수 있습니다 해당  **항목 추가** 대화 상자.  프로젝트 하위 수 있습니다 템플릿 디렉터리의 새 사양을 제공, 새로운 종류의 항목을 추가, 기존 항목을 제거 및 기본 프로젝트에 있는 항목의 하위 집합을 다시  **항목 추가** 대화 상자.|  
|`PropertyPagesCLSIDList`|프로젝트 하위 유형을 추가 하거나 구성 독립적 속성 페이지를 제거할 수 있습니다.|  
|`CfgPropertyPagesCLSIDList`|프로젝트 하위 유형을 추가 하거나 구성 종속 속성 페이지를 제거할 수 있습니다.|  
|`ExtObjectCATID`|프로젝트 하위를 자동화 Extender에 대 한 프로젝트 또는 프로젝트 항목 개체 Extender CATID를 알면 제공할 수 있습니다.  사용자 정의 프로젝트 하위 유형을 제공할 수 있습니다 예를 들어, `Project.Extender("<subtype>")` 개체입니다.|  
|`BrowseObjectCATID`|프로젝트 하위 자동화 Extender를 제공할 수 있습니다의 `Browse` 개체에서 Extender CATID를 알 수 있습니다.  프로젝트 하위 유형을 추가 속성을 추가할 수 있습니다 예를 들어 있는 <xref:EnvDTE.Project.Properties%2A> 컬렉션입니다.|  
|`CfgBrowseObjectCATID`|프로젝트 하위를 프로젝트 구성 찾아보기 개체를 자동화 하는 Extender를 제공할 수 있습니다.  프로젝트 하위 유형을 추가 속성을 추가할 수 있습니다 예를 들어 있는 <xref:EnvDTE.Configuration.Properties%2A> 컬렉션입니다.|  
|`CfgExtObjectCATID`|프로젝트 하위를 구성 개체에 대 한 자동화 Extender를 제공할 수 있습니다.|  
|`DefaultPlatformName`|프로젝트 하위를 프로젝트의 구성 개체에 대 한 플랫폼 이름을 확인할 수 있습니다.|  
  
 기본 프로젝트 위 속성의 기본 구현을 제공합니다.  기본 프로젝트를 호출 하 여 가져옵니다 `QueryInterface` 에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 가장 바깥쪽 프로젝트 하위에서 하므로 프로젝트 하위 속성의 구현을 재정의할 수 있습니다.  
  
## 참고 항목  
 [프로젝트 하위 형식 디자인](../../extensibility/internals/project-subtypes-design.md)