---
title: "프로젝트 및 항목 템플릿 등록 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 [Visual Studio SDK], 항목 추가"
  - "레지스트리, 새 항목 추가 대화 상자"
  - "새 항목 추가 대화 상자"
  - "새 프로젝트 추가 대화 상자"
  - "레지스트리, 새 프로젝트 추가 대화 상자"
ms.assetid: 6b909f93-d7f5-4aec-81c6-ee9ff0f31638
caps.latest.revision: 27
caps.handback.revision: 27
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로젝트 및 항목 템플릿 등록
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트 형식 프로젝트 및 프로젝트 항목 템플릿을 들어 있는 디렉터리에 등록 해야 합니다.[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 형식에 연결 된 등록 정보를 사용 하 여 표시 내용을 결정 하는 **새 프로젝트 추가** 및 **새 항목 추가** 대화 상자입니다.  
  
 템플릿에 대 한 자세한 내용은 참조 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)합니다.  
  
## 프로젝트에 대 한 레지스트리 항목  
 다음 예제는 레지스트리 항목 HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\VisualStudio\\ 아래 나열 \<*버전*\>입니다. 함께 제공 되는 테이블 예제에서 사용 되는 요소에 설명 합니다.  
  
```  
[Projects\{ProjectGUID}]  
@="MyProjectType"  
"DisplayName"="#2"  
"Package"="{VSPackageGUID}"  
"ProjectTemplatesDir"="C:\\MyProduct\\MyProjectTemplates"  
```  
  
|이름|형식|설명|  
|--------|--------|--------|  
|@|REG\_SZ|이러한 종류의 프로젝트의 기본 이름입니다.|  
|DisplayName|REG\_SZ|패키지에서 등록 하는 위성 DLL에서에서 검색 해야 하는 이름의 리소스 ID입니다.|  
|Package|REG\_SZ|패키지에서 등록 된 패키지의 클래스 ID입니다.|  
|ProjectTemplatesDir|REG\_SZ|프로젝트 템플릿 파일의 기본 경로입니다. 프로젝트 템플릿 파일은 표시는 **새 프로젝트** 템플릿.|  
  
### 항목 템플릿 등록  
 항목 템플릿을 저장할 디렉터리를 등록 해야 합니다.  
  
```  
[Projects\{ProjectGUID}\AddItemTemplates\TemplateDirs\{VSPackageGUID}\1]  
@="#7"  
"TemplatesDir"="C:\\MyProduct\\MyProjectItemTemplates "  
"TemplatesLocalizedSubDir"="#10"  
"SortPriority"=dword:00000064  
```  
  
|이름|형식|설명|  
|--------|--------|--------|  
|@|REG\_SZ|항목 추가 템플릿에 대 한 리소스 ID입니다.|  
|TemplatesDir|REG\_SZ|에 대 한 대화 상자에 표시 되는 프로젝트 항목의 경로 **새 항목 추가** 마법사.|  
|TemplatesLocalizedSubDir|REG\_SZ|리소스 ID는 TemplatesDir의 하위 디렉터리의 이름을 지정 하는 문자열의 지역화 된 템플릿을 보유 합니다. 때문에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 로드의 문자열 리소스를 위성 Dll에 있는 경우, 각 위성 DLL에는 지역화 된 다른 하위 디렉터리 이름이 포함 될 수 있습니다.|  
|SortPriority|REG\_DWORD|서식 파일에 표시 되는 순서를 제어 하는 SortPriority 설정의 **새 항목 추가** 대화 상자입니다. 더 큰 SortPriority 값 템플릿 목록에서 앞에 표시 됩니다.|  
  
### 파일 필터를 등록 하는 중  
 필요에 따라 필터를 등록할 수 있습니다는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 파일 이름에 대 한 메시지를 표시 하는 경우 사용 합니다. 예를 들어는 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 에 대 한 필터링 된는 **파일 열기** 대화 상자는:  
  
 **Visual C\# 파일 \(\*.cs, \*.resx, \*.settings, \*.xsd, \*.wsdl과 같은\); \*.cs, \*.resx, \*.settings, \*.xsd, \*.wsdl과 같은\)**  
  
 여러 필터의 등록을 지원 하려면 각 필터 HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\VisualStudio\\ 아래에 자체 하위 키에 등록 된 \<*버전*\> \\Projects\\ {\<*ProjectGUID*\>} \\Filters\\ \<*하위 키*\>입니다. 하위 키 이름이 임의; [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 하위 키의 이름을 무시 하 고 해당 값만 사용 합니다.  
  
 다음 표에 표시 된 플래그를 설정 하 여 사용 되는 필터 컨텍스트를 제어할 수 있습니다. 표시에서 공통 필터 후 됩니다 필터에 설정 된 모든 플래그 없는 경우는 **기존 항목 추가** 대화 상자 및 **파일 열기** 하지만 대화 상자, 사용 되지 것입니다에 **파일에서 찾기** 대화 상자.  
  
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
|--------|--------|--------|  
|CommonFindFilesFilter|REG\_DWORD|공통 필터 중 하나에 있는 필터를 사용 하면는 **파일에서 찾기** 대화 상자입니다. 공통 필터는 일반적으로 표시 되지 않은 필터 보다 먼저 필터 목록에 나열 됩니다.|  
|CommonOpenFilesFilter|REG\_DWORD|공통 필터 중 하나에 있는 필터를 사용 하면는 **파일 열기** 대화 상자입니다. 공통 필터는 일반적으로 표시 되지 않은 필터 보다 먼저 필터 목록에 나열 됩니다.|  
|FindInFilesFilter|REG\_DWORD|일반적인 필터 후 필터를 나열 된 **파일에서 찾기** 대화 상자.|  
|NotOpenFileFilter|REG\_DWORD|필터에서 사용 되지 않음을 나타냅니다는 **파일 열기** 대화 상자입니다.|  
|NotAddExistingItemFilter|REG\_DWORD|필터에서 사용 되지 않음을 나타냅니다는 **기존 항목 추가** 대화 상자입니다.|  
|SortPriority|REG\_DWORD|필터 표시 되는 순서를 제어 하는 SortPriority를 설정 합니다. 더 큰 SortPriority 값 필터 목록에서 앞에 표시 됩니다.|  
  
## 디렉터리 구조  
 Vspackage 넣을 수 템플릿 파일 및 폴더 어디서 나 로컬 또는 원격 디스크의 위치를 통해 통합된 개발 환경 \(IDE\) 등록으로. 그러나 조직 편의성, 제품의 설치 경로 아래에 다음 디렉터리 구조를 좋습니다.  
  
 \\Templates  
  
 \\Projects \(프로젝트 템플릿 포함\)  
  
 \\Applications  
  
 \\Components  
  
 \\ ...  
  
 \\ProjectItems \(프로젝트 항목이 포함\)  
  
 \\Class  
  
 \\Form  
  
 \\Web 페이지  
  
 \\HelperFiles \(다중 파일 프로젝트 항목에 사용 되는 파일 포함\)  
  
 \\WizardFiles  
  
## 참고 항목  
 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [마법사](../../extensibility/internals/wizards.md)   
 [응용 프로그램 지역화](../../ide/localizing-applications.md)   
 [일반적으로 프로젝트를 확장 하는 데 사용 되는 개체에 대 한 Catid](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)