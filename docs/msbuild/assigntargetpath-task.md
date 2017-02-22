---
title: "AssignTargetPath Task | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
ms.assetid: 0e830e31-3bcf-4259-b2a8-a5df49b92d51
caps.latest.revision: 4
caps.handback.revision: 4
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# AssignTargetPath Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 작업은 목록 파일을 허용하며 `<TargetPath>` 특성이 이미 지정되지 않은 경우 해당 특성을 추가합니다.  
  
## 작업 매개 변수  
 다음 표에서는 `AssignTargetPath` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`RootFolder`|선택적 `string` 입력 매개 변수입니다.<br /><br /> 대상 링크가 들어 있는 폴더에 대한 경로를 포함합니다.|  
|`Files`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 입력 매개 변수입니다.<br /><br /> 수신되는 파일 목록을 포함합니다.|  
|`AssignedFiles`|Optional<br /><br /> <xref:Microsoft.Build.Framework.ITaskItem> `[]` 출력 매개 변수.<br /><br /> 결과 파일 목록을 포함합니다.|  
  
## 설명  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제는 `AssignTargetPath` 작업을 실행하여 프로젝트를 구성합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="MyProject">  
        <AssignTargetPath  
RootFolder="Resources"  
            Files="@(ResourceFiles)"  
            <Output TaskParameter="AssignedFiles"  
                ItemName="OutAssignedFiles"/>  
        </AssignTargetPath>  
    </Target>  
</Project>  
```  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)