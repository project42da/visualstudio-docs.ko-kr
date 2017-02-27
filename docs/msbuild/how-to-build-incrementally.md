---
title: "방법: 증분 빌드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "증분 빌드"
  - "MSBuild, 증분 빌드"
  - "MSBuild, 증분 빌드"
ms.assetid: 8d82d7d8-a2f1-4df6-9d2f-80b9e0cb3ac3
caps.latest.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 21
---
# 방법: 증분 빌드
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

큰 프로젝트를 빌드할 경우 이전에 빌드된 구성 요소 중 아직까지 최신 상태인 구성 요소는 다시 빌드하지 않는 것이 중요합니다.  매번 모든 대상을 빌드하면 각 빌드를 완성하는 데 오랜 시간이 걸립니다.  증분 빌드\(전에 빌드된 적이 없는 대상이나 만료된 대상만 다시 빌드되는 빌드\)를 활성화하려면 [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)]\([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]\)에서 입력 파일의 타임스탬프를 출력 파일의 타임스탬프와 비교하여 대상을 건너뛸 것인지, 빌드할 것인지 또는 일부만 빌드할 것인지를 결정합니다.  그러나 입력과 출력 사이에는 일대일 매핑이 있어야 합니다.  변환을 사용하여 대상에서 이러한 직접 매핑을 식별하도록 할 수 있습니다.  변환에 대한 자세한 내용은 [변환](../msbuild/msbuild-transforms.md)을 참조하십시오.  
  
## 입력 및 출력 지정  
 입력과 출력이 프로젝트 파일에 지정된 경우 대상을 증분 빌드할 수 있습니다.  
  
#### 대상의 입력 및 출력을 지정하려면  
  
-   `Target` 요소의 `Inputs` 및 `Outputs` 특성을 사용합니다.  예를 들면 다음과 같습니다.  
  
    ```  
    <Target Name="Build"  
        Inputs="@(CSFile)"  
        Outputs="hello.exe">  
    ```  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 입력 파일의 타임스탬프를 출력 파일의 타임스탬프와 비교하여 대상을 건너뛸 것인지, 빌드할 것인지 또는 일부만 빌드할 것인지 결정할 수 있습니다.  다음 예제에서 `@(CSFile)` 항목 목록에 있는 파일이 hello.exe 파일보다 새로운 파일인 경우 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 대상을 실행하고, 그렇지 않으면 건너뜁니다.  
  
```  
<Target Name="Build"   
    Inputs="@(CSFile)"   
    Outputs="hello.exe">  
  
    <Csc  
        Sources="@(CSFile)"   
        OutputAssembly="hello.exe"/>  
</Target>  
```  
  
 대상에 입력과 출력이 지정된 경우, 각 출력이 하나의 입력에만 매핑되거나 입력과 출력 사이에 직접적인 매핑이 없는 상태가 됩니다.  예를 들어, 이전의 [Csc Task](../msbuild/csc-task.md)에서 hello.exe라는 출력 파일은 모든 입력에 따라 달라지므로 단일 입력에 매핑될 수 없습니다.  
  
> [!NOTE]
>  각 출력이 하나의 입력에만 매핑되는 경우보다 입력과 출력 사이에 직접적인 매핑이 없는 경우에 대상이 더 자주 빌드됩니다. 일부 입력이 변경되면 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서 다시 빌드해야 하는 출력을 결정할 수 없기 때문입니다.  
  
 다수의 입력에서 하나의 출력 어셈블리를 생성하는 `Csc` 및 [Vbc](../msbuild/vbc-task.md) 같은 작업과 달리, [LC Task](../msbuild/lc-task.md) 같이 입력과 출력 사이의 직접 매핑을 식별할 수 있는 작업은 증분 백업에 가장 적합합니다.  
  
## 예제  
 다음 예제에서는 가상의 도움말 시스템에 사용할 도움말 파일을 빌드하는 프로젝트를 사용합니다.  프로젝트는 소스 .txt 파일을 중간 .content 파일로 변환하는 방식으로 작동합니다. 그런 다음 변환된 파일이 XML 메타데이터 파일과 결합하여 도움말 시스템에서 사용되는 최종 .help 파일을 생성합니다.  이 프로젝트에서는 다음과 같은 가상의 작업을 사용합니다.  
  
-   `GenerateContentFiles`: .txt 파일을 .content 파일로 변환합니다.  
  
-   `BuildHelp`: .content 파일과 XML 메타데이터 파일을 결합하여 최종 .help 파일을 빌드합니다.  
  
 이 프로젝트에서는 변환을 사용하여 `GenerateContentFiles` 작업의 입력과 출력 사이에 일대일 매핑을 만듭니다.  자세한 내용은 [변환](../msbuild/msbuild-transforms.md)을 참조하십시오.  또한 `Output` 요소는 `GenerateContentFiles` 작업의 출력을 자동으로 `BuildHelp` 작업의 입력으로 사용하도록 설정됩니다.  
  
 이 프로젝트 파일에는 `Convert` 및 `Build` 대상 모두가 포함되어 있습니다.  `GenerateContentFiles`와 `BuildHelp` 작업은 각각 `Convert`와 `Build` 대상에 배치되므로 각 대상을 증분 빌드할 수 있습니다.  `GenerateContentFiles` 작업의 출력은 `Output` 요소를 사용하여 `ContentFile` 항목 목록에 배치되며 이 컬렉션에서 `BuildHelp` 작업의 입력으로 사용될 수 있습니다.  `Output` 요소를 이런 식으로 사용하면 한 작업의 출력을 자동으로 다른 작업의 입력으로 제공할 수 있으므로 개별 항목이나 항목 목록을 각 작업에 수동으로 나열할 필요가 없습니다.  
  
> [!NOTE]
>  `GenerateContentFiles` 대상을 증분 빌드할 수 있지만, 이 경우 해당 대상의 모든 출력은 항상 `BuildHelp` 대상의 입력이 되어야 합니다.  사용자가 `Output` 요소를 사용하는 경우 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 자동으로 한 대상의 모든 출력을 다른 대상의 입력으로 제공합니다.  
  
```  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <ItemGroup>  
        <TXTFile Include="*.txt"/>  
        <XMLFile Include="\metadata\*.xml"/>  
    </ItemGroup>  
  
    <Target Name = "Convert"  
        Inputs="@(TXTFile)"  
        Outputs="@(TXTFile->'%(Filename).content')">  
  
        <GenerateContentFiles  
            Sources = "@(TXTFile)">  
            <Output TaskParameter = "OutputContentFiles"  
                ItemName = "ContentFiles"/>  
        </GenerateContentFiles>  
    </Target>  
  
    <Target Name = "Build" DependsOnTargets = "Convert"  
        Inputs="@(ContentFiles);@(XMLFiles)"  
        Outputs="$(MSBuildProjectName).help">  
  
        <BuildHelp  
            ContentFiles = "@(ContentFiles)"  
            MetadataFiles = "@(XMLFile)"  
            OutputFileName = "$(MSBuildProjectName).help"/>  
    </Target>  
</Project>  
```  
  
## 참고 항목  
 [대상](../msbuild/msbuild-targets.md)   
 [Target 요소\(MSBuild\)](../msbuild/target-element-msbuild.md)   
 [변환](../msbuild/msbuild-transforms.md)   
 [Csc Task](../msbuild/csc-task.md)   
 [Vbc Task](../msbuild/vbc-task.md)