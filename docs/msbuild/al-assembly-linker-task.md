---
title: "AL (Assembly Linker) Task | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#AL"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "AL task [MSBuild]"
  - "MSBuild, AL task"
ms.assetid: 2ddefbf2-5662-4d55-99a6-ac383bf44560
caps.latest.revision: 22
caps.handback.revision: 22
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# AL (Assembly Linker) Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

AL 작업에서는 [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]와 함께 배포되는 도구인 AL.exe를 래핑합니다.  이 어셈블리 링커 도구는 모듈 또는 리소스 파일인 하나 이상의 파일에서 매니페스트가 있는 어셈블리를 만드는 데 사용됩니다.  컴파일러와 개발 환경에 이러한 기능이 이미 있으므로 대부분의 경우 이 작업을 직접 사용할 필요는 없습니다.  어셈블리 링커는 혼합 언어 개발 환경에서 여러 구성 요소 파일을 만드는 경우처럼 여러 구성 요소 파일에서 하나의 어셈블리를 만들어야 하는 개발자에게 가장 알맞은 도구입니다.  이 작업에서는 모듈을 단일 어셈블리 파일로 결합하지 않습니다. 결과 어셈블리를 올바르게 로드하려면 개별 모듈을 분산하여 사용할 수 있어야 합니다.  AL.exe에 대한 자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)를 참조하십시오.  
  
