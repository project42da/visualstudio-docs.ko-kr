---
title: 속성 사용자 인터페이스 프로젝트 | Microsoft Docs
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project properties [Visual Studio], user interface
- projects [Visual Studio SDK], properties UI
- project properties UI
ms.assetid: b6aec634-8533-476c-9ebd-36536a2288e2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 788107666f8103a77753b93fa7c1febc73f9b97f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="project-property-user-interface"></a>프로젝트 속성 사용자 인터페이스
프로젝트 하위 형식 프로젝트에 항목을 사용할 수 **속성 페이지** 대화 상자 기본 프로젝트에서 제공 하는 대로 숨기기 읽기 전용 컨트롤 및 전체 페이지도 제공 또는 프로젝트 하위 형식의 특정 페이지는 를추가할**속성 페이지** 대화 상자.

## <a name="extending-the-project-property-dialog-box"></a>프로젝트 속성 대화 상자를 확장합니다.
 프로젝트 하위 형식 자동화 extender 및 프로젝트 구성 찾아보기 개체를 구현합니다. 이러한 extender 구현에서 <xref:EnvDTE.IFilterProperties> 숨김 또는 읽기 전용 특정 속성을 확인 하는 인터페이스입니다. **속성 페이지** 기본 프로젝트에서 구현 하는 기본 프로젝트의 대화 상자 Automation Extenders 수행한 필터링을 적용 합니다.

 확장 프로세스는 한 **프로젝트 속성** 대화 상자가 다음과 같습니다.

-   기본 프로젝트는 extender 프로젝트 하위 형식에서 구현 하 여 검색 된 <xref:EnvDTE80.IInternalExtenderProvider> 인터페이스입니다. 찾아보기, 프로젝트 자동화 및 모든 기본 프로젝트의 프로젝트 구성 찾아보기 개체에는이 인터페이스를 구현 합니다.

-   구현 <xref:EnvDTE80.IInternalExtenderProvider> 프로젝트 찾아보기 개체와 프로젝트 자동화 개체에 위임에 대 한는 <xref:EnvDTE80.IInternalExtenderProvider> 프로젝트 하위 형식 aggregator의 구현 (즉, 이러한 `QueryInterface` 에 대 한 <xref:EnvDTE80.IInternalExtenderProvider> 에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 프로젝트 개체)입니다.

-   기본 프로젝트 구성 찾아보기 개체도 구현 <xref:EnvDTE80.IInternalExtenderProvider> 을 Automation Extender 프로젝트 하위 형식 구성 개체에서 직접 연결 합니다. 구현에 위임 된 <xref:EnvDTE80.IInternalExtenderProvider> 프로젝트 하위 형식 집계에서 구현 된 인터페이스입니다.

-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetProjectItem%2A>를 반환 프로젝트 구성 찾아보기 개체에 의해 구현 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 개체입니다.

-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetCfg%2A>도 프로젝트 구성 찾아보기 개체를 반환 하 여 구현 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg> 개체입니다.

-   프로젝트 하위 형식에서 다음을 검색 하 여 런타임 시 기본 프로젝트의 다양 한 확장 가능한 개체에 대 한 적절 한 Catid를 결정할 수 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> 값:

    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>

    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>

    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>

프로젝트 범위에 대 한 Catid를 확인 하려면 프로젝트 하위 형식에 대 한 위의 속성을 검색 [VSITEMID 합니다. 루트](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>) 에서 `VSITEMID typedef`합니다. 제어 하는 프로젝트 하위 형식 수도 **속성 페이지** 프로젝트에 대 한 대화 상자 페이지는 표시 독립 구성 종속 및 독립 구성 합니다. 일부 프로젝트 하위 형식 기본 제공 페이지를 제거 하 고 프로젝트 하위 형식에 대 한 특정 페이지를 추가 해야 합니다. 이 프로젝트 대 한 관리 되는 클라이언트를 사용 하도록 설정 하려면는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> 메서드는 다음과 같은 속성:

-   `VSHPROPID_PropertyPagesCLSIDList` -구성과 무관 속성 페이지의 Clsid의 세미콜론으로 구분 된 목록입니다.

-   `VSHPROPID_CfgPropertyPagesCLSIDList —` 구성에 종속 된 속성 페이지의 Clsid의 세미콜론으로 구분 된 목록입니다.

프로젝트 하위 집계 형식 이므로 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 개체를 제어 하는 이러한 속성의 정의 재정의할 수 **속성 페이지** 대화 상자가 표시 됩니다. 프로젝트 하위 형식 내부 기본 프로젝트에서 이러한 속성을 검색 한 다음 추가 하거나 제거할 수 Clsid 필요에 따라 합니다.

프로젝트 하위 형식에서 추가한 새 속성 페이지의 기본 프로젝트 구현에서 프로젝트 구성 찾아보기 개체가 전달 됩니다. 이 프로젝트 구성 찾아보기 개체 Automation Extenders를 지원합니다. AutomationExtenders에 대 한 자세한 내용은 참조 하십시오. [구현 및 사용 하 여 Automation Extenders](http://msdn.microsoft.com/Library/0d5c218c-f412-4b28-ab0c-33a611f62356)합니다. 프로젝트 하위 형식 호출에 의해 구현 된 속성 페이지 <xref:EnvDTE.Project.Extender%2A> 기본 프로젝트의 구성 찾아보기 개체를 확장 하는 자신의 프로젝트 하위 형식 구성 찾아보기 개체를 검색 합니다.

## <a name="see-also"></a>참고자료

- <xref:EnvDTE.IFilterProperties>
- [속성 페이지 대화 상자](http://msdn.microsoft.com/en-us/4a3d34ac-ed03-45e8-ae60-a0e1aad300e4)