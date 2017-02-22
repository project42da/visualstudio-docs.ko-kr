---
title: "FindUnderPath Task | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#FindUnderPath"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MSBuild, FindUnderPath task"
  - "FindUnderPath task [MSBuild]"
ms.assetid: 3c6d58b0-36e8-47aa-bfca-b73dd2045d91
caps.latest.revision: 9
caps.handback.revision: 9
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# FindUnderPath Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지정된 항목 컬렉션에서 지정한 폴더 또는 그 하위 폴더에 경로가 있는 항목을 확인합니다.  
  
## 매개 변수  
 다음 표에서는 `FindUnderPath` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`Files`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> `Path` 매개 변수에서 지정한 경로와 해당 경로를 비교할 파일을 지정합니다.|  
|`InPath`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 지정한 경로 아래에서 찾은 항목이 들어 있습니다.|  
|`OutOfPath`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 지정한 경로 아래에서 발견되지 않은 항목이 들어 있습니다.|  
|`Path`|필수적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> 참조로 사용할 폴더 경로를 지정합니다.|  
|`UpdateToAbsolutePaths`|선택적 `Boolean` 매개 변수입니다.<br /><br /> true인 경우 출력 파일의 경로가 절대 경로로 업데이트됩니다.|  
  
## 설명  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `FindUnderPath` 작업을 사용하여 `MyFiles` 항목에 포함된 파일의 경로가 `SearchPath` 속성에서 지정한 경로 아래에 있는지 확인합니다.  작업이 완료된 후에 `FilesNotFoundInPath` 항목에는 `File1.txt` 파일이 포함되고 `FilesFoundInPath` 항목에는 `File2.txt` 파일이 포함됩니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <MyFiles Include="C:\File1.txt" />  
        <MyFiles Include="C:\Projects\MyProject\File2.txt" />  
    </ItemGroup>  
  
    <PropertyGroup>  
        <SearchPath>C:\Projects\MyProject</SearchPath>  
    </PropertyGroup>  
  
    <Target Name="FindFiles">  
        <FindUnderPath  
            Files="@(MyFiles)"  
            Path="$(SearchPath)">  
            <Output  
                TaskParameter="InPath"  
                ItemName="FilesFoundInPath" />  
            <Output  
                TaskParameter="OutOfPath"  
                ItemName="FilesNotFoundInPath" />  
        </FindUnderPath>  
    </Target>  
  
</Project>  
```  
  
## 참고 항목  
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [작업](../msbuild/msbuild-tasks.md)   
 [MSBuild 개념](../msbuild/msbuild-concepts.md)