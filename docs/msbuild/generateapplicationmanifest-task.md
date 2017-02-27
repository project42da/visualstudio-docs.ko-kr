---
title: "GenerateApplicationManifest Task | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#GenerateApplicationManifest"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MSBuild, GenerateApplicationManifest task"
  - "HostInBrowser property (MSBuild)"
  - "GenerateApplicationManifest task [MSBuild]"
ms.assetid: a494102b-0cb2-4755-8e2a-d2c0f39fac1d
caps.latest.revision: 24
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 24
---
# GenerateApplicationManifest Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트나 네이티브 매니페스트를 생성합니다.  네이티브 매니페스트는 구성 요소에 대한 고유한 ID를 정의하고 구성 요소를 이루는 모든 어셈블리와 파일을 식별하여 구성 요소를 설명합니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트는 응용 프로그램의 진입점을 지정하고 응용 프로그램 보안 수준을 지정하여 네이티브 매니페스트를 확장합니다.  
  
## 매개 변수  
 다음 표에서는 `GenerateApplicationManifest` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`AssemblyName`|선택적 `String` 매개 변수입니다.<br /><br /> 생성된 매니페스트에 대한 어셈블리 ID의 `Name` 필드를 지정합니다.  이 매개 변수를 지정하지 않으면 `EntryPoint` 또는 `InputManifest` 매개 변수에서 이름이 유추됩니다.  이름을 만들 수 없으면 작업에서 오류가 throw됩니다.|  
