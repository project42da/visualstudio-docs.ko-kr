---
title: "GenerateTemporaryTargetAssembly Task | Microsoft Docs"
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
  - "build process [WPF MSBuild], XAML page refers to a locally declared type"
  - "GenerateTemporaryTargetAssembly task [WPF MSBuild]"
  - "GenerateTemporaryTargetAssembly task [WPF MSBuild], parameters"
  - "creating an assembly [WPF MSBuild], XAML page refers to a locally declared type"
ms.assetid: 92b6539c-6897-45e0-8989-0c234bbfe782
caps.latest.revision: 7
caps.handback.revision: 7
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# GenerateTemporaryTargetAssembly Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

<xref:Microsoft.Build.Tasks.Windows.GenerateTemporaryTargetAssembly> 작업은 프로젝트에서 적어도 하나의 [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] 페이지가 해당 프로젝트에 로컬로 선언된 형식을 참조하는 경우 어셈블리를 생성합니다.  빌드 프로세스가 완료되거나 실패하면 생성된 어셈블리가 제거됩니다.  
  
## 작업 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`AssemblyName`|필수 **String** 매개 변수입니다.<br /><br /> 프로젝트에 대해 생성되는 어셈블리의 약식 이름을 지정하며 임시로 생성되는 대상 어셈블리의 이름이기도 합니다.  예를 들어 프로젝트에서 이름이 **WinExeAssembly.exe**인 [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)] 실행 파일을 생성하는 경우 **AssemblyName** 매개 변수의 값은 **WinExeAssembly**입니다.|  
|`CompileTargetName`|필수 **String** 매개 변수입니다.<br /><br /> 소스 코드 파일에서 어셈블리를 생성하는 데 사용되는 [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)] 대상의 이름을 지정합니다.  **CompileTargetName**의 일반적인 값은 **CoreCompile**입니다.|  
|`CompileTypeName`|필수 **String** 매개 변수입니다.<br /><br /> **CompileTargetName** 매개 변수로 지정된 대상이 수행하는 컴파일 유형을 지정합니다.  **CoreCompile** 대상의 경우 이 값은 **Compile**입니다.|  
|`CurrentProject`|필수 **String** 매개 변수입니다.<br /><br /> 임시 대상 어셈블리가 필요한 [!INCLUDE[TLA2#tla_msbuild](../msbuild/includes/tla2sharptla_msbuild_md.md)] 프로젝트 파일의 전체 경로를 지정합니다.|  
|`GeneratedCodeFiles`|선택적 **ITaskItem\[\]** 매개 변수입니다.<br /><br /> [MarkupCompilePass1](../msbuild/markupcompilepass1-task.md)으로 생성된 언어별 관리 코드 파일의 목록을 지정합니다.|  
|`IntermediateOutputPath`|필수 **String** 매개 변수입니다.<br /><br /> 임시 대상 어셈블리가 생성되는 디렉터리를 지정합니다.|  
|`MSBuildBinPath`|필수 **String** 매개 변수입니다.<br /><br /> 임시 대상 어셈블리를 컴파일하는 데 필요한 **MSBuild.exe**의 위치를 지정합니다.|  
|`ReferencePath`|선택적 **ITaskItem\[\]** 매개 변수입니다.<br /><br /> 임시 대상 어셈블리로 컴파일되는 형식이 참조하는 어셈블리의 경로 및 파일 이름별 목록을 지정합니다.|  
|`ReferencePathTypeName`|필수 **String** 매개 변수입니다.<br /><br /> 어셈블리 참조\(**ReferencePath**\)의 목록을 지정하는 컴파일 대상\(**CompileTargetName**\) 매개 변수에 사용되는 매개 변수를 지정합니다.  적절한 값은 **ReferencePath**입니다.|  
  
## 설명  
 [MarkupCompilePass1](../msbuild/markupcompilepass1-task.md)에서 실행하는 첫 번째 태그 컴파일 패스에서는 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일을 이진 형식으로 컴파일합니다.  따라서 컴파일러에는 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일에서 사용하는 형식을 포함하는 참조된 어셈블리의 목록이 필요합니다.  하지만 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일이 같은 프로젝트에서 정의된 형식을 사용하는 경우에는 프로젝트가 빌드될 때까지 프로젝트에 대한 해당 어셈블리가 생성되지 않습니다.  따라서 첫 번째 태그 컴파일 패스 동안에는 어셈블리 참조를 제공할 수 없습니다.  
  
 대신 **MarkupCompilePass1**은 같은 프로젝트의 형식에 대한 참조가 포함된 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일의 변환을 [MarkupCompilePass2](../msbuild/markupcompilepass2-task.md)에서 실행하는 두 번째 태그 컴파일 패스로 연기합니다.  **MarkupCompilePass2**가 실행되기 전에 임시 어셈블리가 생성됩니다.  이 어셈블리에는 태그 컴파일 패스가 연기된 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일에서 사용하는 형식이 포함됩니다.  연기된 컴파일 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 파일을 이진 형식으로 변환할 수 있도록 **MarkupCompilePass2**가 실행될 때 앞서 생성된 어셈블리에 대한 참조가 이 태그 컴파일 패스에 제공됩니다.  
  
## 예제  
 다음 예제에서는 `Page1.xaml`에 같은 프로젝트에 있는 형식에 대한 참조가 포함되어 있기 때문에 임시 어셈블리를 생성합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask  
    TaskName="Microsoft.Build.Tasks.Windows.GenerateTemporaryTargetAssembly"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="GenerateTemporaryTargetAssemblyTask">  
    <GenerateTemporaryTargetAssembly  
      AssemblyName="WPFMSBuildSample"  
      CompileTargetName="CoreCompile"  
      CompileTypeName="Compile"  
      CurrentProject="FullBuild.proj"  
      GeneratedCodeFiles="obj\debug\app.g.cs;obj\debug\Page1.g.cs;obj\debug\Page2.g.cs"  
      ReferencePath="c:\windows\Microsoft.net\Framework\v2.0.50727\System.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationCore.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationFramework.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\WindowsBase.dll"  
      IntermediateOutputPath=".\obj\debug\"  
      MSBuildBinPath="$(MSBuildBinPath)"  
      ReferencePathTypeName="ReferencePath"/>  
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