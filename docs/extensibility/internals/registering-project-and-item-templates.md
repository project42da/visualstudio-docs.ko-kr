---
title: "프로젝트 및 항목 템플릿 등록 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], adding items
- registry, Add New Item dialog box
- Add New Item dialog box
- Add New Project dialog box
- registry, Add New Project dialog box
ms.assetid: 6b909f93-d7f5-4aec-81c6-ee9ff0f31638
caps.latest.revision: "27"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5c1cb9e31384822dddcdd3668bfb3a54bc2782d6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="registering-project-and-item-templates"></a>프로젝트 및 항목 템플릿 등록
프로젝트 형식 프로젝트 및 프로젝트 항목 템플릿이 있는 디렉터리에 등록 해야 합니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]프로젝트 형식에 연결 된 등록 정보를 사용 하 여에 표시할 작업을 결정 하는 **새 프로젝트 추가** 및 **새 항목 추가** 대화 상자.  
  
 서식 파일에 대 한 자세한 내용은 참조 [추가 프로젝트 및 프로젝트 항목 템플릿](../../extensibility/internals/adding-project-and-project-item-templates.md)합니다.  
  
## <a name="registry-entries-for-projects"></a>프로젝트에 대 한 레지스트리 항목  
 다음 예제에서는 보여 레지스트리 항목 HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio 아래\\<*버전*> 합니다. 함께 제공 되는 테이블 예제에서 사용 되는 요소에 설명 합니다.  
  
```  
[Projects\{ProjectGUID}]  
@="MyProjectType"  
"DisplayName"="#2"  
"Package"="{VSPackageGUID}"  
"ProjectTemplatesDir"="C:\\MyProduct\\MyProjectTemplates"  
```  
  
|이름|형식|설명|  
|----------|----------|-----------------|  
|@|REG_SZ|이러한 종류의 프로젝트의 기본 이름입니다.|  
|DisplayName|REG_SZ|패키지에서 등록 하는 위성 DLL에서에서 검색 해야 하는 이름의 리소스 ID입니다.|  
|패키지|REG_SZ|패키지에서 등록 된 패키지의 클래스 ID입니다.|  
|ProjectTemplatesDir|REG_SZ|프로젝트 템플릿 파일의 기본 경로입니다. 프로젝트 템플릿 파일 여 표시 되는 **새 프로젝트** 템플릿.|  
  
### <a name="registering-item-templates"></a>등록 항목 템플릿  
 항목 템플릿을 저장할 디렉터리를 등록 해야 합니다.  
  
```  
[Projects\{ProjectGUID}\AddItemTemplates\TemplateDirs\{VSPackageGUID}\1]  
@="#7"  
"TemplatesDir"="C:\\MyProduct\\MyProjectItemTemplates "  
"TemplatesLocalizedSubDir"="#10"  
"SortPriority"=dword:00000064  
```  
  
|이름|형식|설명|  
|----------|----------|-----------------|  
|@|REG_SZ|항목 추가 템플릿에 대 한 리소스 ID입니다.|  
|TemplatesDir|REG_SZ|에 대 한 대화 상자에 표시 되는 프로젝트 항목의 경로 **새 항목 추가** 마법사.|  
|TemplatesLocalizedSubDir|REG_SZ|리소스 ID는 TemplatesDir의 하위 디렉터리의 이름을 지정 하는 문자열의 지역화 된 템플릿에 보유 합니다. 때문에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 로드 문자열 리소스를 위성 Dll에 있는 경우, 각 위성 DLL에는 지역화 된 다른 하위 디렉터리 이름이 포함 될 수 있습니다.|  
|SortPriority|REG_DWORD|서식 파일에 표시 되는 순서를 제어 하는 SortPriority 설정는 **새 항목 추가** 대화 상자. 더 큰 SortPriority 값 템플릿 목록에서 앞에 표시 됩니다.|  
  