## 매개 변수  
 다음 표에서는 `AL` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`AlgorithmID`|선택적 `String` 매개 변수입니다.<br /><br /> 어셈블리 매니페스트가 포함된 파일을 제외하고 다중 파일 어셈블리에 있는 모든 파일을 해시하는 알고리즘을 지정합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/algid` 옵션에 대한 설명을 참조하십시오.|  
|`BaseAddress`|선택적 `String` 매개 변수입니다.<br /><br /> 런타임에 DLL이 사용자의 컴퓨터에 로드되는 주소를 지정합니다.  운영 체제가 프로세스 공간에서 DLL을 재배치하게 놔두지 않고 DLL의 기본 주소를 지정하면 응용 프로그램의 로드 속도가 빨라집니다.  이 매개 변수는 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)의 \/base\[address\] 옵션에 해당합니다.|  
|`CompanyName`|선택적 `String` 매개 변수입니다.<br /><br /> 어셈블리의 `Company` 필드에 대한 문자열을 지정합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/comp[any]` 옵션에 대한 설명을 참조하십시오.|  
|`Configuration`|선택적 `String` 매개 변수입니다.<br /><br /> 어셈블리의 `Configuration` 필드에 대한 문자열을 지정합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/config[uration]` 옵션에 대한 설명을 참조하십시오.|  
|`Copyright`|선택적 `String` 매개 변수입니다.<br /><br /> 어셈블리의 `Copyright` 필드에 대한 문자열을 지정합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/copy[right]` 옵션에 대한 설명을 참조하십시오.|  
|`Culture`|선택적 `String` 매개 변수입니다.<br /><br /> 어셈블리에 연결할 culture 문자열을 지정합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/c[ulture]` 옵션에 대한 설명을 참조하십시오.|  
|`DelaySign`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 어셈블리에 공개 키만 배치하고, `false`이면 어셈블리에 완전히 서명합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/delay[sign]` 옵션에 대한 설명을 참조하십시오.|  
|`Description`|선택적 `String` 매개 변수입니다.<br /><br /> 어셈블리의 `Description` 필드에 대한 문자열을 지정합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/descr[iption]` 옵션에 대한 설명을 참조하십시오.|  
|`EmbedResources`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 지정된 리소스를 어셈블리 매니페스트가 포함된 이미지에 포함합니다.  이 작업에서는 리소스 파일의 내용을 이미지에 복사합니다.  이 매개 변수에 전달되는 항목에는 `LogicalName` 및 `Access`라는 선택적 메타데이터가 연결될 수 있습니다.  `LogicalName` 메타데이터는 리소스에 대한 내부 식별자를 지정하는 데 사용됩니다.  `Access` 메타데이터를 `private`로 설정하면 다른 어셈블리에서 리소스에 접근할 수 없도록 할 수 있습니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/embed[resource]` 옵션에 대한 설명을 참조하십시오.|  
|`EvidenceFile`|선택적 `String` 매개 변수입니다.<br /><br /> 지정된 파일을 `Security.Evidence`라는 리소스 이름으로 어셈블리에 포함합니다.<br /><br /> 기본 리소스에는 `Security.Evidence`를 사용할 수 없습니다.  이 매개 변수는 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)의 `/e[vidence]` 옵션에 해당합니다.|  
|`ExitCode`|선택적 `Int32` 읽기 전용 출력 매개 변수입니다.<br /><br /> 실행한 명령에서 제공하는 종료 코드를 지정합니다.|  
|`FileVersion`|선택적 `String` 매개 변수입니다.<br /><br /> 어셈블리의 `File Version` 필드에 대한 문자열을 지정합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/fileversion` 옵션에 대한 설명을 참조하십시오.|  
|`Flags`|선택적 `String` 매개 변수입니다.<br /><br /> 어셈블리의 `Flags` 필드에 대한 값을 지정합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/flags` 옵션에 대한 설명을 참조하십시오.|  
|`GenerateFullPaths`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 작업에서 오류 메시지에 보고되는 모든 파일에 절대 경로를 사용하도록 합니다.  이 매개 변수는 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)의 `/fullpaths` 옵션에 해당합니다.|  
|`KeyContainer`|선택적 `String` 매개 변수입니다.<br /><br /> 키 쌍을 보관하는 컨테이너를 지정합니다.  어셈블리 매니페스트에 공개 키를 삽입하여 어셈블리에 서명\(강력한 이름을 부여\)합니다.  그런 다음 작업에서 개인 키를 사용하여 최종 어셈블리에 서명합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/keyn[ame]` 옵션에 대한 설명을 참조하십시오.|  
|`KeyFile`|선택적 `String` 매개 변수입니다.<br /><br /> 어셈블리에 서명하기 위한 키 쌍 또는 공개 키만을 포함하는 파일을 지정합니다.  컴파일러는 공개 키를 어셈블리 매니페스트에 삽입한 다음 개인 키를 사용하여 최종 어셈블리에 서명합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/keyf[ile]` 옵션에 대한 설명을 참조하십시오.|  
|`LinkResources`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 지정한 리소스 파일을 어셈블리에 링크합니다.  리소스가 어셈블리의 일부가 되지만 파일은 복사되지 않습니다.  이 매개 변수에 전달되는 항목에는 `LogicalName`, `Target` 및 `Access`라는 선택적 메타데이터가 연결될 수 있습니다.  `LogicalName` 메타데이터는 리소스에 대한 내부 식별자를 지정하는 데 사용됩니다.  `Target` 메타데이터는 작업에서 파일을 복사할 대상 경로와 파일 이름을 지정할 수 있습니다. 이 경로와 파일 이름에 따라 이 새 파일이 어셈블리로 컴파일됩니다.  `Access` 메타데이터를 `private`로 설정하면 다른 어셈블리에서 리소스에 접근할 수 없도록 할 수 있습니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/link[resource]` 옵션에 대한 설명을 참조하십시오.|  
|`MainEntryPoint`|선택적 `String` 매개 변수입니다.<br /><br /> 모듈을 실행 파일로 변환할 때 진입점으로 사용할 메서드의 정규화된 이름\(*class.method*\)을 지정합니다.  이 매개 변수는 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)의 `/main` 옵션에 해당합니다.|  
|`OutputAssembly`|필수적 <xref:Microsoft.Build.Framework.ITaskItem> 출력 매개 변수입니다.<br /><br /> 이 작업으로 생성되는 파일의 이름을 지정합니다.  이 매개 변수는 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)의 `/out` 옵션에 해당합니다.|  
|`Platform`|선택적 `String` 매개 변수입니다.<br /><br /> 이 코드를 실행할 수 있는 플랫폼을 `x86`, `Itanium`, `x64` 또는 `anycpu` 중 하나로 제한합니다.  기본값은 `anycpu`입니다.  이 매개 변수는 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)의 `/platform` 옵션에 해당합니다.|  
|`ProductName`|선택적 `String` 매개 변수입니다.<br /><br /> 어셈블리의 `Product` 필드에 대한 문자열을 지정합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/prod[uct]` 옵션에 대한 설명을 참조하십시오.|  
|`ProductVersion`|선택적 `String` 매개 변수입니다.<br /><br /> 어셈블리의 `ProductVersion` 필드에 대한 문자열을 지정합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/productv[ersion]` 옵션에 대한 설명을 참조하십시오.|  
|`ResponseFiles`|선택적 `String[]` 매개 변수입니다.<br /><br /> 어셈블리 링커로 전달할 추가 옵션이 들어 있는 지시 파일을 지정합니다.|  
|`SdkToolsPath`|선택적 `String` 매개 변수입니다.<br /><br /> resgen.exe와 같이 SDK 도구에 대한 경로를 지정합니다.|  
|`SourceModules`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 어셈블리로 컴파일할 하나 이상의 모듈입니다.  모듈은 결과 어셈블리의 매니페스트에 나열되며, 어셈블리를 로드할 수 있으려면 분산하여 사용할 수 있어야 합니다.  이 매개 변수에 전달되는 항목에는 `Target`이라는 추가 메타데이터가 연결될 수 있습니다. 이 메타데이터는 작업에서 파일을 복사할 대상 경로와 파일 이름을 지정합니다. 이 경로와 파일 이름에 따라 이 새 파일이 어셈블리로 컴파일됩니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에 대한 설명을 참조하십시오.  이 매개 변수는 특정 스위치가 없는 Al.exe로 전달되는 모듈의 목록에 해당합니다.|  
|`TargetType`|선택적 `String` 매개 변수입니다.<br /><br /> 출력 파일의 파일 형식을 `library`\(코드 라이브러리\), `exe`\(콘솔 응용 프로그램\) 또는 `win`\(Windows 기반 응용 프로그램\)으로 지정합니다.  기본값은 `library`입니다.  이 매개 변수는 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)의 `/t[arget]` 옵션에 해당합니다.|  
|`TemplateFile`|선택적 `String` 매개 변수입니다.<br /><br /> culture 필드를 제외한 모든 어셈블리 메타데이터를 상속받을 상위 어셈블리를 지정합니다.  지정한 어셈블리에는 강력한 이름을 사용해야 합니다.<br /><br /> `TemplateFile` 매개 변수를 사용하여 만든 어셈블리는 위성 어셈블리입니다.  이 매개 변수는 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)의 `/template` 옵션에 해당합니다.|  
|`Timeout`|선택적 `Int32` 매개 변수입니다.<br /><br /> 작업 실행 파일이 얼마 후에 종료될 지를 밀리초 단위로 지정합니다.  기본값은 제한 시간이 없음을 나타내는 `Int.MaxValue`입니다.|  
|`Title`|선택적 `String` 매개 변수입니다.<br /><br /> 어셈블리의 `Title` 필드에 대한 문자열을 지정합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/title` 옵션에 대한 설명을 참조하십시오.|  
|`ToolPath`|선택적 `String` 매개 변수입니다.<br /><br /> 작업에서 내부 실행 파일\(Al.exe\)을 로드할 위치를 지정합니다.  이 매개 변수를 지정하지 않으면 작업에서는 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]를 실행하고 있는 버전의 Framework에 해당하는 SDK 설치 경로가 사용됩니다.|  
|`Trademark`|선택적 `String` 매개 변수입니다.<br /><br /> 어셈블리의 `Trademark` 필드에 대한 문자열을 지정합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/trade[mark]` 옵션에 대한 설명을 참조하십시오.|  
|`Version`|선택적 `String` 매개 변수입니다.<br /><br /> 이 어셈블리의 버전 정보를 지정합니다.  문자열의 형식은 *major.minor.build.revision*입니다.  기본값은 0입니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/v[ersion]` 옵션에 대한 설명을 참조하십시오.|  
|`Win32Icon`|선택적 `String` 매개 변수입니다.<br /><br /> .ico 파일을 어셈블리에 삽입합니다.  .Ico 파일 출력 파일을 원하는 모양으로 파일 탐색기를 제공합니다.  이 매개 변수는 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)의 `/win32icon` 옵션에 해당합니다.|  
|`Win32Resource`|선택적 `String` 매개 변수입니다.<br /><br /> Win32 리소스\(.res 파일\)를 출력 파일에 삽입합니다.  자세한 내용은 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)에서 `/win32res` 옵션에 대한 설명을 참조하십시오.|  
  
## 설명  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.ToolTask> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.ToolTaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [ToolTaskExtension Base Class](../msbuild/tooltaskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 지정한 옵션을 사용하여 어셈블리를 만듭니다.  
  
```  
<AL  
    EmbedResources="@(EmbeddedResource)"  
    Culture="%(EmbeddedResource.Culture)"  
    TemplateFile="@(IntermediateAssembly)"  
    KeyContainer="$(KeyContainerName)"  
    KeyFile="$(KeyOriginatorFile)"  
    DelaySign="$(DelaySign)"  
  
    OutputAssembly=  
       "%(EmbeddedResource.Culture)\$(TargetName).resources.dll">  
  
    <Output TaskParameter="OutputAssembly"  
        ItemName="SatelliteAssemblies"/>  
</AL>  
```  
  
## 참고 항목  
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [작업](../msbuild/msbuild-tasks.md)