|`AssemblyVersion`|선택적 `String` 매개 변수입니다.<br /><br /> 생성된 매니페스트에 대한 어셈블리 ID의 `Version` 필드를 지정합니다.  이 매개 변수를 지정하지 않으면 기본값으로 "1.0.0.0"이 사용됩니다.|  
|`ClrVersion`|선택적 `String` 매개 변수입니다.<br /><br /> 응용 프로그램에 필요한 CLR\(공용 언어 런타임\)의 최소 버전을 지정합니다.  기본값은 빌드 시스템에 사용되고 있는 CLR 버전입니다.  네이티브 매니페스트를 생성하는 작업에서는 이 매개 변수가 무시됩니다.|  
|`ConfigFile`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 응용 프로그램 구성 파일이 들어 있는 항목을 지정합니다.  네이티브 매니페스트를 생성하는 작업에서는 이 매개 변수가 무시됩니다.|  
|`Dependencies`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 생성된 매니페스트에 대한 종속 어셈블리 집합을 정의하는 항목 목록을 지정합니다.  추가 배포 상태와 종속 형식을 지정하여 항목 메타데이터에서 각 항목을 추가로 설명할 수 있습니다.  자세한 내용은 아래의 "항목 메타데이터" 단원을 참조하십시오.|  
|`Description`|선택적 `String` 매개 변수입니다.<br /><br /> 응용 프로그램이나 구성 요소에 대한 설명을 지정합니다.|  
|`EntryPoint`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 생성된 매니페스트 어셈블리에 대한 진입점을 나타내는 단일 항목을 지정합니다.<br /><br /> [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트의 경우 이 매개 변수는 응용 프로그램을 실행할 때 시작하는 어셈블리를 지정합니다.|  
|`ErrorReportUrl`|선택적 [String](assetId:///String?qualifyHint=False&autoUpgrade=True) 매개 변수입니다.<br /><br /> ClickOnce 설치 시 오류 보고 대화 상자에 표시되는 웹 페이지의 URL을 지정합니다.|  
|`FileAssociations`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> ClickOnce 배포 매니페스트와 연결되는 하나 이상의 파일 형식에 대한 목록을 가져오거나 지정합니다.<br /><br /> 파일 연결은 .NET Framework 3.5 이상을 대상으로 할 경우에만 유효합니다.|  
|`Files`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 매니페스트에 포함할 파일입니다.  각 파일의 전체 경로를 지정합니다.|  
|`HostInBrowser`|선택적 [Boolean](assetId:///Boolean?qualifyHint=False&autoUpgrade=True) 매개 변수입니다.<br /><br /> `true`인 경우 응용 프로그램이 브라우저에 \(WPF 웹 브라우저 응용 프로그램으로\) 호스팅됩니다.|  
|`IconFile`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 응용 프로그램 아이콘 파일을 지정합니다.  응용 프로그램 아이콘은 생성된 응용 프로그램 매니페스트에 표현되고, 시작 메뉴와 프로그램 추가\/제거 대화 상자에 사용됩니다.  이 입력을 지정하지 않으면 기본 아이콘이 사용됩니다.  네이티브 매니페스트를 생성하는 작업에서는 이 매개 변수가 무시됩니다.|  
|`InputManifest`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> 매니페스트 생성기에 대한 기반으로 사용할 입력 XML 문서를 지정합니다.  이렇게 하면 응용 프로그램 보안이나 사용자 지정 매니페스트 정의 같은 구조화된 데이터를 출력 매니페스트에 반영할 수 있습니다.  XML 문서의 루트 요소는 asmv1 네임스페이스의 어셈블리 노드여야 합니다.|  
|`IsolatedComReferences`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 생성된 매니페스트에서 격리할 COM 구성 요소를 지정합니다.  이 매개 변수는 "등록이 필요 없는 COM" 배포를 위한 COM 구성 요소 격리 기능을 지원합니다.  이러한 기능은 표준 COM 등록 정의를 사용하여 매니페스트를 자동으로 생성하는 방식으로 이루어집니다.  그러나 이 기능이 올바르게 작동하려면 COM 구성 요소가 빌드 컴퓨터에 등록되어 있어야 합니다.|  
|`ManifestType`|선택적 `String` 매개 변수입니다.<br /><br /> 생성할 매니페스트의 형식을 지정합니다.  이 매개 변수는 다음 값을 가질 수 있습니다.<br /><br /> -   `Native`<br />-   `ClickOnce`<br /><br /> 이 매개 변수를 지정하지 않으면 작업이 `ClickOnce`로 기본 설정됩니다.|  
|`MaxTargetPath`|선택적 `String` 매개 변수입니다.<br /><br /> [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 배포에서 사용할 수 있는 파일 경로의 최대 길이를 지정합니다.  이 값을 지정하면 응용 프로그램의 각 파일 경로 길이가 이 제한값을 기준으로 검사됩니다.  한 항목이라도 제한을 초과하면 빌드 경고가 발생합니다.  이 입력을 지정하지 않거나 0으로 지정하면 검사를 수행하지 않습니다.  네이티브 매니페스트를 생성하는 작업에서는 이 매개 변수가 무시됩니다.|  
|`OSVersion`|선택적 `String` 매개 변수입니다.<br /><br /> 응용 프로그램에 필요한 최소 OS\(운영 체제\) 버전을 지정합니다.  예를 들어, "5.1.2600.0"이라는 값은 운영 체제가 Windows XP임을 나타냅니다.  이 매개 변수를 지정하지 않으면 .NET Framework를 지원하는 최소 OS인 Windows 98 Second Edition을 나타내는 "4.10.0.0"이 값으로 사용됩니다.  네이티브 매니페스트를 생성하는 작업에서는 이 입력이 무시됩니다.|  
|`OutputManifest`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 출력 매개 변수입니다.<br /><br /> 생성된 출력 매니페스트 파일의 이름을 지정합니다.  이 매개 변수를 지정하지 않으면 생성된 매니페스트의 ID에서 출력 파일의 이름이 유추됩니다.|  
|`Platform`|선택적 `String` 매개 변수입니다.<br /><br /> 응용 프로그램의 대상 플랫폼을 지정합니다.  이 매개 변수는 다음 값을 가질 수 있습니다.<br /><br /> -   `AnyCPU`<br />-   `x86`<br />-   `x64`<br />-   `Itanium`<br /><br /> 이 매개 변수를 지정하지 않으면 작업이 `AnyCPU`로 기본 설정됩니다.|  
|`Product`|선택적 `String` 매개 변수입니다.<br /><br /> 응용 프로그램의 이름을 지정합니다.  이 매개 변수를 지정하지 않으면 생성된 매니페스트의 ID에서 이름이 유추됩니다.  이 이름은 시작 메뉴에서 바로 가기 이름에 사용되고 프로그램 추가\/제거 대화 상자에 나타나는 이름의 일부로도 사용됩니다.|  
|`Publisher`|선택적 `String` 매개 변수입니다.<br /><br /> 응용 프로그램의 게시자를 지정합니다.  이 매개 변수를 지정하지 않으면 등록된 사용자나 생성된 매니페스트의 ID에서 이름이 유추됩니다.  이 이름은 시작 메뉴에서 폴더 이름에 사용되고 프로그램 추가\/제거 대화 상자에 나타나는 이름의 일부로도 사용됩니다.|  
|`RequiresMinimumFramework35SP1`|선택적 `Boolean` 매개 변수입니다.<br /><br /> True인 경우 응용 프로그램에 .NET Framework 3.5 SP1 이상의 최신 버전이 필요합니다.|  
|`TargetCulture`|선택적 `String` 매개 변수입니다.<br /><br /> 응용 프로그램의 culture를 식별하고 생성된 매니페스트에 대한 어셈블리 ID의 `Language` 필드를 지정합니다.  이 매개 변수를 지정하지 않으면 응용 프로그램이 culture 고정적인 것으로 간주합니다.|  
|`TargetFrameworkMoniker`|선택적 assetId:///String?qualifyHint=False&autoUpgrade=True 매개 변수입니다.<br /><br /> 대상 프레임워크 모니커를 지정합니다.|  
|`TargetFrameworkProfile`|선택적 assetId:///String?qualifyHint=False&autoUpgrade=True 매개 변수입니다.<br /><br /> 대상 프레임워크 프로필을 지정합니다.|  
|`TargetFrameworkSubset`|선택적 assetId:///String?qualifyHint=False&autoUpgrade=True 매개 변수입니다.<br /><br /> 대상으로 할 .NET Framework 하위 집합의 이름을 지정합니다.|  
|`TargetFrameworkVersion`|선택적 assetId:///String?qualifyHint=False&autoUpgrade=True 매개 변수입니다.<br /><br /> 프로젝트의 대상 .NET Framework의 프로필을 지정합니다.|  
|`TrustInfoFile`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> 응용 프로그램 보안을 지정하는 XML 문서를 나타냅니다.  XML 문서의 루트 요소는 asmv2 네임스페이스의 trustInfo 노드여야 합니다.  네이티브 매니페스트를 생성하는 작업에서는 이 매개 변수가 무시됩니다.|  
|`UseApplicationTrust`|선택적 assetId:///Boolean?qualifyHint=False&autoUpgrade=True 매개 변수입니다.<br /><br /> true인 경우 `Product`, `Publisher` 및 `SupportUrl` 속성이 응용 프로그램 매니페스트에 기록됩니다.|  
  
## 설명  
 위에 열거된 매개 변수 뿐만 아니라, 이 작업은 <xref:Microsoft.Build.Tasks.GenerateManifestBase> 클래스의 매개 변수를 상속받습니다, 이 클래스는 <xref:Microsoft.Build.Utilities.Task> 클래스로부터 자기 자신을 상속받습니다.  작업 클래스의 매개 변수 목록을 보려면 [Task Base Class](../msbuild/task-base-class.md)를 참조하십시오.  
  
 `GenerateDeploymentManifest` 작업을 사용하는 방법에 대한 자세한 내용은 [GenerateApplicationManifest Task](../msbuild/generateapplicationmanifest-task.md)을 참조하십시오.  
  
 종속 항목과 파일에 대한 입력을 항목 메타데이터로 더 세밀하게 설정하여 각 항목에 대한 추가 배포 상태를 지정할 수 있습니다.  
  
## 항목 메타데이터  
  
|메타데이터 이름|설명|  
|--------------|--------|  
|`DependencyType`|종속 항목이 응용 프로그램이나 사전 요구 사항과 함께 게시 및 설치되는지 나타냅니다.  이 메타데이터는 모든 종속 항목에 유효하지만 파일에는 사용되지 않습니다.  이 메타데이터에 대해 사용할 수 있는 값은 다음과 같습니다.<br /><br /> -   `Install`<br />-   `Prerequisite`<br /><br /> 기본값은 Install입니다.|  
|`AssemblyType`|종속 항목이 관리되는 어셈블리인지 네이티브 어셈블리인지 나타냅니다.  이 메타데이터는 모든 종속 항목에 유효하지만 파일에는 사용되지 않습니다.  이 메타데이터에 대해 사용할 수 있는 값은 다음과 같습니다.<br /><br /> -   `Managed`<br />-   `Native`<br />-   `Unspecified`<br /><br /> 기본값은 매니페스트 생성기에서 어셈블리 형식을 자동으로 결정하도록 지시하는 `Unspecified`입니다.|  
|`Group`|요청 시 추가 파일을 다운로드할 그룹을 나타냅니다.  그룹 이름은 응용 프로그램에서 정의되며 임의의 문자열일 수 있습니다.  빈 문자열을 사용하면 파일이 다운로드 그룹의 일부가 아님을 나타냅니다. 이는 기본값입니다.  그룹에 없는 파일은 초기 응용 프로그램 다운로드의 일부입니다.  그룹에 있는 파일은 응용 프로그램에서 <xref:System.Deployment.Application>를 사용하여 명시적으로 요청하는 경우에만 다운로드됩니다.<br /><br /> 이 메타데이터는 `IsDataFile`이 `false`인 모든 파일과 `DependencyType`이 `Install`인 모든 종속 항목에 대해 유효합니다.|  
|`TargetPath`|생성된 매니페스트에서 경로가 정의되는 방식을 지정합니다.  이 특성은 모든 파일에 유효합니다.  이 특성을 지정하지 않으면 항목 사양이 사용됩니다.  이 특성은 `DependencyType` 값이 `Install`인 모든 파일과 종속 항목에 유효합니다.|  
|`IsDataFile`|파일이 데이터 파일인지 여부를 나타내는 `Boolean` 메타데이터 값입니다.  데이터 파일은 응용 프로그램을 업데이트할 때 마이그레이션되는 특수 파일입니다.  이 메타데이터는 파일에만 유효합니다.  기본값은 `False`입니다.|  
  
## 예제  
 이 예제에서는 `GenerateApplicationManifest` 작업을 사용하여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트를 생성하고 `GenerateDeploymentManifest` 작업을 사용하여 어셈블리가 하나인 응용 프로그램에 대한 배포 매니페스트를 생성합니다.  그런 다음 `SignFile` 작업을 사용하여 매니페스트에 서명합니다.  
  
 이 예제에서는 프로그램 하나에 대해 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 매니페스트를 생성하는 매우 간단한 매니페스트 생성 시나리오를 보여 줍니다.  기본 이름과 ID는 매니페스트의 어셈블리에서 유추됩니다.  
  
> [!NOTE]
>  아래 예제에서는 매니페스트 생성 과정을 중점적으로 살펴볼 수 있도록 모든 응용 프로그램 이진 파일이 미리 빌드되어 있습니다.  이 예제에서는 완전히 작동하는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 생성합니다.  
  
> [!NOTE]
>  이 예제의 `SignFile` 작업에 사용되는 `Thumbprint` 속성에 대한 자세한 내용은 [SignFile Task](../msbuild/signfile-task.md)을 참조하십시오.  
  
```  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <EntryPoint Include="SimpleWinApp.exe" />  
    </ItemGroup>  
  
    <PropertyGroup>  
        <Thumbprint>  
             <!-- Insert generated thumbprint here -->  
        </Thumbprint>  
    </PropertyGroup>  
  
    <Target Name="Build">  
  
        <GenerateApplicationManifest  
            EntryPoint="@(EntryPoint)">  
            <Output  
                ItemName="ApplicationManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateApplicationManifest>  
  
        <GenerateDeploymentManifest  
            EntryPoint="@(ApplicationManifest)">  
            <Output  
                ItemName="DeployManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateDeploymentManifest>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(ApplicationManifest)"/>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(DeployManifest)"/>  
  
    </Target>  
</Project>  
```  
  
## 예제  
 이 예제에서는 `GenerateApplicationManifest` 및 `GenerateDeploymentManifest` 작업을 사용하여 어셈블리가 하나인 응용 프로그램에 대한 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 및 배포 매니페스트를 생성하고 매니페스트의 이름과 ID를 지정합니다.  
  
 이 예제는 이전 예제와 비슷하지만 매니페스트의 이름과 ID를 명시적으로 지정한다는 점에서 차이가 있습니다.  또한 이 예제는 설치되는 응용 프로그램이 아니라 온라인 응용 프로그램으로 구성되어 있습니다.  
  
> [!NOTE]
>  아래 예제에서는 매니페스트 생성 과정을 중점적으로 살펴볼 수 있도록 모든 응용 프로그램 이진 파일이 미리 빌드되어 있습니다.  이 예제에서는 완전히 작동하는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 생성합니다.  
  
> [!NOTE]
>  이 예제의 `SignFile` 작업에 사용되는 `Thumbprint` 속성에 대한 자세한 내용은 [SignFile Task](../msbuild/signfile-task.md)을 참조하십시오.  
  
```  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <EntryPoint Include="SimpleWinApp.exe" />  
    </ItemGroup>  
  
    <PropertyGroup>  
        <Thumbprint>  
             <!-- Insert generated thumbprint here -->  
        </Thumbprint>  
    </PropertyGroup>  
  
    <Target Name="Build">  
  
        <GenerateApplicationManifest  
            AssemblyName="SimpleWinApp.exe"  
            AssemblyVersion="1.0.0.0"  
            EntryPoint="@(EntryPoint)"  
            OutputManifest="SimpleWinApp.exe.manifest">  
            <Output  
                ItemName="ApplicationManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateApplicationManifest>  
  
        <GenerateDeploymentManifest  
                AssemblyName="SimpleWinApp.application"  
                AssemblyVersion="1.0.0.0"  
                EntryPoint="@(ApplicationManifest)"  
                Install="false"  
                OutputManifest="SimpleWinApp.application">  
                <Output  
                    ItemName="DeployManifest"  
                    TaskParameter="OutputManifest"/>  
        </GenerateDeploymentManifest>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(ApplicationManifest)"/>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(DeployManifest)"/>  
  
    </Target>  
</Project>  
```  
  
## 예제  
 이 예제에서는 `GenerateApplicationManifest` 및 `GenerateDeploymentManifest` 작업을 사용하여 파일과 어셈블리가 여러 개인 응용 프로그램에 대한 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 및 배포 매니페스트를 생성합니다.  
  
> [!NOTE]
>  아래 예제에서는 매니페스트 생성 과정을 중점적으로 살펴볼 수 있도록 모든 응용 프로그램 이진 파일이 미리 빌드되어 있습니다.  이 예제에서는 완전히 작동하는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 생성합니다.  
  
> [!NOTE]
>  이 예제의 `SignFile` 작업에 사용되는 `Thumbprint` 속성에 대한 자세한 내용은 [SignFile Task](../msbuild/signfile-task.md)을 참조하십시오.  
  
```  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <EntryPoint Include="SimpleWinApp.exe" />  
    </ItemGroup>  
  
    <PropertyGroup>  
        <Thumbprint>  
             <!-- Insert generated thumbprint here -->  
        </Thumbprint>  
        <DeployUrl>  
            <!-- Insert the deployment URL here -->  
        </DeployUrl>  
        <SupportUrl>  
            <!-- Insert the support URL here -->  
        </SupportUrl>  
    </PropertyGroup>  
  
    <Target Name="Build">  
  
    <ItemGroup>  
        <EntryPoint Include="SimpleWinApp.exe"/>  
        <Dependency Include="ClassLibrary1.dll">  
            <AssemblyType>Managed</AssemblyType>  
            <DependencyType>Install</DependencyType>  
        </Dependency>  
        <Dependency Include="ClassLibrary2.dll">  
            <AssemblyType>Managed</AssemblyType>  
            <DependencyType>Install</DependencyType>  
            <Group>Secondary</Group>  
        </Dependency>  
        <Dependency Include="MyAddIn1.dll">  
            <AssemblyType>Managed</AssemblyType>  
            <DependencyType>Install</DependencyType>  
            <TargetPath>Addins\MyAddIn1.dll</TargetPath>  
        </Dependency>  
        <Dependency Include="ClassLibrary3.dll">  
            <AssemblyType>Managed</AssemblyType>  
            <DependencyType>Prerequisite</DependencyType>  
        </Dependency>  
  
        <File Include="Text1.txt">  
            <TargetPath>Text\Text1.txt</TargetPath>  
            <Group>Text</Group>  
        </File>  
        <File Include="DataFile1.xml ">  
            <TargetPath>Data\DataFile1.xml</TargetPath>  
            <IsDataFile>true</IsDataFile>  
        </File>  
  
        <IconFile Include="Heart.ico"/>  
        <ConfigFile Include="app.config">  
            <TargetPath>SimpleWinApp.exe.config</TargetPath>  
        </ConfigFile>  
        <BaseManifest Include="app.manifest"/>  
    </ItemGroup>  
  
    <Target Name="Build">  
  
        <GenerateApplicationManifest  
            AssemblyName="SimpleWinApp.exe"  
            AssemblyVersion="1.0.0.0"  
            ConfigFile="@(ConfigFile)"  
            Dependencies="@(Dependency)"  
            Description="TestApp"  
            EntryPoint="@(EntryPoint)"  
            Files="@(File)"  
            IconFile="@(IconFile)"  
            InputManifest="@(BaseManifest)"  
            OutputManifest="SimpleWinApp.exe.manifest">  
            <Output  
                ItemName="ApplicationManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateApplicationManifest>  
  
        <GenerateDeploymentManifest  
            AssemblyName="SimpleWinApp.application"  
            AssemblyVersion="1.0.0.0"  
            DeploymentUrl="$(DeployToUrl)"  
            Description="TestDeploy"  
            EntryPoint="@(ApplicationManifest)"  
            Install="true"  
            OutputManifest="SimpleWinApp.application"  
            Product="SimpleWinApp"  
            Publisher="Microsoft"  
            SupportUrl="$(SupportUrl)"  
            UpdateEnabled="true"  
            UpdateInterval="3"  
            UpdateMode="Background"  
            UpdateUnit="weeks">  
            <Output  
                ItemName="DeployManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateDeploymentManifest>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(ApplicationManifest)"/>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(DeployManifest)"/>  
  
    </Target>  
</Project>  
```  
  
## 예제  
 이 예제에서는 `GenerateApplicationManifest` 작업을 사용하여 Test.exe 응용 프로그램에 대한 네이티브 매니페스트를 생성합니다. 이때 네이티브 구성 요소 Alpha.dll 및 격리된 COM 구성 요소 Bravo.dll을 참조합니다.  
  
 이 예제에서는 Test.exe.manifest를 생성하여 배포 가능한 응용 프로그램 XCOPY에 등록이 필요 없는 COM을 활용합니다.  
  
> [!NOTE]
>  아래 예제에서는 매니페스트 생성 과정을 중점적으로 살펴볼 수 있도록 모든 응용 프로그램 이진 파일이 미리 빌드되어 있습니다.  이 예제에서는 완전히 작동하는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 생성합니다.  
  
```  
<Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <File Include="Test.exe" />  
        <Dependency Include="Alpha.dll">  
            <AssemblyType>Native</AssemblyType>  
            <DependencyType>Install</DependencyType>  
        </Dependency>  
        <ComComponent Include="Bravo.dll" />  
    </ItemGroup>  
  
    <Target Name="Build">  
        <GenerateApplicationManifest  
            AssemblyName="Test.exe"  
            AssemblyVersion="1.0.0.0"  
            Dependencies="@(Dependency)"  
            Files="@(File)"  
            IsolatedComReferences="@(ComComponent)"  
            ManifestType="Native">  
            <Output  
                ItemName="ApplicationManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateApplicationManifest>  
  
    </Target>  
</Project>  
```  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [GenerateDeploymentManifest Task](../msbuild/generatedeploymentmanifest-task.md)   
 [SignFile Task](../msbuild/signfile-task.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)