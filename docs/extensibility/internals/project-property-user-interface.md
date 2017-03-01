---
title: "프로젝트 속성 사용자 인터페이스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project properties [Visual Studio], user interface
- projects [Visual Studio SDK], properties UI
- project properties UI
ms.assetid: b6aec634-8533-476c-9ebd-36536a2288e2
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: b344731061053abb208225a0480408ebbe682050
ms.lasthandoff: 02/22/2017

---
# <a name="project-property-user-interface"></a>프로젝트 속성 사용자 인터페이스
프로젝트 하위 프로젝트에서 항목을 사용할 수 **속성 페이지** 대화 상자는 기본 프로젝트에서 제공 되기 때문 숨기기 읽기 전용 컨트롤 및 전체 페이지 값을 제공 하는 대로 또는 프로젝트 하위 형식의 특정 페이지를 추가 하는 **속성 페이지** 대화 상자입니다.  
  
## <a name="extending-the-project-property-dialog-box"></a>프로젝트 속성 대화 상자를 확장합니다.  
 프로젝트 하위 automation extender 및 프로젝트 구성 찾아보기 개체를 구현합니다. 이러한 extender 구현에서 <xref:EnvDTE.IFilterProperties>숨겨져 있거나 읽기 전용 특정 속성을 확인 하는 인터페이스입니다.</xref:EnvDTE.IFilterProperties> **속성 페이지** 기본 프로젝트에서 구현 하는 기본 프로젝트의 대화 상자 Automation Extender 수행한 필터링을 적용 합니다.  
  
 확장 하는 프로세스는 **프로젝트 속성** 대화 상자 아래에 나와 있습니다.  
  
-   기본 프로젝트의 경우 extender 프로젝트 하위 형식에서 구현 하 여 검색 된 <xref:EnvDTE80.IInternalExtenderProvider>인터페이스.</xref:EnvDTE80.IInternalExtenderProvider> 찾아보기, 프로젝트 자동화 및 모든 기본 프로젝트의 프로젝트 구성 찾아보기 개체에는이 인터페이스를 구현 합니다.  
  
-   구현의 <xref:EnvDTE80.IInternalExtenderProvider>프로젝트 찾아보기 개체 및 프로젝트 자동화 개체에 대리자에 대 한는 <xref:EnvDTE80.IInternalExtenderProvider>프로젝트 하위 집계의 구현 (즉, 이러한 `QueryInterface` 에 대 한 <xref:EnvDTE80.IInternalExtenderProvider>에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>프로젝트 개체).</xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> </xref:EnvDTE80.IInternalExtenderProvider> </xref:EnvDTE80.IInternalExtenderProvider> </xref:EnvDTE80.IInternalExtenderProvider>  
  
-   기본 프로젝트 구성 찾아보기 개체도 구현 <xref:EnvDTE80.IInternalExtenderProvider>프로젝트 하위 구성 개체에서 자동화 Extender에 직접 연결할.</xref:EnvDTE80.IInternalExtenderProvider> 구현에 위임 하는 <xref:EnvDTE80.IInternalExtenderProvider>프로젝트 하위 집계에서 구현 된 인터페이스입니다.</xref:EnvDTE80.IInternalExtenderProvider>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetProjectItem%2A>프로젝트 구성 찾아보기 개체를 반환 하 여 구현 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>개체.</xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy></xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetProjectItem%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetCfg%2A>도 프로젝트 구성 찾아보기 개체를 반환 하 여 구현 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg>개체.</xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg></xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetCfg%2A>  
  
-   프로젝트 하위 다음을 검색 하 여 런타임 시 기본 프로젝트의 다양 한 확장 가능한 개체에 대 한 적절 한 Catid를 결정할 수 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>값:</xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2></xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2></xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2></xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>  
  
 프로젝트 범위에 대 한 Catid를 확인 하려면 프로젝트 하위 검색에 대 한 위의 속성 <xref:Microsoft.VisualStudio.VSConstants.VSITEMID_ROOT>에서 `VSITEMID``typedef`.</xref:Microsoft.VisualStudio.VSConstants.VSITEMID_ROOT> 프로젝트 하위 유형을 제어 하는 할 수 **속성 페이지** 는 프로젝트에 대 한 대화 상자 페이지는 표시 구성에 종속적인와 독립적인 구성 합니다. 일부 프로젝트 하위 형식 기본 제공 페이지를 제거 하 고 프로젝트 하위 형식에 대 한 특정 페이지를 추가 해야 합니다. 이 호출 하 여 관리 되는 클라이언트 프로젝트를 사용 하도록 설정 하려면는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>다음 속성에 대 한 메서드:</xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>  
  
-   `VSHPROPID_PropertyPagesCLSIDList`— 구성 독립적 속성 페이지의 Clsid의 세미콜론으로 구분 된 목록이 있습니다.  
  
-   `VSHPROPID_CfgPropertyPagesCLSIDList —`구성에 종속 된 속성 페이지의 Clsid의 세미콜론으로 구분 된 목록입니다.  
  
 프로젝트 하위 집계 형식 때문에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>개체를 제어 하는 이러한 속성의 정의 재정의할 수 **속성 페이지** 대화 상자가 표시 됩니다.</xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 프로젝트 하위 내부 기본 프로젝트에서 이러한 속성을 검색 하 고 추가 하거나 제거할 수 clsid가 필요에 따라 합니다.  
  
 프로젝트 하위 형식으로 추가 하는 새 속성 페이지에서 기본 프로젝트 구현 프로젝트 구성 찾아보기 개체를 전달 됩니다. 이 프로젝트 구성 찾아보기 개체 Automation Extender를 지원합니다. AutomationExtenders에 대 한 자세한 내용은 참조 하십시오. [구현 및 Automation Extender를 사용 하 여](http://msdn.microsoft.com/Library/0d5c218c-f412-4b28-ab0c-33a611f62356)합니다. 프로젝트 하위 호출에 의해 구현 된 속성 페이지 <xref:EnvDTE.Project.Extender%2A>기본 프로젝트의 구성 찾아보기 개체를 확장 하는 자신의 프로젝트 하위 구성 찾아보기 개체를 검색 합니다.</xref:EnvDTE.Project.Extender%2A>  
  
## <a name="see-also"></a>참고 항목  
 <xref:EnvDTE.IFilterProperties></xref:EnvDTE.IFilterProperties>   
 [속성 페이지 대화 상자](http://msdn.microsoft.com/en-us/4a3d34ac-ed03-45e8-ae60-a0e1aad300e4)
