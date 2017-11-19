---
title: "기본 프로젝트의 개체 모델을 확장 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automation object model, extending
- project subtypes, extending automation object model
- automation object model
ms.assetid: 2f95cc53-dff6-476c-bacd-500fb0ff7725
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b92fe7fece58dd2006507f0285d3c440af437ee4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="extending-the-object-model-of-the-base-project"></a>기본 프로젝트의 개체 모델 확장
프로젝트 하위 형식에는 다음 위치에서 기본 프로젝트의 자동화 개체 모델을 확장 될 수 있습니다.  
  
-   Project.Extender ("\<ProjectSubtypeName >")-이 통해 프로젝트 하위 형식 사용자 지정 메서드를 사용 하 여 개체를 제공 하는 <xref:EnvDTE.Project>합니다. 프로젝트 하위 형식 צ ְ ײ Automation Extenders 노출 하는 `Project` 개체입니다. <xref:EnvDTE80.IInternalExtenderProvider>주 프로젝트 하위 형식 집계 중에 구현 된 인터페이스에 대 한 해당 개체를 제공 해야는 `VSHPROPID_ExtObjectCATID` 에서 <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2> (해당 하는 `itemid` VSITEMID_ROOT의 값에서 `VSITEMID`) CATID 합니다.  
  
-   ProjectItem.Extender ("\<ProjectSubtypeName >")-이 통해 사용자 지정 메서드를 통해 특정에서 개체를 제공 하는 프로젝트 하위 형식 <xref:EnvDTE.ProjectItem> 프로젝트 내에서 개체입니다. 프로젝트 하위 형식 Automation Extenders 사용이 개체를 노출할 수 있습니다. <xref:EnvDTE80.IInternalExtenderProvider> 주 프로젝트 하위 형식 집계 중에 구현 된 인터페이스에 대 한 해당 개체를 제공 해야 하는 경우는 `VSHPROPID_ExtObjectCATID` 에서 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> (해당 하는 원하는 `VSITEMID`) CATID 합니다.  
  
-   Project.Properties-이 컬렉션의 구성 독립 속성을 표시는 `Project` 개체입니다. 프로젝트 속성에 대 한 자세한 내용은 참조 하십시오. <xref:EnvDTE.Project.Properties%2A>합니다. 프로젝트 하위 형식 Automation Extenders 사용이 컬렉션에 해당 속성을 추가할 수 있습니다. <xref:EnvDTE80.IInternalExtenderProvider> 주 프로젝트 하위 형식 집계 중에 구현 된 인터페이스에 대 한 해당 개체를 제공 해야 하는 경우는 `VSHPROPID_BrowseObjectCATID` VSHPROPID2에서 (해당 하는 `itemid` VSITEMID_ROOT의 값에서 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>) CATID 합니다.  
  
-   Configuration.Properties-이 컬렉션의 특정 구성 (예: 디버그)에 대 한 프로젝트 구성 종속 속성을 노출합니다. 자세한 내용은 <xref:EnvDTE.Configuration>를 참조하세요. 프로젝트 하위 형식 Automation Extenders 사용이 컬렉션에 해당 속성을 추가할 수 있습니다. <xref:EnvDTE80.IInternalExtenderProvider> CATID 대 한 해당 개체를 제공 하는 주 프로젝트 하위 형식 집계 중에 구현 된 인터페이스 `VSHPROPID_CfgBrowseObjectCATID` (해당 하는 `itemid` 값 <xref:Microsoft.VisualStudio.VSConstants.VSITEMID_ROOT>). <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>인터페이스가 하나 구성 찾아보기 개체를 구분 하기 위해서 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>