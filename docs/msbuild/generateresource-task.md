---
title: "GenerateResource Task | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#GenerateResource"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MSBuild, GenerateResource task"
  - "GenerateResource task [MSBuild]"
ms.assetid: c0aff32f-f2cc-46f6-9c3e-a5c9f8f912b1
caps.latest.revision: 15
caps.handback.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# GenerateResource Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

.txt 파일과 XML 기반 리소스 형식의 .resx 파일을 런타임 이진 실행 파일에 포함시키거나 위성 어셈블리로 컴파일할 수 있는 공용 언어 런타임 이진 .resources 파일로 변환하거나 그 반대로 변환합니다.  이 작업은 일반적으로 .txt 또는 .resx 파일을 .resource 파일로 변환하는 데 사용됩니다.  `GenerateResource` 작업은 [resgen.exe](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md)와 비슷한 기능을 수행합니다.  
  
## 매개 변수  
 다음 표에서는 `GenerateResource` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`AdditionalInputs`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]`  매개 변수입니다.<br /><br /> 이 작업이 수행한 종속성 검사에 대한 추가 입력을 포함합니다.  예를 들어 프로젝트 및 대상 파일이 업데이트될 때 모든 리소스가 다시 생성되도록 하려면 일반적으로 프로젝트 및 대상 파일을 입력해야 합니다.|  
|`EnvironmentVariables`|선택적 `String[]` 매개 변수입니다.<br /><br /> 선택적으로 재정의하는 일반 환경 블록과 함께, 생성된 resgen.exe에 전달되어야 하는 환경 변수의 이름\-값 쌍 배열을 가져오거나 지정합니다.|  
|`ExcludedInputPaths`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]`  매개 변수입니다.<br /><br /> 최신 검사를 수행하는 동안 추적된 입력이 무시될 경로를 지정하는 항목 배열을 지정합니다.|  
|`ExecuteAsTool`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 적절한 대상 프레임워크의 tlbimp.exe 및 aximp.exe가 out\-of\-proc로 실행되어 필요한 래퍼 어셈블리를 생성합니다.  이 매개 변수는 `ResolveComReferences`의 멀티 타기팅을 허용합니다.|  
|`FilesWritten`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 디스크에 기록된 모든 파일의 이름이 들어 있습니다.  캐시 파일이 있는 경우 이 파일도 여기에 포함됩니다.  이 매개 변수는 Clean을 구현하는 데 유용합니다.|  
|`MinimalRebuildFromTracking`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 추적된 증분 빌드의 사용 여부를 지정하는 스위치를 가져오거나 설정합니다.  `true`이면 증분 빌드가 설정되고, 그렇지 않으면 다시 빌드가 강제로 적용됩니다.|  
|`NeverLockTypeAssemblies`|선택적 `Boolean` 매개 변수입니다.<br /><br /> .resources 파일 같이 생성된 파일의 이름을 지정합니다.  이름을 지정하지 않으면 일치하는 입력 파일의 이름이 사용되고 작성된 .resources 파일이 입력 파일과 동일한 디렉터리에 배치됩니다.|  
|`OutputResources`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> .resources 파일 같이 생성된 파일의 이름을 지정합니다.  이름을 지정하지 않으면 일치하는 입력 파일의 이름이 사용되고 작성된 .resources 파일이 입력 파일과 동일한 디렉터리에 배치됩니다.|  
|`PublicClass`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 공용 클래스로 강력한 형식의 리소스 클래스를 만듭니다.|  
|`References`|선택적 `String[]` 매개 변수입니다.<br /><br /> .resx 파일에서 로드할 형식에 대한 참조입니다.  Resx 파일 데이터 요소에는 .NET 형식이 있을 수 있습니다.  .resx 파일을 읽을 때는 이를 확인해야 합니다.  일반적으로 표준 형식 로드 규칙을 사용하여 확인할 수 있습니다.  `References`에 어셈블리를 제공하면 이 어셈블리가 우선 적용됩니다.<br /><br /> 강력한 형식의 리소스에는 이 매개 변수가 필요하지 않습니다.|  
|`SdkToolsPath`|선택적 `String` 매개 변수입니다.<br /><br /> resgen.exe와 같이 SDK 도구에 대한 경로를 지정합니다.|  
|`Sources`|필수적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 변환할 항목을 지정합니다.  이 매개 변수에 전달되는 항목의 확장명은 다음 중 하나여야 합니다.<br /><br /> -   `.txt`: 변환할 텍스트 파일의 확장명을 지정합니다.  텍스트 파일에는 문자열 리소스만 포함될 수 있습니다.<br />-   `.resx`: 변환할 XML 기반 리소스 파일의 확장명을 지정합니다.<br />-   `.restext`: .txt와 동일한 형식을 지정합니다.  이와 같이 확장명을 다르게 사용하면 리소스가 포함되어 있는 소스 파일과 빌드 프로세스의 다른 소스 파일을 명확하게 구분할 수 있습니다.<br />-   `.resources`: 변환할 리소스 파일의 확장명을 지정합니다.|  
|`StateFile`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> .resx 입력 파일에서 링크의 종속성 검사 속도를 향상시키기 위해 사용되는 선택적 캐시 파일의 경로를 지정합니다.|  
|`StronglyTypedClassName`|선택적 `String` 매개 변수입니다.<br /><br /> 강력한 형식의 리소스 클래스에 대한 클래스 이름을 지정합니다.  이 매개 변수를 지정하지 않으면 리소스 파일의 기본 이름이 사용됩니다.|  
|`StronglyTypedFilename`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> 소스 파일에 대한 파일 이름을 지정합니다.  이 매개 변수를 지정하지 않으면 클래스의 이름이 기본 파일 이름으로 사용됩니다. 확장명은 언어에 따라 달라집니다.  예를 들면 `MyClass.cs` 형식으로 코드를 작성해야 합니다.|  
|`StronglyTypedLanguage`|선택적 `String` 매개 변수입니다.<br /><br /> 강력한 형식의 리소스에 대한 클래스 소스를 생성할 때 사용되는 언어를 지정합니다.  이 매개 변수는 CodeDomProvider에 사용되는 언어 중 하나와 정확하게 일치해야 합니다.  예를 들어 `VB` 또는 `C#`를 지정할 수 있습니다.<br /><br /> 이 매개 변수에 값을 전달하면 작업에서 강력한 형식의 리소스가 생성됩니다.|  
|`StronglyTypedManifestPrefix`|선택적 `String` 매개 변수입니다.<br /><br /> 강력한 형식의 리소스에 대해 생성된 클래스 소스에 사용할 리소스 네임스페이스 또는 매니페스트 접두사를 지정합니다.|  
|`StronglyTypedNamespace`|선택적 `String` 매개 변수입니다.<br /><br /> 강력한 형식의 리소스에 대해 생성된 클래스 소스에 사용할 네임스페이스를 지정합니다.  이 매개 변수를 지정하지 않으면 강력한 형식의 리소스가 모두 전역 네임스페이스에 배치됩니다.|  
|`TLogReadFiles`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 읽기 전용 매개 변수입니다.<br /><br /> 읽기 추적 로그를 나타내는 항목 배열을 가져옵니다.|  
|`TLogWriteFiles`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 읽기 전용 매개 변수입니다.<br /><br /> 쓰기 추적 로그를 나타내는 항목 배열을 가져옵니다.|  
|`ToolArchitecture`|선택적 [String](assetId:///String?qualifyHint=False&autoUpgrade=True) 매개 변수입니다.<br /><br /> ResGen.exe를 생성하는 데 Tracker.exe를 사용할 필요가 있는지를 판단하는 데 사용합니다.<br /><br /> <xref:Microsoft.Build.Utilities.ExecutableType> 열거형의 멤버에 대해 구문 분석할 수 있어야 합니다.  `String.Empty`인 경우 경험적 접근을 사용하여 기본 아키텍처를 결정합니다.  Microsoft.Build.Utilities.ExecutableType 열거형의 멤버에 대해 구문 분석할 수 있어야 합니다.|  
|`TrackerFrameworkPath`|선택적 assetId:///String?qualifyHint=False&autoUpgrade=True 매개 변수입니다.<br /><br /> FileTracker.dll을 포함하는 적절한 .NET Framework 위치에 대한 경로를 지정합니다.<br /><br /> 설정된 경우, 사용자는 전달하는 FileTracker.dll의 비트가 사용하려는 ResGen.exe의 비트와 일치하는지 확인해야 합니다.  위치를 설정하지 않은 경우 이 작업은 현재 .NET Framework 버전에 따라 적절한 위치를 결정합니다.|  
|`TrackerLogDirectory`|선택적 assetId:///String?qualifyHint=False&autoUpgrade=True 매개 변수입니다.<br /><br /> 이 작업 실행에 대한 추적 로그를 배치할 중간 디렉터리를 지정합니다.|  
|`TrackerSdkPath`|선택적 assetId:///String?qualifyHint=False&autoUpgrade=True 매개 변수입니다.<br /><br /> Tracker.exe를 포함하는 적절한 Windows SDK 위치에 대한 경로를 지정합니다.<br /><br /> 설정된 경우, 사용자는 전달하는 Tracker.exe의 비트가 사용하려는 ResGen.exe의 비트와 일치하는지 확인해야 합니다.  위치를 설정하지 않은 경우 이 작업은 현재 Windows SDK에 따라 적절한 위치를 결정합니다.|  
|`TrackFileAccess`|선택적 [Boolean](assetId:///Boolean?qualifyHint=False&autoUpgrade=True) 매개 변수입니다.<br /><br /> true인 경우 입력 파일의 디렉터리를 상대 파일 경로를 확인하는 데 사용합니다.|  
|`UseSourcePath`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 파일의 상대 경로를 확인하는 데 입력 파일의 디렉터리를 사용하도록 지정합니다.|  
  
## 설명  
 .resx 파일에는 다른 리소스 파일에 대한 링크가 포함될 수 있으므로 출력이 최신 상태인지 확인하기 위해 단순히 .resx 및 .resource 파일 타임스탬프를 비교하는 것만으로는 충분하지 않습니다.  `GenerateResource` 작업에서는 .resx 파일의 링크를 따라가며 연결된 파일의 타임스탬프도 함께 검사합니다.  그러므로, 대개의 경우 `GenerateResource` 작업이 들어 있는 대상에 대해 `Inputs` 및 `Outputs` 특성을 사용하지 말아야 합니다. 이렇게 하면 실제로 실행해야 할 작업이 생략될 수 있습니다.  
  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
 .NET 3.4 프로젝트를 대상으로 하기 위해 MSBuild 4.0을 사용하는 경우 x86 리소스에서 빌드가 실패할 수 있습니다.  대상을 AnyCPU 어셈블리로 빌드하여 이 문제를 해결할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `Resx` 항목 컬렉션에서 지정한 파일에서 .resources 파일을 생성하기 위해 `GenerateResource` 작업을 사용합니다.  
  
```  
<GenerateResource  
    Sources="@(Resx)"  
    OutputResources="@(Resx->'$(IntermediateOutputPath)%(Identity).resources')">  
    <Output  
        TaskParameter="OutputResources"  
        ItemName="Resources"/>  
</GenerateResource>  
```  
  
 `GenerateResource` 작업은 \<EmbeddedResource\> 항목의 \<LogicalName\> 메타데이터를 사용하여 어셈블리에 포함된 리소스 이름을 지정합니다.  
  
 어셈블리 이름은 myAssembly이고, 다음 코드는 someQualifier.someResource.resources라는 포함된 리소스를 생성한다고 가정합니다.  
  
```  
<ItemGroup>   <EmbeddedResource Include="myResource.resx">       <LogicalName>someQualifier.someResource.resources</LogicalName>   </EmbeddedResource></ItemGroup>  
```  
  
 \<LogicalName\> 메타데이터가 없으면 리소스 이름은 myAssembly.myResource.resources이 됩니다.  이 예제에서는 Visual Basic 및 C\# 빌드 프로세스에만 적용됩니다.  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)