---
title: 기본 프로젝트의 개체 모델을 확장 | Microsoft Docs
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- automation object model, extending
- project subtypes, extending automation object model
- automation object model
ms.assetid: 2f95cc53-dff6-476c-bacd-500fb0ff7725
caps.latest.revision: ''
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a0fdda35744aaddf8789818afd1f938897470147
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2018
---
# <a name="extending-the-object-model-of-the-base-project"></a>기본 프로젝트의 개체 모델 확장

프로젝트 하위 형식에는 다음 위치에서 기본 프로젝트의 자동화 개체 모델을 확장 될 수 있습니다.

-   Project.Extender ("\<ProjectSubtypeName >")-이 통해 프로젝트 하위 형식 사용자 지정 메서드를 사용 하 여 개체를 제공 하는 <xref:EnvDTE.Project>합니다. 프로젝트 하위 형식 צ ְ ײ Automation Extenders 노출 하는 `Project` 개체입니다. <xref:EnvDTE80.IInternalExtenderProvider> 주 프로젝트 하위 형식 집계 중에 구현 된 인터페이스에 대 한 해당 개체를 제공 해야는 `VSHPROPID_ExtObjectCATID` 에서 <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2> (해당 하는 `itemid` 값 [VSITEMID 합니다. 루트](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)) CATID 합니다.

-   ProjectItem.Extender ("\<ProjectSubtypeName >")-이 통해 사용자 지정 메서드를 통해 특정에서 개체를 제공 하는 프로젝트 하위 형식 <xref:EnvDTE.ProjectItem> 프로젝트 내에서 개체입니다. 프로젝트 하위 형식 Automation Extenders 사용이 개체를 노출할 수 있습니다. <xref:EnvDTE80.IInternalExtenderProvider> 주 프로젝트 하위 형식 집계 중에 구현 된 인터페이스에 대 한 해당 개체를 제공 해야 하는 경우는 `VSHPROPID_ExtObjectCATID` 에서 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> (해당 하는 원하는 <xref:Microsoft.VisualStudio.VSConstants.VSITEMID>) CATID 합니다.

-   이 컬렉션의 구성에 관계 없이 속성을 노출 Project.Properties-는 `Project` 개체입니다. 프로젝트 속성에 대 한 자세한 내용은 참조 하십시오. <xref:EnvDTE.Project.Properties%2A>합니다. 프로젝트 하위 형식 Automation Extenders 사용이 컬렉션에 해당 속성을 추가할 수 있습니다. <xref:EnvDTE80.IInternalExtenderProvider> 주 프로젝트 하위 형식 집계 중에 구현 된 인터페이스에 대 한 해당 개체를 제공 해야 하는 경우는 `VSHPROPID_BrowseObjectCATID` VSHPROPID2에서 (해당 하는 `itemid` 값 [VSITEMID 합니다. 루트](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)에서 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>) CATID 합니다.

-   Configuration.Properties-이 컬렉션 (예: 디버그) 특정 구성에 대 한 프로젝트의 구성에 종속 된 속성을 노출합니다. 자세한 내용은 <xref:EnvDTE.Configuration>을 참조하세요. 프로젝트 하위 형식 Automation Extenders 사용이 컬렉션에 해당 속성을 추가할 수 있습니다. <xref:EnvDTE80.IInternalExtenderProvider> CATID 대 한 해당 개체를 제공 하는 주 프로젝트 하위 형식 집계 중에 구현 된 인터페이스 `VSHPROPID_CfgBrowseObjectCATID` (해당 하는 `itemid` 값 [VSITEMID 합니다. 루트](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)). <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>인터페이스가 하나 구성 찾아보기 개체를 구분 하기 위해서 사용 됩니다.

## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>