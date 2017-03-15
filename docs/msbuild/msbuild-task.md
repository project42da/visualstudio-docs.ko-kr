---
title: "MSBuild 작업 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#MSBuild"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MSBuild 작업[MSBuild]"
  - "MSBuild, MSBuild 작업"
ms.assetid: 76577f6c-7669-44ad-a840-363e37a04d34
caps.latest.revision: 32
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 32
---
# MSBuild 작업
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다른 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트에서 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트를 빌드합니다.  
  
## 매개 변수  
 다음 표에서는 `MSBuild` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`BuildInParallel`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 가능한 경우 `Projects` 매개 변수에 지정된 프로젝트가 병렬로 빌드됩니다.  기본값은 `false`입니다.|  
|`Projects`|필수적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 빌드할 프로젝트 파일을 지정합니다.|  
|`Properties`|선택적 `String` 매개 변수입니다.<br /><br /> 자식 프로젝트에 대한 전역 속성으로 적용할 속성 이름\/값 쌍을 세미콜론으로 구분한 목록입니다.  이 매개 변수를 지정하는 것은 [MSBuild.exe](../msbuild/msbuild-command-line-reference.md)를 사용하여 빌드할 때 **\/property** 스위치를 사용하여 속성을 설정하는 것과 기능 면에서 같습니다.  예를 들면 다음과 같습니다.<br /><br /> `Properties="Configuration=Debug;Optimize=$(Optimize)"`<br /><br /> `Properties` 매개 변수를 통해 프로젝트에 속성을 전달하면 프로젝트 파일이 이미 로드된 경우에도 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 프로젝트의 새 인스턴스를 만듭니다.  프로젝트의 새 인스턴스가 만들어지면 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 새 인스턴스를 전역 속성이 서로 다르고 프로젝트의 다른 인스턴스와 병렬로 빌드할 수 있는 별개의 프로젝트로 처리합니다.  예를 들어, 릴리스 구성을 디버그 구성과 동시에 빌드할 수 있습니다.|  
|`RebaseOutputs`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 빌드된 프로젝트의 대상 출력 항목에 대한 상대 경로가 호출하는 프로젝트에 상대적으로 조정됩니다.  기본값은 `false`입니다.|  
|`RemoveProperties`|선택적 `String` 매개 변수입니다.<br /><br /> 제거할 전역 속성 집합을 지정합니다.|  
|`RunEachTargetSeparately`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 작업이 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에 전달된 목록에 있는 대상을 한 번에 모두 호출하는 대신 한 번에 하나씩 호출합니다.  이 매개 변수를 `true`로 설정하면 이전에 호출한 대상이 실패하더라도 이후의 대상이 호출됩니다.  그렇지 않으면 빌드 오류가 발생할 경우 이후 모든 대상의 호출이 중지됩니다.  기본값은 `false`입니다.|  
|`SkipNonexistentProjects`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 디스크에 없는 프로젝트 파일을 건너뜁니다.  그렇지 않으면 그러한 프로젝트에서 오류가 발생합니다.|  
|`StopOnFirstFailure`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 프로젝트 중 하나가 빌드에 실패하면 프로젝트가 더 이상 빌드되지 않습니다.  현재 \(다중 프로세서\)와 병렬로 빌드하는 경우는 지원되지 않습니다.|  
|`TargetAndPropertyListSeparators`|선택적 `String[]` 매개 변수입니다.<br /><br /> 대상 및 속성의 목록을 `Project` 항목 메타데이터로 지정합니다.  구분 기호는 처리 전에 이스케이프 해제됩니다.  e.g. %3b \(이스케이프는 ';'\)를 이스케이프 되지 않은 것 처럼 처리 됩니다 ';'.|  
|`TargetOutputs`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 읽기 전용 출력 매개 변수입니다.<br /><br /> 모든 프로젝트 파일에서 빌드된 대상의 출력을 반환합니다.  지정된 대상의 출력만 반환되고 이러한 대상이 의존하는 다른 대상이 있을 수 있는 출력은 반환되지 않습니다.<br /><br /> `TargetOutputs` 매개 변수에는 다음 메타데이터도 들어 있습니다.<br /><br /> -   `MSBuildSourceProjectFile`: 출력을 설정하는 대상이 들어 있는 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트 파일<br />-   `MSBuildSourceTargetName`: 출력을 설정하는 대상 **Note:**  각 프로젝트 파일이나 대상의 출력을 개별적으로 식별하려면 각 프로젝트 파일이나 대상에 대해 `MSBuild` 작업을 개별적으로 실행해야 합니다.  `MSBuild` 작업을 한 번만 실행하여 모든 프로젝트 파일을 빌드하면 모든 대상의 출력이 하나의 배열로 수집됩니다.|  
|`Targets`|선택적 `String` 매개 변수입니다.<br /><br /> 프로젝트 파일에 빌드할 하나 이상의 대상을 지정합니다.  대상 이름의 목록을 구분하는 데는 세미콜론을 사용합니다.  `MSBuild` 작업에 대상을 지정하지 않으면 프로젝트 파일에 지정한 기본 대상이 빌드됩니다. **Note:**  대상은 모든 프로젝트 파일에 있어야 합니다.  그렇지 않으면 빌드 오류가 발생합니다.|  
|`ToolsVersion`|선택적 `String` 매개 변수입니다.<br /><br /> 이 작업에 전달된 프로젝트를 빌드할 때 사용할 `ToolsVersion`을 지정합니다.<br /><br /> [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 작업에서 프로젝트에 지정된 것과 다른 버전의 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]를 대상으로 하는 프로젝트를 빌드할 수 있게 합니다.  유효한 값은 `2.0`, `3.0` 및 `3.5`입니다.  기본값은 `3.5`으로,|  
|`UnloadProjectsOnCompletion`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 작업이 완료된 후 프로젝트가 언로드됩니다.|  
|`UseResultsCache`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 캐시된 결과가 있으면 해당 결과가 반환됩니다.  MSBuild 작업이 실행되면 결과가 범위\(ProjectFileName, GlobalProperties\)\[TargetNames\]에 캐시됩니다.<br /><br /> 빌드 항목의 목록으로|  
  
