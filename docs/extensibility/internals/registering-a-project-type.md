---
title: "프로젝트 형식 등록 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 [Visual Studio SDK] 새 레지스트리 항목을 프로젝트"
  - "레지스트리, 새 프로젝트 형식"
  - "등록, 새 프로젝트 형식"
ms.assetid: dfc0e231-6b4e-447d-9d64-0e66dea3394a
caps.latest.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 21
---
# 프로젝트 형식 등록
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

새 프로젝트 형식을 만들 때 사용 하는 레지스트리 항목을 만들어야 합니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 인식 하 고 프로젝트 형식으로 작업할 수 있습니다.  일반적으로 레지스트리 스크립트 \(.rgs\) 파일을 사용 하 여 이러한 레지스트리 항목 만듭니다.  
  
 아래 예제에서는 기본 경로 레지스트리에서 문을 제공 하 고 데이터가 적용 되는 레지스트리 스크립트 각 문에 대 한 항목을 포함 하는 테이블에.  테이블 스크립트 항목 및 해당 문에 대 한 추가 정보를 제공합니다.  
  
> [!NOTE]
>  종류의 예 고 항목 프로젝트 형식 등록 하려면 작성 하려는 레지스트리 스크립트에는 다음 레지스트리 정보를 위한 것입니다.  실제 항목 및 그 사용법을 프로젝트 형식의 특정 요구 사항에 따라 달라질 수 있습니다.  개발 중인 프로젝트의 형식에 유사한 찾을 수 있는 샘플을 검토 하 고 레지스트리 스크립트를 샘플을 검토 해야 합니다.  
  
 다음 예제에서 HKEY\_CLASSES\_ROOT입니다.  
  
## 예제  
  
```  
\.figp  
   @="FigPrjFile"  
   "Content Type"="text/plain"  
\.figp\ShellNew  
   "NullFile"=""  
\FigPrjFile  
   @="Figure Project File"  
\DefaultIcon  
   @="<Visual Studio SDK installation path>\\9.0VSIntegration\\SomeFolder\\FigPkgs\\FigPrj\\Debug\\FigPrj.dll,-206"  
\shell\open  
   @="&Open in Visual Studio"  
\shell\open\command  
   @="devenv.exe \"%1\""  
```  
  
|Name|형식|데이터|설명|  
|----------|--------|---------|--------|  
|`@`|REG\_SZ|`FigPrjFile`|파일 확장명이.figp 프로젝트의 이름과 설명을 입력 합니다.|  
|`Content Type`|REG\_SZ|`Text/plain`|프로젝트 파일에 대 한 콘텐츠 형식입니다.|  
|`NullFile`|REG\_SZ|`Null`||  
|`@`|REG\_SZ|`%MODULE%,-206`|이러한 종류의 프로젝트에 사용 되는 기본 아이콘입니다.  %MODULE% 문은 프로젝트 형식의 DLL의 기본 위치에 완료 됩니다.|  
|`@`|REG\_SZ|`&Open in Visual Studio`|이 프로젝트 형식은 열리는 기본 응용 프로그램입니다.|  
|`@`|REG\_SZ|`devenv.exe "%1"`|이러한 종류의 프로젝트를 열 때 실행 되는 기본 명령입니다.|  
  
 다음 예제에서 HKEY\_LOCAL\_MACHINE 이며 레지스트리 키 \[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\99.0Exp\\Packages\] 아래에 있습니다.  
  
## 예제  
  
```  
\{ACEF4EB2-57CF-11D2-96F4-000000000000} (The CLSID for the VSPackage)  
   @="FigPrj Project Package"  
   "InprocServer32"="9.0<Visual Studio SDK installation path>\\VSIntegration\\Archive\\FigPkgs\\FigPrj\\                      Debug\\FigPrj.dll"  
   "CompanyName"="Microsoft"  
   "ProductName"="Figure Project Sample"  
   "ProductVersion"="9.0"  
   "MinEdition"="professional"  
   "ID"=dword:00000001  
\{ACEF4EB2-57CF-11D2-96F4-000000000000}\SatelliteDLL  
   "DllName"="FigPrjUI.dll"  
   "Path"="9.0<Visual Studio SDK installation path>\\VSIntegration\\Archive\\FigPkgs\\FigPrj\\Debug\\"  
\{ACEF4EB2-57CF-11D2-96F4-000000000000}\Automation  
   "FigProjects"=""  
\{ACEF4EB2-57CF-11D2-96F4-000000000000}\AutomationEvents  
   "FigProjectsEvents"="Returns the FigProjectsEvents Object"  
   "FigProjectItemsEvents"="Returns the FigProjectItemsEvents Object"  
```  
  
