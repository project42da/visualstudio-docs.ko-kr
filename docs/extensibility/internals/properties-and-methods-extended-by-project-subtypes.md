---
title: 속성 및 메서드 확장 프로젝트 하위 형식 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project subtypes, extended methods
- project subtypes, extended properties
ms.assetid: 2b9833bf-8551-4ae1-93db-197ba645c65e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 23510ffbb42e0c0c37c07e0ee80ae15f99e5df00
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="properties-and-methods-extended-by-project-subtypes"></a>속성 및 프로젝트 하위 형식에 의해 확장 메서드
프로젝트 하위 형식에는 전원 기본 프로젝트의 집계로 생성 된 때문에 프로젝트의 동작에 영향을 줍니다. 이 섹션에는 프로젝트 하위 형식에 의해 수정 되거나 향상 될 수 있는 기능 중 일부를 요약 합니다.  
  
## <a name="features-gained-by-aggregation"></a>집계를 통해 얻은 기능  
 다음 표에서 다양 한 집계 프로젝트 하위 형식 기본 프로젝트에서 재정의할 수 있도록 하는 방법을 요약 합니다.  
  
|집계에 의해 재정의 메서드|프로젝트 하위 형식|  
|---------------------------------------|---------------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>:<br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.SetProperty%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetGuidProperty%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.SetGuidProperty%2A>|프로젝트 하위 형식에 사용 하도록 설정<br /><br /> 캡션 및 아이콘의 프로젝트 노드를 변경 합니다.<br />-완전히 프로젝트 재정의 `Browse` 개체입니다.<br />-프로젝트의 이름을 바꿀 수 있는지 여부를 제어 합니다.<br />정렬 순서를 제어 합니다.<br />동적 도움말에 대 한 사용자 컨텍스트를 제어 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProject>:<br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.GetItemContext%2A>|프로젝트 하위 형식을를 디자이너와 편집기 상황에 맞는 서비스 제공 됩니다 제어할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>:<br /><br /> <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A><br /><br /> <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>|프로젝트 하위 형식에 사용 하도록 설정<br /><br /> -프로젝트 명령에 대 한 명령 라우팅에 참여 합니다.<br />-추가, 제거 또는 앰비언트 명령 프로젝트 및 솔루션 탐색기 활성 명령을 둘 다 사용 하지 않도록 설정 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>|프로젝트 하위 형식에서 사용자에 게 어떻게 표시 필터링 할 수 있도록는 **새 항목 추가** 대화 상자.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGeneratorFactory>|프로젝트 하위 형식에 사용 하도록 설정<br /><br /> -기본 생성기 파일 확장명을 결정 합니다.<br />-COM 개체를 사람이 읽을 수 있는 생성기 이름을 매핑하십시오.|  
  
## <a name="properties-used-by-project-subtypes"></a>프로젝트 하위 형식에서 사용 되는 속성  
 환경 및 기본 프로젝트 시스템에서 속성을 사용할 수 <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID> 및 <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2> 프로젝트 하위 프로젝트 시스템의 다양 한 기능을 제어할 수 있도록 다음 표에서 자세히 설명 하는 열거형입니다.  
  
|VSHPROPID 속성|프로젝트 하위 형식|  
|------------------------|---------------------|  
|`AddItemTemplatesGuid`|내용을 제어 하는 프로젝트 하위 형식에 허용 된 **항목 추가** 대화 상자. 프로젝트 하위 형식 수 템플릿 디렉터리의 새 사양을 제공, 새로운 종류의 항목을 추가, 기존 항목을 제거 및 기본 프로젝트에 있는 항목의 하위 집합을 다시 구성 **항목 추가** 대화 상자.|  
|`PropertyPagesCLSIDList`|프로젝트 하위 형식을 구성에 관계 없이 속성 페이지를 추가 하거나 제거할 수 있습니다.|  
|`CfgPropertyPagesCLSIDList`|프로젝트 하위 형식을 구성에 종속 된 속성 페이지를 추가 하거나 제거할 수 있습니다.|  
|`ExtObjectCATID`|개체를 제공 하도록 Automation Extender 프로젝트 또는 프로젝트에 대 한 항목 Extender CATID를 확인 하 여 프로젝트 하위 형식을 수 있습니다. 프로젝트 하위 형식에서 사용자 지정을 제공할 수는 예를 들어 `Project.Extender("<subtype>")` 개체입니다.|  
|`BrowseObjectCATID`|허용 프로젝트 하위 형식에 대 한 자동화 Extender를 제공 하는 `Browse` Extender CATID를 확인 하 여 개체입니다. 예를 들어, 프로젝트 하위 형식에 추가 속성을를 추가할 수는 <xref:EnvDTE.Project.Properties%2A> 컬렉션입니다.|  
|`CfgBrowseObjectCATID`|Automation Extender 프로젝트 구성 찾아보기 개체에 대 한 제공 프로젝트 하위 형식을 수 있습니다. 예를 들어, 프로젝트 하위 형식에 추가 속성을를 추가할 수는 <xref:EnvDTE.Configuration.Properties%2A> 컬렉션입니다.|  
|`CfgExtObjectCATID`|프로젝트 하위 형식을 구성 개체에 대 한 자동화 Extender를 제공할 수 있습니다.|  
|`DefaultPlatformName`|프로젝트 하위 형식을 프로젝트의 구성 개체에 대 한 플랫폼 이름을 확인할 수 있습니다.|  
  
 기본 프로젝트에는 위의 속성의 기본 구현을 제공합니다. 기본 프로젝트를 실행 하 여 가져옵니다 `QueryInterface` 에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 가장 바깥쪽 프로젝트 하위 형식 되므로 속성 구현을 재정의 하는 프로젝트 하위 형식입니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 하위 형식 디자인](../../extensibility/internals/project-subtypes-design.md)