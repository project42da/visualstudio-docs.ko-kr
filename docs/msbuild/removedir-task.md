---
title: "RemoveDir Task | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#RemoveDir"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "RemoveDir task [MSBuild]"
  - "MSBuild, RemoveDir task"
ms.assetid: 7ab214be-26b2-4bcd-9de8-c1b2091c0b74
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# RemoveDir Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지정한 디렉터리와 해당 파일 및 하위 디렉터리 전체를 제거합니다.  
  
## 매개 변수  
 다음 표에서는 `RemoveDir` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`Directories`|필수적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 삭제할 디렉터리를 지정합니다.|  
|`RemovedDirectories`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 성공적으로 삭제한 디렉터리가 들어 있습니다.|  
  
## 설명  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `OutputDirectory` 및 `DebugDirectory` 속성에서 지정한 디렉터리를 제거합니다.  이러한 경로는 프로젝트 디렉터리를 기준으로 한 상대 경로로 취급됩니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2005">  
  
    <PropertyGroup>  
        <OutputDirectory>\Output\</OutputDirectory>  
        <DebugDirectory>\Debug\</DebugDirectory>  
    </PropertyGroup>  
  
    <Target Name="RemoveDirectories">  
        <RemoveDir  
            Directories="$(OutputDirectory);$(DebugDirectory)" />  
    </Target>  
  
</Project>  
```  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)