|Name|형식|데이터|설명|  
|----------|--------|---------|--------|  
|`@` \(기본값\)|REG\_SZ|`FigPrj Project VSPackage`|지역화 가능한 이름을 VSPackage \(프로젝트 형식\)을 등록합니다.|  
|`InprocServer32`|REG\_SZ|`%MODULE%`|프로젝트 형식의 DLL의 경로입니다.  IDE이이 DLL을 로드 하 고 VSPackage CLSID를 전달 `DllGetClassObject` 얻을 수 <xref:Microsoft.VisualStudio.OLE.Interop.IClassFactory> 를 생성 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> 개체입니다.|  
|`CompanyName`|REG\_SZ|`Microsoft`|프로젝트 형식을 개발 하는 회사의 이름입니다.|  
|`ProductName`|REG\_SZ|`Figure Project Sample`|프로젝트 형식에 대 한 이름입니다.|  
|`ProductVersion`|REG\_SZ|`9.0`|프로젝트 형식의 버전 번호를 놓습니다.|  
|`MinEdition`|REG\_SZ|`professional`|등록 중인 Vspackage의 버전입니다.|  
|`ID`|REG\_DWORD|`%IDS_PACKAGE_LOAD_KEY%`|패키지 로드 VSPackage 프로젝트에 대 한 키입니다.  환경 시작 프로젝트가 로드 될 때 키를 확인 합니다.|  
|`DllName`|REG\_SZ|`%RESOURCE_DLL%`|위성 프로젝트 형식에 대 한 지역화 된 리소스를 포함 하는 DLL의 파일 이름입니다.|  
|`Path`|REG\_SZ|`%RESOURCE_PATH%`|위성 DLL의 경로입니다.|  
|`FigProjectsEvents`|REG\_SZ|값에 대 한 설명을 참조 하십시오.|이 자동화 이벤트에 대해 반환 되는 텍스트 문자열을 지정 합니다.|  
|`FigProjectItemsEvents`|REG\_SZ|값에 대 한 설명을 참조 하십시오.|이 자동화 이벤트에 대해 반환 되는 텍스트 문자열을 지정 합니다.|  
  
 다음 예제에서는 \[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\9.0Exp\\Projects\] 키 아래에 위치 합니다.  
  
## 예제  
  
```  
\{C061DB26-5833-11D2-96F5-000000000000} (The CLSID for projects of this type)  
   @="FigPrj Project"  
   "DisplayName"="#2"  
   "Package"="{ACEF4EB2-57CF-11D2-96F4-000000000000}"  
   "ProjectTemplatesDir"="C:\\Program Files\\VSIP 9.0\\EnvSDK\\FigPkgs\\                           FigPrj\\FigPrjProjects"  
   "ItemTemplatesDir"="<Visual Studio SDK installation path>\\VSIntegration\\Archive9.0\\FigPkgs\\FigPrj\\                           FigPrjProjectItems"  
   "DisplayProjectFileExtensions"="#3"  
   "PossibleProjectExtensions"="figp"  
   "DefaultProjectExtension"=".figp"  
\{C061DB26-5833-11D2-96F5-000000000000}\Filters\1       (Folder 1 contains settings for Open Files filters.)  
   @="#4"  
   "CommonOpenFilesFilter"=dword:00000000  
   "CommonFindFilesFilter"=dword:00000000  
   "NotAddExistingItemFilter"=dword:00000000  
   "FindInFilesFilter"=dword:00000000  
   "NotOpenFileFilter"=dword:00000000  
   "SortPriority"=dword:000003e8  
\{C061DB26-5833-11D2-96F5-000000000000}\Filters\2  
      (Folder 2 contains settings for Find in Files filters.)  
   @="#5"  
   "CommonOpenFilesFilter"=dword:00000000  
   "CommonFindFilesFilter"=dword:00000000  
   "NotAddExistingItemFilter"=dword:00000001  
   "FindInFilesFilter"=dword:00000001  
   "NotOpenFileFilter"=dword:00000000  
   "SortPriority"=dword:000003e8  
\{C061DB26-5833-11D2-96F5-000000000000}\AddItemTemplates\TemplateDirs\ {ACEF4EB2-57CF-11D2-96F4-000000000000}\1 (Second GUID indicates the registered project type for the Add Items templates.)  
   @="#6"  
   "TemplatesDir"="<Visual Studio SDK installation path>\\VSIntegration\\Archive9.0\\FigPkgs\\FigPrj\\                    FigPrjProjectItems"  
   "SortPriority"=dword:00000064  
```  
  
