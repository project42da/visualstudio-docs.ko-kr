---
title: "컨텍스트 매개 변수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wizards, context parameters
- context parameters
ms.assetid: 1a062dcb-8a8f-40dd-bea9-3d10f9448966
caps.latest.revision: 13
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
ms.openlocfilehash: 143a8738f2eb6517c1642eafd2b9629e0fa8f84d
ms.lasthandoff: 02/22/2017

---
# <a name="context-parameters"></a>컨텍스트 매개 변수
에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE)을 마법사를 추가할 수는 **새 프로젝트**, **새 항목 추가**, 또는 **하위 프로젝트 추가** 대화 상자. 추가 마법사에서 사용할 수 있는 **파일** 메뉴에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 또는 **솔루션 탐색기**합니다. IDE는 마법사의 구현에 컨텍스트 매개 변수를 전달합니다. IDE는 마법사를 호출 하는 경우 프로젝트의 상태를 정의 하는 컨텍스트 매개 변수입니다.  
  
 IDE 설정 하 여 마법사를 시작할는 <xref:Microsoft.VisualStudio.Shell.Interop.VSADDITEMOPERATION>플래그에 대 한 IDE의 호출에는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.AddItem%2A>프로젝트 방법을.</xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.AddItem%2A> </xref:Microsoft.VisualStudio.Shell.Interop.VSADDITEMOPERATION> 으로 설정 하면 프로젝트를 수행 해야 하는 `IVsExtensibility::RunWizardFile` 등록된 마법사 이름 또는 GUID 및 IDE에서 전달 하는 다른 컨텍스트 매개 변수를 사용 하 여 실행할 메서드를 합니다.  
  
## <a name="context-parameters-for-new-project"></a>새 프로젝트에 대 한 컨텍스트 매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`WizardType`|등록 된 마법사 형식 (<xref:EnvDTE.Constants.vsWizardNewProject>) 또는 마법사의 형식을 나타내는 GUID입니다.</xref:EnvDTE.Constants.vsWizardNewProject> 에 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 구현 마법사에 대 한 GUID는 {0F90E1D0-4999-11D1-B6D1-00A0C90F2744}.|  
|`ProjectName`|고유한 문자열 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 이름입니다.|  
|`LocalDirectory`|프로젝트 파일을 작업의 로컬 위치입니다.|  
|`InstallationDirectory`|디렉터리 경로 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 설치 항목입니다.|  
|`FExclusive`|프로젝트가 열려 있는 솔루션을 종료 해야 여부를 나타내는 부울 플래그입니다.|  
|`SolutionName`|솔루션 파일의 디렉터리 부분 또는.sln 확장명 없이 이름입니다. .Suo 파일 이름을 사용 하 여 작성도 `SolutionName`합니다. 마법사는 <xref:EnvDTE._Solution.Create%2A> <xref:EnvDTE._Solution.AddFromTemplate%2A>.</xref:EnvDTE._Solution.AddFromTemplate%2A> 를 사용 하 여 프로젝트를 추가 하기 전에</xref:EnvDTE._Solution.Create%2A> 사용이 인수는 빈 문자열이 없는 경우 이 이름은 빈 문자열인 경우 <xref:EnvDTE._Solution.AddFromTemplate%2A> <xref:EnvDTE._Solution.Create%2A>.</xref:EnvDTE._Solution.Create%2A> 를 호출 하지 않고</xref:EnvDTE._Solution.AddFromTemplate%2A> 사용 하 여|  
|`Silent`|마법사는 자동으로 실행할지 여부를 나타내는 부울 값 처럼 **마침** 클릭 된 (`TRUE`).|  
  
## <a name="context-parameters-for-add-new-item"></a>에 컨텍스트 매개 변수는 새 항목 추가  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`WizardType`|등록 된 마법사 형식 (<xref:EnvDTE.Constants.vsWizardAddItem>) 또는 마법사의 형식을 나타내는 GUID입니다.</xref:EnvDTE.Constants.vsWizardAddItem> 에 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 구현 마법사에 대 한 GUID는 {0F90E1D1-4999-11D1-B6D1-00A0C90F2744}.|  
|`ProjectName`|고유한 문자열 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 이름입니다.|  
|`ProjectItems`|작업 중인 프로젝트 파일이 포함 된 로컬 위치입니다.|  
|`ItemName`|추가 되는 항목의 이름입니다. 이 이름은 기본 파일 이름 또는 파일 이름에서 사용자 입력으로 **항목 추가** 대화 상자입니다. 이름은은.vsdir 파일에 설정 된 플래그를 기반으로 합니다. Null 값을 이름일 수 있습니다.|  
|`InstallationDirectory`|디렉터리 경로 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 설치 항목입니다.|  
|`Silent`|마법사는 자동으로 실행할지 여부를 나타내는 부울 값 처럼 **마침** 클릭 된 (`TRUE`).|  
  
## <a name="context-parameters-for-add-sub-project"></a>추가 하위 프로젝트에 대 한 컨텍스트 매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`WizardType`|등록 된 마법사 형식 (<xref:EnvDTE.Constants.vsWizardAddSubProject>) 또는 마법사의 형식을 나타내는 GUID입니다.</xref:EnvDTE.Constants.vsWizardAddSubProject> 에 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 구현 마법사에 대 한 GUID는 {0F90E1D2-4999-11D1-B6D1-00A0C90F2744}.|  
|`ProjectName`|고유한 문자열 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 이름입니다.|  
|`ProjectItems`|에 대 한 포인터는 `ProjectItems` 마법사가 작동 하는 컬렉션입니다. 이 포인터는 프로젝트 계층 구조 선택에 따라 마법사에 전달 됩니다. 사용자는 일반적으로 항목을 배치 하는 폴더를 선택 하 고 프로젝트의 다음 호출 **항목 추가** 대화 상자입니다.|  
|`LocalDirectory`|프로젝트 파일을 작업의 로컬 위치입니다.|  
|`ItemName`|추가 되는 항목의 이름입니다. 이 이름은 기본 파일 이름 또는 파일 이름에서 사용자 입력으로 **항목 추가** 대화 상자입니다. 이름은은.vsdir 파일에 설정 된 플래그를 기반으로 합니다. Null 값을 이름일 수 있습니다.|  
|`InstallationDirectory`|디렉터리 경로 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 설치 항목입니다.|  
|`Silent`|마법사는 자동으로 실행할지 여부를 나타내는 부울 값 처럼 **마침** 클릭 된 (`TRUE`).|  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject></xref:Microsoft.VisualStudio.Shell.Interop.IVsProject>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject2></xref:Microsoft.VisualStudio.Shell.Interop.IVsProject2>   
 [사용자 지정 매개 변수](../../extensibility/internals/custom-parameters.md)   
 [마법사](../../extensibility/internals/wizards.md)   
 [마법사 (합니다. Vsz) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)   
 [마법사를 시작 하는 것에 대 한 컨텍스트 매개 변수](http://msdn.microsoft.com/Library/051a10f4-9e45-4604-b344-123044f33a24)
