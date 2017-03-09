---
title: "MarkupCompilePass1 Task | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "converting XAML to binary format [WPF MSBuild]"
  - "MarkupCompilePass1 task [WPF MSBuild], parameters"
  - "converting XAML projects to compiled binary format [WPF MSBuild]"
  - "MarkupCompilePass1 task [WPF MSBuild], converting XAML to binary format"
ms.assetid: 693d6945-fd6f-4698-8f64-9dfcb71052d3
caps.latest.revision: 8
caps.handback.revision: 8
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# MarkupCompilePass1 Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

<xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> 작업은 지역화할 수 없는 [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] 프로젝트 파일을 컴파일된 이진 형식으로 변환합니다.  
  
## 작업 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`AllGeneratedFiles`|선택적 **ITaskItem\[\]** 출력 매개 변수입니다.<br /><br /> <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> 작업에서 생성되는 전체 파일 목록을 포함합니다.|  
|`AlwaysCompileMarkupFilesInSeparateDomain`|선택적 **Boolean** 매개 변수입니다.<br /><br /> 작업을 별도의 <xref:System.AppDomain>에서 실행할 것인지 여부를 지정합니다.  이 매개 변수에서 **false**를 반환하면 작업이 같은 <xref:System.AppDomain>에서 [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)]로 실행되며 이 경우 실행 속도가 더 빠릅니다.  매개 변수에서 **true**를 반환하면 작업이 [!INCLUDE[TLA2#tla_msbuild](../msbuild/includes/tla2sharptla_msbuild_md.md)]에서 격리된 두 번째 <xref:System.AppDomain>에서 실행되며 이 경우 실행 속도가 더 느립니다.|  
|`ApplicationMarkup`|선택적 **ITaskItem\[\]** 매개 변수입니다.<br /><br /> 응용 프로그램 정의 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일의 이름을 지정합니다.|  
|`AssembliesGeneratedDuringBuild`|선택적 **String\[\]** 매개 변수입니다.<br /><br /> 빌드 프로세스 동안 변경되는 어셈블리에 대한 참조를 지정합니다.  예를 들어 [!INCLUDE[TLA#tla_visualstu2005](../msbuild/includes/tlasharptla_visualstu2005_md.md)] 솔루션에는 다른 프로젝트의 컴파일된 출력을 참조하는 하나의 프로젝트가 포함될 수 있습니다.  이 경우 두 번째 프로젝트의 컴파일된 출력이 **AssembliesGeneratedDuringBuild** 매개 변수에 추가될 수 있습니다.<br /><br /> 참고: **AssembliesGeneratedDuringBuild** 매개 변수는 빌드 솔루션에 의해 생성되는 전체 어셈블리 집합에 대한 참조를 포함해야 합니다.|  
|`AssemblyName`|필수 **string** 매개 변수입니다.<br /><br /> 프로젝트에 대해 생성되는 어셈블리의 약식 이름을 지정합니다.  예를 들어 프로젝트에서 이름이 **WinExeAssembly.exe**인 [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)] 실행 파일을 생성하는 경우 **AssemblyName** 매개 변수의 값은 **WinExeAssembly**입니다.|  
|`AssemblyPublicKeyToken`|선택적 **String** 매개 변수입니다.<br /><br /> 어셈블리의 공개 키 토큰을 지정합니다.|  
|`AssemblyVersion`|선택적 **String** 매개 변수입니다.<br /><br /> 어셈블리의 버전 번호를 지정합니다.|  
|`ContentFiles`|선택적 **ITaskItem\[\]** 매개 변수입니다.<br /><br /> 느슨한 콘텐츠 파일의 목록을 지정합니다.|  
|`DefineConstants`|선택적 **String** 매개 변수입니다.<br /><br /> 대상 어셈블리 생성에 영향을 주는 **DefineConstants**의 현재 값이 유지됨을 지정합니다.  이 매개 변수가 변경되면 대상 어셈블리의 공용 API가 변경되고 로컬 형식을 참조하는 [!INCLUDE[TLA2#tla_titlexaml](../msbuild/includes/tla2sharptla_titlexaml_md.md)] 파일의 컴파일에 영향을 미칠 수 있습니다.|  
|`ExtraBuildControlFiles`|선택적 **ITaskItem\[\]** 매개 변수입니다.<br /><br /> <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> 작업이 재실행될 때 재빌드를 트리거하는지 여부를 제어하는 파일의 목록을 지정합니다. 이 파일 중 하나가 변경되면 재빌드가 트리거됩니다.|  
|`GeneratedBamlFiles`|선택적 **ITaskItem\[\]** 출력 매개 변수입니다.<br /><br /> 생성되는 파일의 목록을 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 이진 형식으로 포함합니다.|  
|`GeneratedCodeFiles`|선택적 **ITaskItem\[\]** 출력 매개 변수입니다.<br /><br /> 생성되는 관리 코드 파일의 목록을 포함합니다.|  
|`GeneratedLocalizationFiles`|선택적 **ITaskItem\[\]** 출력 매개 변수입니다.<br /><br /> 지역화 가능한 각 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일에 대해 생성된 지역화 파일의 목록을 포함합니다.|  
|`HostInBrowser`|선택적 **String** 매개 변수입니다.<br /><br /> 생성되는 어셈블리가 [!INCLUDE[TLA#tla_xbap](../msbuild/includes/tlasharptla_xbap_md.md)]인지 여부를 지정합니다.  유효한 옵션은 **true** 및 **false**입니다.  **true**이면 브라우저 호스팅을 지원하기 위해 코드가 생성됩니다.|  
|`KnownReferencePaths`|선택적 **String\[\]** 매개 변수입니다.<br /><br /> 빌드 프로세스 동안 변경되지 않는 어셈블리에 대한 참조를 지정합니다.  [!INCLUDE[TLA#tla_gac](../msbuild/includes/tlasharptla_gac_md.md)], [!INCLUDE[TLA#tla_netframewk](../misc/includes/tlasharptla_netframewk_md.md)] 설치 디렉터리 등에 있는 어셈블리를 포함합니다.|  
|`Language`|필수 **String** 매개 변수입니다.<br /><br /> 컴파일러가 지원하는 관리되는 언어를 지정합니다.  유효한 옵션은  **C\#**,  **VB**,  **JScript**, 및  **C\+\+**.|  
|`LanguageSourceExtension`|선택적 **String** 매개 변수입니다.<br /><br /> 생성되는 관리 코드 파일의 확장명에 추가되는 확장명을 지정합니다.<br /><br /> `<Filename>.g<LanguageSourceExtension>`<br /><br /> **LanguageSourceExtension** 매개 변수에 특정 값을 설정하지 않은 경우 언어의 기본 소스 파일 이름 확장명이 사용됩니다. 예를 들어 [!INCLUDE[TLA#tla_visualb](../msbuild/includes/tlasharptla_visualb_md.md)]의 경우에는 **.vb**가 사용되고, [!INCLUDE[TLA#tla_cshrp](../msbuild/includes/tlasharptla_cshrp_md.md)]의 경우에는 **.csharp**이 사용됩니다.|  
|`LocalizationDirectivesToLocFile`|선택적 **String** 매개 변수입니다.<br /><br /> 각 소스 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일에 대한 지역화 정보를 생성하는 방법을 지정합니다.  유효한 옵션은 **None**, **CommentsOnly** 및 **All**입니다.|  
|`OutputPath`|필수 **String** 매개 변수입니다.<br /><br /> 생성되는 관리 코드 파일과 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 이진 형식 파일이 생성되는 디렉터리를 지정합니다.|  
|`OutputType`|필수 **String** 매개 변수입니다.<br /><br /> 프로젝트에 의해 생성되는 어셈블리의 형식을 지정합니다.  유효한 옵션은 **winexe**, **exe**, **library** 및 **netmodule**입니다.|  
|`PageMarkup`|선택적 **ITaskItem\[\]** 매개 변수입니다.<br /><br /> 처리할 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일의 목록을 지정합니다.|  
|`References`|선택적 **ITaskItem\[\]** 매개 변수입니다.<br /><br /> [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일에 사용되는 형식이 포함된 어셈블리에 대한 파일 참조의 목록을 지정합니다.|  
|`RequirePass2ForMainAssembly`|선택적 **Boolean** 출력 매개 변수입니다.<br /><br /> 기본 어셈블리에 포함되는 로컬 형식을 참조하는 지역화할 수 없는 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일이 프로젝트에 포함되는지 여부를 지정합니다.|  
|`RequirePass2ForSatelliteAssembly`|선택적 **Boolean** 출력 매개 변수입니다.<br /><br /> 기본 어셈블리에 포함되는 로컬 형식을 참조하는 지역화할 수 있는 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일이 프로젝트에 포함되는지 여부를 지정합니다.|  
|`RootNamespace`|선택적 **String** 매개 변수입니다.<br /><br /> 프로젝트 내부에 있는 클래스에 대한 루트 네임스페이스를 지정합니다.  **RootNamespace**는 해당 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일에 `x:Class` 특성이 포함되어 있지 않을 경우, 생성되는 관리 코드 파일의 기본 네임스페이스로도 사용됩니다.|  
|`SourceCodeFiles`|선택적 **ITaskItem\[\]** 매개 변수입니다.<br /><br /> 현재 프로젝트의 코드 파일 목록을 지정합니다.  생성되는 언어 특정 관리 코드 파일은 목록에 포함되지 않습니다.|  
|`UICulture`|선택적 **String** 매개 변수입니다.<br /><br /> 생성되는 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 이진 형식 파일이 포함되는 UI 문화권의 위성 어셈블리를 지정합니다.  **UICulture**를 설정하지 않은 경우 생성되는 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 이진 형식 파일은 기본 어셈블리에 포함됩니다.|  
|`XAMLDebuggingInformation`|선택적 **Boolean** 매개 변수입니다.<br /><br /> **true**인 경우 디버깅에 도움이 되도록 진단 정보가 생성되어 컴파일된 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)]에 포함됩니다.|  
  
## 설명  
 <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> 작업은 일반적으로 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)]을 이진 형식으로 컴파일하고 코드 파일을 생성합니다.  [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일에 같은 프로젝트에서 정의된 형식에 대한 참조가 포함되어 있는 경우 **MarkupCompilePass1**은 이진 형식으로의 컴파일을 두 번째 태그 컴파일 패스\(**MarkupCompilePass2**\)로 연기합니다.  이러한 파일은 참조된 로컬 정의 형식이 컴파일될 때까지 기다려야 하므로 컴파일이 연기되어야 합니다.  하지만 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일에 `x:Class` 특성이 있는 경우에는 <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1>에서 이를 위한 언어 특정 코드 파일을 생성합니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일은 `x:Uid` 특성을 사용하는 요소를 포함하는 경우 지역화가 가능합니다.  
  
```  
<Page x:Class="WPFMSBuildSample.Page1"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    x:Uid="Page1Uid"  
    >  
  ...  
</Page>  
```  
  
 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일은 현재 프로젝트의 네임스페이스를 참조하기 위해 `clr-namespace` 값을 사용하는 [!INCLUDE[TLA#tla_xml](../msbuild/includes/tlasharptla_xml_md.md)] 네임스페이스를 선언할 때, 로컬로 정의된 형식을 참조합니다.  
  
```  
<Page x:Class="WPFMSBuildSample.Page1"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:localNamespace="clr-namespace:WPFMSBuildSample"  
    >  
    <Grid>  
      <Grid.Resources>  
        <localNameSpace:LocalType x:Key="localType" />  
      </Grid.Resources>  
      ...  
    </Grid>  
</Page>  
```  
  
 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일이 지역화 가능하거나 로컬로 정의된 형식을 참조하는 경우에는 두 번째 태그 컴파일 패스가 필요합니다. 이 경우 [GenerateTemporaryTargetAssembly](../msbuild/generatetemporarytargetassembly-task.md)를 실행한 다음 [MarkupCompilePass2](../msbuild/markupcompilepass2-task.md)를 실행해야 합니다.  
  
## 예제  
 다음 예제에서는 세 개의 `Page` [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일을 이진 형식 파일로 변환하는 방법을 보여 줍니다.  `Page1`에는 `Class1` 형식에 대한 참조가 포함되어 있습니다. 이 형식은 프로젝트의 루트 네임스페이스에 있으므로 이 태그 컴파일 패스에서 이진 형식 파일로 변환되지 않습니다.  대신 [GenerateTemporaryTargetAssembly](../msbuild/generatetemporarytargetassembly-task.md)이 실행된 다음 [MarkupCompilePass2](../msbuild/markupcompilepass2-task.md)이 실행됩니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.MarkupCompilePass1"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="MarkupCompilePass1Task">  
    <MarkupCompilePass1   
      AssemblyName="WPFMSBuildSample"  
      Language="C#"  
      OutputType="WinExe"  
      OutputPath="obj\Debug\"  
      ApplicationMarkup="App.xaml"  
      PageMarkup="Page1.xaml;Page2.xaml;Page3.xaml"  
      SourceCodeFiles="Class1.cs"  
      References="c:\windows\Microsoft.net\Framework\v2.0.50727\System.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationCore.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationFramework.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\WindowsBase.dll" />  
  </Target>  
</Project>  
```  
  
## 참고 항목  
 [WPF MSBuild Reference](../msbuild/wpf-msbuild-reference.md)   
 [Task Reference](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild Reference](../msbuild/msbuild-reference.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [WPF 응용 프로그램 만들기\(WPF\)](../Topic/Building%20a%20WPF%20Application%20\(WPF\).md)   
 [WPF XAML 브라우저 응용 프로그램 개요](../Topic/WPF%20XAML%20Browser%20Applications%20Overview.md)