|Name|형식|데이터|설명|  
|----------|--------|---------|--------|  
|`@`|REG\_SZ|`FigPrj Project`|이 형식의 프로젝트의 기본 이름입니다.|  
|`DisplayName`|REG\_SZ|`#%IDS_PROJECT_TYPE%`|위성 DLL을 검색할 리소스 ID 이름이 패키지에서 패키지를 등록 합니다.|  
|`Package`|REG\_SZ|`%CLSID_Package%`|클래스 ID가 있는 VSPackage 패키지에서 패키지를 등록 합니다.|  
|`ProjectTemplatesDir`|REG\_SZ|`%TEMPLATE_PATH%\FigPrjProjects`|프로젝트 서식 파일의 기본 경로입니다.  이러한 새 프로젝트 템플릿에서 표시 되는 파일입니다.|  
|`ItemTemplatesDir`|REG\_SZ|`%TEMPLATE_PATH% \FigPrjProjectItems`|프로젝트 항목 템플릿 파일의 기본 경로입니다.  이러한 새 항목 추가 템플릿을 통해 표시 되는 파일입니다.|  
|`DisplayProjectFileExtensions`|REG\_SZ|`#%IDS_DISPLAY_PROJ_FILE_EXT%`|활성화를 구현 하 여 IDE를  **열기** 대화 상자.|  
|`PossibleProjectExtensions`|REG\_SZ|`figp`|IDE에서 열려 있는 프로젝트 \(프로젝트 공장\)이 프로젝트 형식으로 처리할지 여부를 결정 하는 데 사용 합니다.  두 개 이상의 항목의 형식을 세미콜론으로 구분 된 목록입니다.  예를 들어 "vdproj; vdp"입니다.|  
|`DefaultProjectExtension`|REG\_SZ|`.figp`|IDE에서 기본 파일 이름 확장명으로 이름으로 저장 작업을 사용 합니다.|  
|`Filter Settings`|REG\_DWORD|다양 한 문 및 표 다음 설명을 참조 하십시오.|이러한 설정은 UI 대화 상자에서 파일 표시에 대 한 다양 한 필터를 설정 하는 데 사용 됩니다.|  
|`@`|REG\_SZ|`#%IDS_ADDITEM_TEMPLATES_ENTRY%`|추가 항목 템플릿 리소스 ID입니다.|  
|`TemplatesDir`|REG\_SZ|`%TEMPLATE_PATH%\FigPrjProjectItems`|대화 상자에 표시 되는 프로젝트 항목의 경로  **새 항목 추가** 템플릿.|  
|`SortPriority`|REG\_DWORD|`100 (vcprx64)`|파일 표시의 트리 노드가 정렬 순서로 결정은  **새 항목 추가** 대화 상자.|  
  
 위 코드 세그먼트에 사용할 수 있는 필터 옵션은 다음과 같습니다.  
  
|필터 옵션|설명|  
|-----------|--------|  
|`CommonFindFilesFilter`|필터의 일반적인 필터 중 하나입니다의  **파일에서 찾기** 대화 상자.  일반 필터 하기 전에 일반적으로 표시 되지 않은 필터 필터 목록에 표시 됩니다.|  
|`CommonOpenFilesFilter`|필터의 일반적인 필터 중 하나입니다의  **파일 열기** 대화 상자.  일반 필터 하기 전에 일반적으로 표시 되지 않은 필터 필터 목록에 표시 됩니다.|  
|`FindInFilesFilter`|필터에 있는 필터 중 하나 임을 나타냅니다의  **파일에서 찾기** 대화 한 후 일반 필터가 나열 됩니다.|  
|`NotOpenFileFilter`|필터에서 사용 되지 않습니다 것을 나타냅니다에  **파일 열기** 대화 상자.|  
|`NotAddExistingItemFilter`|필터 추가에서 사용 되지 않습니다 것을 나타내는  **기존 항목** 대화 상자.|  
  
 기본적으로, 더 이러한 플래그 집합을 필터를 하나 없을 경우 필터에 사용 되는  **기존 항목 추가** 대화 상자 및 해당  **파일 열기**  공통 필터 나열 된 후 대화 상자.  필터에 사용 되는 것은  **파일에서 찾기** 대화 상자.  
  
 다음 예제에서는 \[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\9.0Exp\\Projects\] 키 아래에 위치 합니다.  
  
