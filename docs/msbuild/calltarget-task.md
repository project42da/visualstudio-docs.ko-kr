---
title: "CallTarget Task | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "CallTarget task [MSBuild]"
  - "MSBuild, CallTarget task"
ms.assetid: bb1fe2c4-4383-436f-8326-c24cc4a46150
caps.latest.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 6
---
# CallTarget Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

프로젝트 파일 내의 지정된 대상을 호출합니다.  
  
## 작업 매개 변수  
 다음 표에서는 `CallTarget` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`RunEachTargetSeparately`|선택적 `Boolean` 출력 매개 변수입니다.<br /><br /> `true`이면 대상마다 한 번씩 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 엔진이 호출됩니다.  `false`이면 모든 대상을 빌드하도록 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 엔진이 한 번 호출됩니다.  기본값은 `false`입니다.|  
|`TargetOutputs`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 빌드된 모든 대상의 출력을 포함합니다.|  
|`Targets`|선택적 `String[]` 매개 변수입니다.<br /><br /> 빌드할 대상을 지정합니다.|  
|`UseResultsCache`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 캐시된 결과가 있으면 해당 결과가 반환됩니다.<br /><br /> **참고** MSBuild 작업이 실행되면 결과가 범위\(ProjectFileName, GlobalProperties\)\[TargetNames\]에 빌드 항목의 목록으로 캐시됩니다.|  
  
## 설명  
 `Targets`에서 지정한 대상이 실패하고 `RunEachTargetSeparately`가 `true`이면 작업은 계속해서 나머지 대상을 빌드합니다.  
  
 기본 대상을 빌드하려는 경우 [MSBuild 작업](../msbuild/msbuild-task.md)을 사용하고 `Projects` 매개 변수를 `$(MSBuildProjectFile)`와 같게 설정합니다.  
  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `CallOtherTargets` 내부에서 `TargetA`를 호출합니다.  
  
```  
<Project DefaultTargets="CallOtherTargets"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <Target Name="CallOtherTargets">  
        <CallTarget Targets="TargetA"/>  
    </Target>  
  
    <Target Name="TargetA">  
        <Message Text="Building TargetA..." />  
    </Target>  
  
</Project>  
```  
  
## 참고 항목  
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [대상](../msbuild/msbuild-targets.md)