## 설명  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
 [Exec Task](../msbuild/exec-task.md)을 사용하여 MSBuild.exe를 시작하는 경우와 달리 이 작업에서는 동일한 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로세스를 사용하여 자식 프로젝트를 빌드합니다.  이미 빌드되어 생략할 수 있는 대상의 목록은 부모와 자식 빌드 사이에 공유됩니다.  또한 이 작업에서는 새 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로세스를 만들지 않으므로 속도가 더 빠릅니다.  
  
 이 작업에서는 프로젝트 파일뿐만 아니라 솔루션 파일도 처리할 수 있습니다.  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서 프로젝트를 동시에 빌드하는 데 필요한 모든 구성은 포트, 프로토콜, 시간 초과, 재시도 등의 원격 인프라와 관련이 있는 경우에도 구성 파일을 사용하여 구성할 수 있어야 합니다.  가능하면 구성 항목은 `MSBuild` 작업에 작업 매개 변수로 지정할 수 있어야 합니다.  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 3.5부터는 솔루션 프로젝트가 빌드하는 모든 하위 프로젝트의 TargetOutputs가 해당 솔루션 프로젝트에 표시됩니다.  
  
## 프로젝트에 속성 전달  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 3.5 이전 버전의 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 항목에 나열된 여러 프로젝트에 서로 다른 속성 집합을 전달하는 것이 어려웠습니다.  [MSBuild Task](../msbuild/msbuild-task.md)의 속성 특성을 사용하는 경우 [MSBuild Task](../msbuild/msbuild-task.md)을 일괄 처리하여 항목 목록에 있는 각 프로젝트에 서로 다른 속성을 조건부로 제공하지 않으면 빌드 중인 모든 프로젝트에 해당 속성 적용됩니다.  
  
 그러나 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 3.5에서는 [MSBuild Task](../msbuild/msbuild-task.md)을 사용하여 빌드 중인 여러 프로젝트에 서로 다른 속성을 전달할 수 있는 유연한 방법을 제공하는 두 개의 예약된 메타데이터 항목, Properties 및 AdditionalProperties를 새로 제공합니다.  
  
> [!NOTE]
>  이러한 새 메타데이터 항목은 [MSBuild Task](../msbuild/msbuild-task.md)의 Projects 특성에 전달된 항목에만 적용할 수 있습니다.  
  
## 다중 프로세서 빌드의 이점  
 이 새 메타데이터의 사용에 따른 주요 이점 중 하나는 다중 프로세서 시스템에서 프로젝트를 병렬로 빌드할 때 얻을 수 있습니다.  이 메타데이터를 사용하면 일괄 처리 또는 조건부 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 작업을 수행하지 않고도 모든 프로젝트를 단일 [MSBuild Task](../msbuild/msbuild-task.md) 호출로 통합할 수 있습니다.  또한 단일 [MSBuild Task](../msbuild/msbuild-task.md)만 호출해도 Projects 특성에 나열된 모든 프로젝트가 병렬로 빌드됩니다  \(단, [MSBuild Task](../msbuild/msbuild-task.md)에 `BuildInParallel=true` 특성이 있을 경우\). 자세한 내용은 [병렬로 여러 프로젝트 빌드](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)을 참조하십시오.  
  