## 예제  
  
```  
{FE3BBBB6-72D5-11d2-9ACE-00C04F79A2A4} (The CLSID for Enterprise Projects)  
\{FE3BBBB6-72D5-11d2-9ACE-00C04F79A2A4}\AddItemTemplates\TemplateDirs\ {ACEF4EB2-57CF-11D2-96F4-000000000000}\1 (CLSID for projects of this type)  
   @="#7"  
   "TemplatesDir"="<Visual Studio SDK installation path>\\VSIntegration\\Archive9.0\\FigPrj\\FigPrjProjects"  
   "SortPriority"=dword:00000029  
   "NewProjectDialogOnly"=dword:00000000  
```  
  
|Name|형식|데이터|설명|  
|----------|--------|---------|--------|  
|`@`|REG\_SZ|`#%IDS_NEWPROJ_ TEMPLATES_ENTRY%`|새 프로젝트 서식 파일의 리소스 ID입니다.|  
|`TemplatesDir`|REG\_SZ|`%TEMPLATE_PATH%\FigPrjProjects`|기본적으로 등록 된 프로젝트 형식의 프로젝트에 대 한 경로.|  
|`SortPriority`|REG\_DWORD|`41 (x29)`|새 프로젝트 마법사 대화 상자에 표시 되는 프로젝트의 순서 집합을 정렬 합니다.|  
|`NewProjectDialogOnly`|REG\_DWORD|`0`|0이이 유형의 프로젝트를 새 프로젝트 대화 상자에 표시 되는지 나타냅니다.|  
  
 다음 예제에서는 \[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\9.0Exp\\Projects\] 키 아래에 위치 합니다.  
  
## 예제  
  
```  
\{A2FE74E1-B743-11d0-AE1A-00A0C90FFFC3} (CLSID for Miscellaneous Files projects)  
   @="Miscellaneous Files Project"  
\AddItemTemplates\TemplateDirs\{ACEF4EB2-57CF-11D2-96F4-000000000000}\1  
                                 (CLSID for Figures Project projects)  
   @="#6"  
   "TemplatesDir"="<Visual Studio SDK installation path>\\VSIntegration\\Archive9.0\\FigPkgs\\FigPrj\\                    FigPrjProjectItems"  
   "SortPriority"=dword:00000064  
```  
  
|Name|형식|데이터|설명|  
|----------|--------|---------|--------|  
|`@`|REG\_SZ|없음|기본값을 다음 항목에 대 한 기타 파일 프로젝트 항목 임을 나타냅니다.|  
|`@`|REG\_SZ|`#%IDS_ADDITEM_TEMPLATES_ENTRY%`|새 항목 추가 템플릿 파일에 대 한 리소스 ID 값입니다.|  
|`TemplatesDir`|REG\_SZ|`%TEMPLATE_PATH%\FigPrjProjectItems`|에 표시 되는 항목의 기본 경로  **새 항목 추가** 대화 상자.|  
|`SortPriority`|REG\_DWORD|`100 (vcprx64)`|트리 노드를 표시 하기 위한 정렬 순서를 설정에서  **새 항목 추가** 대화 상자.|  
  
 다음 예제에서는 \[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\9.0Exp\\Menus\] 키 아래에 있습니다.  
  
## 예제  
  
```  
"{ACEF4EB2-57CF-11D2-96F4-000000000000}"=",1000,1"  
```  
  
 메뉴 항목은 IDE 메뉴 정보를 검색 하는 데 사용 되는 리소스를 가리킵니다.  이 데이터 메뉴 데이터베이스로 병합 된 때 같은 키 레지스트리 MenusMerged 절에 추가 됩니다.  있는 VSPackage 아무것도 MenusMerged 섹션에서 직접 수정할 수 없습니다.  다음 표에서 데이터 필드에는 세 개의 쉼표\-구분 된\-필드입니다.  첫 번째 필드 메뉴 리소스 파일의 전체 경로 식별합니다.  
  