### <a name="registering-file-filters"></a>파일 필터를 등록 하는 중  
 필요에 따라 필터를 등록할 수 있습니다는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 파일 이름에 대 한 메시지가 나타날 경우에 사용 합니다. 예를 들어는 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 에 대 한 필터는 **열려 있는 파일** 대화 상자:  
  
 **Visual C# 파일 (\*.cs,\*.resx,\*.settings,\*.xsd,\*.wsdl);\*합니다. cs,\*.resx,\*.settings,\*.xsd,\*.wsdl)**  
  
 여러 필터의 등록을 지원 하려면 각 필터 HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio 아래에 자체 하위 키에 등록 되어\\<*버전*> \Projects\\{ \< *ProjectGUID*>} \Filters\\<*하위 키*> 합니다. 하위 키 이름은 임의로 지정 됩니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 하위 키의 이름을 무시 하 고 해당 값만 사용 합니다.  
  
 다음 표에 표시 된 플래그를 설정 하 여 사용 되는 필터 컨텍스트를 제어할 수 있습니다. 필터에 설정 된 모든 플래그 없는 경우 그 뒤에 나열 됩니다에 공통 필터는 **기존 항목 추가** 대화 상자와 **열려 있는 파일** 대화 상자, 하지만 사용 되지 것입니다에 **파일에서 찾기**  대화 상자.  
  
```  
[Projects\{ProjectGUID}\Filters\MyLanguageFilter]  
@="#3"  
"CommonOpenFilesFilter"=dword:00000000  
"CommonFindFilesFilter"=dword:00000000  
"FindInFilesFilter"=dword:00000000  
"NotOpenFileFilter"=dword:00000000  
"NotAddExistingItemFilter"=dword:00000000  
"SortPriority"=dword:00000064  
```  
  
|이름|형식|설명|  
|----------|----------|-----------------|  
|CommonFindFilesFilter|REG_DWORD|공통 필터 중 하나에 있는 필터를 사용 하면는 **파일에서 찾기** 대화 상자. 공통 필터는 일반적으로 표시 되어 있지 필터 보다 먼저 필터 목록에 나열 됩니다.|  
|CommonOpenFilesFilter|REG_DWORD|공통 필터 중 하나에 있는 필터를 사용 하면는 **열려 있는 파일** 대화 상자. 공통 필터는 일반적으로 표시 되어 있지 필터 보다 먼저 필터 목록에 나열 됩니다.|  
|FindInFilesFilter|REG_DWORD|일반적인 필터 후 필터를 나열는 **파일에서 찾기** 대화 상자.|  
|NotOpenFileFilter|REG_DWORD|필터에 사용 되지 않음을 나타냅니다는 **열려 있는 파일** 대화 상자.|  
|NotAddExistingItemFilter|REG_DWORD|필터에 사용 되지 않음을 나타냅니다는 **기존 항목 추가** 대화 상자.|  
|SortPriority|REG_DWORD|필터 표시 되는 순서를 제어 하는 SortPriority를 설정 합니다. 더 큰 SortPriority 값 필터 목록에서 앞에 표시 됩니다.|  
  
## <a name="directory-structure"></a>디렉터리 구조  
 Vspackage에 올릴 수 템플릿 파일 및 폴더 위치는 로컬 또는 원격 디스크 위치 통합된 개발 환경 (IDE)를 통해 등록 된 상태로. 그러나 하기 쉽도록 조직, 제품의 설치 경로에서 다음과 같은 디렉터리 구조를 권장 합니다.  
  
 \Templates  
  
 \Projects (프로젝트 템플릿을 포함)  
  
 \Applications  
  
 \Components  
  
 \ ...  
  
 \ProjectItems (프로젝트 항목 포함)  
  
 \Class  
  
 \Form  
  
 \Web 페이지  
  
 \HelperFiles (다중 파일 프로젝트 항목에 사용 되는 파일 포함)  
  
 \WizardFiles  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [마법사](../../extensibility/internals/wizards.md)   
 [응용 프로그램 지역화](../../ide/localizing-applications.md)   
 [일반적으로 프로젝트를 확장하는 데 사용되는 개체에 대한 CATID](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)