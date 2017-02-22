---
title: "기본 프로젝트의 개체 모델 확장 | Microsoft Docs"
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
  - "자동화 개체 모델, 확장"
  - "자동화 개체 모델을 확장 프로젝트 하위 형식"
  - "자동화 개체 모델"
ms.assetid: 2f95cc53-dff6-476c-bacd-500fb0ff7725
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# 기본 프로젝트의 개체 모델 확장
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트 하위 형식에는 다음 위치에서 기본 프로젝트의 자동화 개체 모델을 확장 될 수 있습니다.  
  
-   Project.Extender ("\< ProjectSubtypeName>")-이 통해 프로젝트 하위 개체에서 사용자 지정 메서드를 제공 하는 <xref:EnvDTE.Project>합니다. 프로젝트 하위 노출 Automation Extender를 사용할 수는 `Project` 개체입니다.  <xref:EnvDTE80.IInternalExtenderProvider>주 프로젝트 하위 집계에 구현 된 인터페이스에 대 한 해당 개체를 제공 해야는 `VSHPROPID_ExtObjectCATID` 에서 <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2> (해당 하는 `itemid` VSITEMID_ROOT의 값에서 `VSITEMID`) CATID입니다.  
  
-   ProjectItem.Extender ("\< ProjectSubtypeName>")-이 통해 특정에서 사용자 지정 메서드의 개체를 제공 하는 프로젝트 하위 <xref:EnvDTE.ProjectItem> 프로젝트 내에서 개체입니다. 프로젝트 하위 Automation Extender를 사용 하 여이 개체를 노출 하 수 있습니다.  <xref:EnvDTE80.IInternalExtenderProvider> 주 프로젝트 하위 집계에 구현 된 인터페이스에 대 한 해당 개체를 제공 해야 하는 경우는 `VSHPROPID_ExtObjectCATID` 에서 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> (해당 하는 원하는 `VSITEMID`) CATID입니다.  
  
-   Project.Properties –이 컬렉션의 구성 독립 속성을 노출 된 `Project` 개체입니다. 프로젝트 속성에 대 한 자세한 내용은 참조 하십시오. <xref:EnvDTE.Project.Properties%2A>합니다. 프로젝트 하위 Automation Extender 사용이 컬렉션에 해당 속성을 추가할 수 있습니다.  <xref:EnvDTE80.IInternalExtenderProvider> 주 프로젝트 하위 집계에 구현 된 인터페이스에 대 한 해당 개체를 제공 해야 하는 경우는 `VSHPROPID_BrowseObjectCATID` VSHPROPID2에서 (해당 하는 `itemid` VSITEMID_ROOT의 값에서 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>) CATID입니다.  
  
-   Configuration.Properties –이 컬렉션 (예: 디버그)는 특정 구성에 대 한 프로젝트의 구성 종속 속성을 노출합니다. 자세한 내용은 참조 하십시오 <xref:EnvDTE.Configuration>합니다. 프로젝트 하위 Automation Extender 사용이 컬렉션에 해당 속성을 추가할 수 있습니다.  <xref:EnvDTE80.IInternalExtenderProvider> 주 프로젝트 하위 집계에 구현 된 인터페이스의 CATID를 해당 개체를 제공 `VSHPROPID_CfgBrowseObjectCATID` (해당 하는 `itemid` 값 <xref:Microsoft.VisualStudio.VSConstants.VSITEMID_ROOT>).  <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>인터페이스를 하나 구성 찾아보기 개체를 구분 하기 위해서 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>