-   첫 번째 필드를 지정 하지 않으면 메뉴 리소스 위성 DLL VSPackage guid에서 로드 됩니다.  
  
 두 번째 필드 CTMENU 형식의 메뉴 리소스 ID를 식별합니다.  
  
-   리소스 ID를 지정 하 여 파일 경로 제공 하는 경우 메뉴 리소스의 전체 파일 경로에서 로드 됩니다.  
  
-   리소스 ID를 사용 하지만 파일 경로가 없는 경우 메뉴 리소스 위성 DLL을 로드 합니다.  
  
-   전체 파일 경로 제공 하는 리소스 ID를 지정 하지 않으면 파일을 불러온된 CTO 파일 수 있어야 합니다.  
  
 마지막 필드의 버전 번호를 CTMENU 리소스를 식별합니다.  버전 번호를 변경 하 여 다시 메뉴를 병합할 수 있습니다.  
  
|Name|형식|데이터|설명|  
|----------|--------|---------|--------|  
|%Clsid\_package%|REG\_SZ|`,1000,1`|메뉴 정보를 검색 하는 리소스입니다.|  
  
 다음 예제에서는 \[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\9.0Exp\\NewProjectTemplates\] 키 아래에 위치 합니다.  
  
```  
\TemplateDirs\{ACEF4EB2-57CF-11D2-96F4-000000000000}\1                (CLSID for Figures Project projects)  
   @="#7"  
   "TemplatesDir"="<Visual Studio SDK installation path>\\VSIntegration\\Archive9.0\\FigPkgs\\FigPrj\\FigPrjProjects"  
   "SortPriority"=dword:00000029  
   "NewProjectDialogOnly"=dword:00000000  
```  
  
|Name|형식|데이터|설명|  
|----------|--------|---------|--------|  
|`@`|REG\_SZ|`#%IDS_NEWPROJ_TEMPLATES_ENTRY%`|그림 프로젝트 새 프로젝트 서식 파일의 리소스 ID 값입니다.|  
|`TemplatesDir`|REG\_SZ|`%TEMPLATE_PATH%\FigPrjProjects`|새 프로젝트 디렉터리의 기본 경로입니다.  이 디렉터리의 항목에 표시할 수 있는  **새 프로젝트 마법사** 대화 상자.|  
|`SortPriority`|REG\_DWORD|`41 (x29)`|프로젝트 표시 됩니다 트리 노드를 순서 대로 설정 하는  **새 프로젝트** 대화 상자.|  
|`NewProjectDialogOnly`|REG\_DWORD|`0`|이 종류의 프로젝트에만 표시 되도록 나타냅니다의  **새 프로젝트** 대화 상자.|  
  
 다음 예제에서는 \[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\9.0Exp\\InstalledProducts\] 키 아래에 있습니다.  
  
```  
\FiguresProductSample  
   "Package"="{ACEF4EB2-57CF-11D2-96F4-000000000000}"  
   "UseInterface"=dword:00000001  
```  
  
|Name|형식|데이터|설명|  
|----------|--------|---------|--------|  
|`Package`|REG\_SZ|`%CLSID_Package%`|등록 된 Vspackage의 클래스 ID입니다.|  
|`UseInterface`|REG\_DWORD|`1`|1 UI이이 프로젝트와 상호 작용 하는 데 사용 될 의미 합니다.  0 UI 인터페이스 없이 나타냅니다.|  
  
 자주 새 프로젝트 형식을 제어 하는 The.vsz 파일에서 RELATIVE\_PATH 항목 포함.  이 경로의 다음 설치 키의 프로젝트 형식 \\ProductDir 항목에서 지정 된 경로에 상대적입니다.  
  
 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\7.0Exp\\Setup  
  
 예를 들어, 엔터프라이즈 프레임 워크 프로젝트 템플릿은 다음 레지스트리 항목을 추가합니다.  
  
 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\7.0Exp\\Setup\\EF\\ProductDir C:\\Program 상자 Visual Studio\\EnterpriseFrameworks\\ \=  
  
 즉, PROJECT\_TYPE를 포함 하는 경우 \= EF 항목.vsz 파일에.vsz 파일을 ProductDir 디렉터리에서 이전에 지정 된 환경 찾습니다.  
  
## 참고 항목  
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [프로젝트 모델의 요소](../../extensibility/internals/elements-of-a-project-model.md)   
 [프로젝트 팩터리를 사용 하 여 프로젝트 인스턴스 만들기](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)