---
title: "ReadLinesFromFile Task | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#ReadLinesFromFile"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MSBuild, ReadLinesFromFile task"
  - "ReadLinesFromFile task [MSBuild]"
ms.assetid: a18af929-b53a-4d9e-b7bf-e3d3737ee85f
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 10
---
# ReadLinesFromFile Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

텍스트 파일에서 항목의 목록을 읽습니다.  
  
## 매개 변수  
 다음 표에서는 `ReadLinesFromFile` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`File`|필수적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> 읽을 파일을 지정합니다.  파일의 각 줄에 항목이 하나씩 있어야 합니다.|  
|`Lines`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 파일에서 읽은 줄이 들어 있습니다.|  
  
## 설명  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `ReadLinesFromFile` 작업을 사용하여 텍스트 파일에서 목록의 항목을 만듭니다.  파일에서 읽은 항목은 `ItemsFromFile` 항목 컬렉션에 저장됩니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyTextFile Include="Items.txt"/>  
    </ItemGroup>  
  
    <Target Name="ReadFromFile">  
        <ReadLinesFromFile  
            File="@(MyTextFile)" >  
            <Output  
                TaskParameter="Lines"  
                ItemName="ItemsFromFile"/>  
        </ReadLinesFromFile>  
    </Target>  
  
</Project>  
```  
  
## 참고 항목  
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [MSBuild 개념](../msbuild/msbuild-concepts.md)   
 [작업](../msbuild/msbuild-tasks.md)