## Properties 메타데이터  
 일반적으로 [MSBuild Task](../msbuild/msbuild-task.md)을 사용하여 여러 솔루션 파일을 빌드할 때는 서로 다른 빌드 구성을 사용해야 합니다.  즉, 디버그 구성을 사용하여 솔루션 a1을 빌드하고 릴리스 구성을 사용하여 솔루션 a2를 빌드할 수 있습니다.  [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 2.0에서 이 프로젝트는 다음과 같습니다.  
  
> [!NOTE]
>  다음 예제에서 "…"는 추가 솔루션 파일을 나타냅니다.  
  
### a.proj  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="Build">  
        <MSBuild Projects="a1.sln..." Properties="Configuration=Debug"/>  
        <MSBuild Projects="a2.sln" Properties="Configuration=Release"/>  
    </Target>  
</Project>  
```  
  
 그러나 속성 메타데이터를 사용하면 이 작업을 단순화하여 다음과 같이 단일 [MSBuild Task](../msbuild/msbuild-task.md)을 사용할 수 있습니다.  
  
### a.proj  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <ProjectToBuild Include="a1.sln…">  
            <Properties>Configuration=Debug</Properties>  
        </ProjectToBuild>  
        <ProjectToBuild Include="a2.sln">  
            <Properties>Configuration=Release</Properties>  
        </ProjectToBuild>  
    </ItemGroup>  
    <Target Name="Build">  
        <MSBuild Projects="@(ProjectToBuild)"/>  
    </Target>  
</Project>  
```  
  
 \-또는\-  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <ProjectToBuild Include="a1.sln…"/>  
        <ProjectToBuild Include="a2.sln">  
            <Properties>Configuration=Release</Properties>  
        </ProjectToBuild>  
    </ItemGroup>  
    <Target Name="Build">  
        <MSBuild Projects="@(ProjectToBuild)"   
          Properties="Configuration=Debug"/>  
    </Target>  
</Project>  
```  
  
## AdditionalProperties 메타데이터  
 [MSBuild Task](../msbuild/msbuild-task.md)을 사용하여 두 개의 솔루션 파일을 빌드할 때 둘 다 릴리스 구성을 사용하지만 하나는 x86 아키텍처를 사용하고 다른 하나는 ia64 아키텍처를 사용한다고 가정할 경우  [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 2.0에서는 [MSBuild Task](../msbuild/msbuild-task.md)의 인스턴스를 여러 개 만들어야 합니다. 즉, 하나는 x86 아키텍처를 사용하는 릴리스 구성을 사용하여 프로젝트를 빌드하기 위한 것이고 다른 하나는 ia64 아키텍처를 사용하는 릴리스 구성을 사용하여 프로젝트를 빌드하기 위한 것입니다.  이 프로젝트 파일은 다음과 같습니다.  
  
### a.proj  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="Build">  
        <MSBuild Projects="a1.sln…" Properties="Configuration=Release;   
          Architecture=x86"/>  
        <MSBuild Projects="a2.sln" Properties="Configuration=Release;   
          Architecture=ia64"/>  
    </Target>  
</Project>  
```  
  
 그러나 AdditionalProperties 메타데이터를 사용하면 이 작업을 단순화하여 다음과 같이 단일 [MSBuild Task](../msbuild/msbuild-task.md)을 사용할 수 있습니다.  
  
### a.proj  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <ProjectToBuild Include="a1.sln…">  
            <AdditionalProperties>Architecture=x86  
              </AdditionalProperties>  
        </ProjectToBuild>  
        <ProjectToBuild Include="a2.sln">  
            <AdditionalProperties>Architecture=ia64  
              </AdditionalProperties>  
        </ProjectToBuild>  
    </ItemGroup>  
    <Target Name="Build">  
        <MSBuild Projects="@(ProjectToBuild)"   
          Properties="Configuration=Release"/>  
    </Target>  
</Project>  
```  
  
## 예제  
 다음 예제에서는 `ProjectReferences` 항목 컬렉션에서 지정한 프로젝트를 빌드하기 위해 `MSBuild` 작업을 사용합니다.  결과 대상 출력은 `AssembliesBuiltByChildProjects` 항목 컬렉션에 저장됩니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <ProjectReferences Include="*.*proj" />  
    </ItemGroup>  
  
    <Target Name="BuildOtherProjects">  
        <MSBuild  
            Projects="@(ProjectReferences)"  
            Targets="Build">  
            <Output  
                TaskParameter="TargetOutputs"  
                ItemName="AssembliesBuiltByChildProjects" />  
        </MSBuild>  
    </Target>  
  
</Project>  
```  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)