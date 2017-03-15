---
title: "RemoveDuplicates Task | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#RemoveDuplicates"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MSBuild, RemoveDuplicates task"
  - "RemoveDuplicates task [MSBuild]"
ms.assetid: 481cbab6-73ff-488c-aba5-2c09f9eb1e04
caps.latest.revision: 9
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 9
---
# RemoveDuplicates Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지정한 항목 컬렉션에서 중복 항목을 제거합니다.  
  
## 매개 변수  
 다음 표에서는 `RemoveDuplicates` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`Filtered`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 중복 항목이 모두 제거된 항목 컬렉션이 들어 있습니다.|  
|`Inputs`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 중복 항목을 제거할 항목 컬렉션입니다.|  
  
## 설명  
 이 작업에서는 대\/소문자를 구분하지 않으며 중복 여부를 확인할 때 항목 메타데이터를 비교하지 않습니다.  
  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `RemoveDuplicates` 작업을 사용하여 `MyItems` 항목 컬렉션에서 중복 항목을 제거합니다.  작업이 완료된 후에 `FilteredItems` 항목 컬렉션에는 항목이 하나만 남습니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyItems Include="MyFile.cs"/>  
        <MyItems Include="MyFile.cs">  
            <Culture>fr</Culture>  
        </MyItems>  
        <MyItems Include="myfile.cs"/>  
    </ItemGroup>  
  
    <Target Name="RemoveDuplicateItems">  
        <RemoveDuplicates  
            Inputs="@(MyItems)">  
            <Output  
                TaskParameter="Filtered"  
                ItemName="FilteredItems"/>  
        </RemoveDuplicates>  
    </Target>  
</Project>  
```  
  
## 참고 항목  
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [MSBuild 개념](../msbuild/msbuild-concepts.md)   
 [작업](../msbuild/msbuild-tasks.md)