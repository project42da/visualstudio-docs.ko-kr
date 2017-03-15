---
title: "MT Task | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCManifestTool.ResourceOutputFileName"
  - "VC.Project.VCManifestTool.SuppressDependencyElement"
  - "VC.Project.VCManifestTool.ManifestFromManagedAssembly"
  - "VC.Project.VCManifestTool.GenerateCategoryTags"
  - "VC.Project.VCManifestTool.EnableDPIAwareness"
  - "vc.task.mt"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
  - "C++"
helpviewer_keywords: 
  - "MSBUILD (Visual C++), MT task"
  - "MT task (MSBuild (Visual C++))"
ms.assetid: bb94913c-1042-4968-9f08-b394518e899f
caps.latest.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 6
---
# MT Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Microsoft Manifest 도구인 mt.exe를 래핑합니다.  자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"를 참조하십시오.  
  
## 매개 변수  
 다음 표에서는 **MT** 작업의 매개 변수에 대해 설명합니다.  대부분의 작업 매개 변수 및 일부 매개 변수 집합은 명령줄 옵션에 해당합니다.  
  
> [!NOTE]
>  mt.exe 설명서는 명령줄 옵션의 접두사로 하이픈\(**\-**\)을 사용하지만 이 항목은 슬래시\(**\/**\)를 사용합니다.  두 접두사를 사용할 수 있습니다.  
  
|Parameter|설명|  
|---------------|--------|  
|**AdditionalManifestFiles**|선택적 **String\[\]** 매개 변수입니다.<br /><br /> 하나 이상의 매니페스트 파일의 이름을 지정합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/manifest** 옵션을 참조하십시오.|  
|**AdditionalOptions**|선택적 **String** 매개 변수입니다.<br /><br /> 명령줄 옵션의 목록입니다.  예를 들어, "*\/option1 \/option2 \/option\#*"입니다.  이 매개 변수를 사용하여 다른 **MT** 작업 매개 변수로 표현되지 않는 명령줄 옵션을 지정합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"를 참조하십시오.|  
|**AssemblyIdentity**|선택적 **String** 매개 변수입니다.<br /><br /> 매니페스트의 **assemblyIdentity** 요소의 특성 값을 지정합니다.  `name` 특성의 값이 첫 번째 구성 요소가 있고 *\<attribute name\>\=\<attribute\_value\>* 양식의 이름\/값 쌍이 하나 이상 뒤에 오는 쉼표로 구분된 목록을 지정합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/identity** 옵션을 참조하십시오.|  
|**ComponentFileName**|선택적 **String** 매개 변수입니다.<br /><br /> .rgs 또는 .tlb 파일에서 빌드할 동적 연결 라이브러리의 이름을 지정합니다.  이 매개 변수는 **RegistrarScriptFile** 또는 **TypeLibraryFile** MT 작업 매개 변수를 지정하는 경우 필요합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/dll** 옵션을 참조하십시오.|  
|**DependencyInformationFile**|선택적 **String** 매개 변수입니다.<br /><br /> Visual Studio가 매니페스트 도구에 대한 빌드 종속성 정보를 추적하는 데 사용하는 종속성 정보 파일을 지정합니다.|  
|**EmbedManifest**|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 어셈블리에 매니페스트 파일이 들어 있습니다.  `false`인 경우 독립 실행형 매니페스트 파일로 만듭니다.|  
|**EnableDPIAwareness**|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 응용 프로그램을 DPI 인식으로 표시하는 매니페스트 정보에 추가합니다.  DPI 인식 응용 프로그램을 작성하면 다양한 높은 DPI 디스플레이 설정에서 일관성 있게 보이도록 사용자 인터페이스를 만들 수 있습니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "High DPI"를 참조하십시오.|  
|**GenerateCatalogFiles**|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 카탈로그 정의\(.cdf\) 파일을 생성합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737)의 "Mt.exe"에서 **\/makecdfs** 옵션을 참조하십시오.|  
|**GenerateCategoryTags**|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 범주 태그가 생성되도록 합니다.  이 매개 변수가 `true`인 경우 **ManifestFromManagedAssembly MT** 작업 매개 변수도 지정해야 합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/category** 옵션을 참조하십시오.|  
|**InputResourceManifests**|선택적 **String** 매개 변수입니다.<br /><br /> 지정한 식별자가 있는 형식 RT\_MANIFEST의 리소스에서 매니페스트를 입력합니다.  선택적 `resource_id` 매개 변수가 음수가 아니고 16비트 숫자가 있는 *\<file\>\[***;***\[***\#***\]\<resource\_id\>\]* 양식의 리소스를 지정합니다.<br /><br /> `resource_id`가 지정되지 않은 경우 CREATEPROCESS\_MANIFEST\_RESOURCE 기본값\(1\)이 사용됩니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/inputresource** 옵션을 참조하십시오.|  
|**ManifestFromManagedAssembly**|선택적 **String** 매개 변수입니다.<br /><br /> 지정된 관리되는 어셈블리에서 매니페스트를 생성합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/managedassemblyname** 옵션을 참조하십시오.|  
|**ManifestToIgnore**|선택적 **String** 매개 변수입니다.<br /><br /> 사용되지 않습니다.|  
|**OutputManifestFile**|선택적 **String** 매개 변수입니다.<br /><br /> 출력 매니페스트의 이름을 지정합니다.  이 매개 변수를 생략하고 하나의 매니페스트에서 작업 중인 경우 해당 매니페스트는 이 위치에서 수정됩니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/out** 옵션을 참조하십시오.|  
|**OutputResourceManifests**|선택적 **String** 매개 변수입니다.<br /><br /> 지정한 식별자가 있는 형식 RT\_MANIFEST의 리소스로 매니페스트를 출력합니다.  선택적 `resource_id` 매개 변수가 음수가 아니고 16비트 숫자가 있는 *\<file\>\[***;***\[***\#***\]\<resource\_id\>\]* 양식의 리소스를 지정합니다.<br /><br /> `resource_id`가 지정되지 않은 경우 CREATEPROCESS\_MANIFEST\_RESOURCE 기본값\(1\)이 사용됩니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/outputresource** 옵션을 참조하십시오.|  
|**RegistrarScriptFile**|선택적 **String** 매개 변수입니다.<br /><br /> 등록이 필요 없는 COM 매니페스트 지원에 사용할 등록자 스크립트\(.rgs\) 파일의 이름을 지정합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/rgs** 옵션을 참조하십시오.|  
|**ReplacementsFile**|선택적 **String** 매개 변수입니다.<br /><br /> 등록자 스크립트\(.rgs\) 파일에서 대체할 수 있는 문자열의 값이 들어 있는 파일을 지정합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/replacements** 옵션을 참조하십시오.|  
|**ResourceOutputFileName**|선택적 **String** 매개 변수입니다.<br /><br /> 프로젝트 출력에 매니페스트를 포함하는 데 사용한 출력 리소스 파일을 지정합니다.|  
|**Sources**|선택적 `ITaskItem[]` 매개 변수입니다.<br /><br /> 공백으로 구분된 매니페스트 소스 파일 목록을 지정합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/manifest** 옵션을 참조하십시오.|  
|**SuppressDependencyElement**|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 종속 요소 없이 매니페스트를 생성합니다.  이 매개 변수가 `true`인 경우 **ManifestFromManagedAssembly MT** 작업 매개 변수를 지정합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/nodependency** 옵션을 참조하십시오.|  
|**SuppressStartupBanner**|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 작업을 시작할 때 저작권과 버전 번호 메시지가 표시되지 않도록 합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/nologo** 옵션을 참조하십시오.|  
|**TrackerLogDirectory**|선택적 `String` 매개 변수입니다.<br /><br /> 이 작업에 대한 추적 로그가 저장되는 중간 디렉터리를 지정합니다.|  
|**TypeLibraryFile**|선택적 **String** 매개 변수입니다.<br /><br /> 형식 라이브러리\(.tlb\) 파일의 이름을 지정합니다.  이 매개 변수를 지정하는 경우 **ComponentFileName MT** 작업 매개 변수도 지정합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/tlb** 옵션을 참조하십시오.|  
|**UpdateFileHashes**|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 **UpdateFileHashesSearchPath MT** 작업 매개 변수에 의해 지정된 경로에서 파일의 해시 값을 계산한 다음 계산된 값을 사용하여 매니페스트의 **file** 요소의 **hash** 특성 값을 업데이트합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/hashupdate** 옵션을 참조하십시오.  또한 이 테이블의 **UpdateFileHashesSearchPath** 매개 변수를 참조하십시오.|  
|**UpdateFileHashesSearchPath**|선택적 `String` 매개 변수입니다.<br /><br /> 파일 해시를 업데이트할 때 사용할 검색 경로를 지정합니다.  **UpdateFileHashes MT** 작업 매개 변수와 함께 이 매개 변수를 사용합니다.<br /><br /> 자세한 내용은 이 표의 **UpdateFileHashes** 매개 변수를 참조하십시오.|  
|**VerboseOutput**|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 디버깅에 대한 자세한 정보를 표시합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Mt.exe"에서 **\/verbose** 옵션을 참조하십시오.|  
  
## 설명  
  
## 참고 항목  
 [Task Reference](../msbuild/msbuild-task-reference.md)