---
title: "WriteLinesToFile Task | Microsoft Docs"
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
  - "http://schemas.microsoft.com/developer/msbuild/2003#WriteLinesToFile"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "WriteLinesToFile task [MSBuild]"
  - "MSBuild, WriteLinesToFile task"
ms.assetid: 9c8862ac-8da5-4437-9430-ecc30421f1c9
caps.latest.revision: 9
caps.handback.revision: 9
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# WriteLinesToFile Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지정한 텍스트 파일에 특정 항목의 경로를 씁니다.  
  
## 작업 매개 변수  
 다음 표에서는 `WriteLinestoFile` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`File`|필수적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> 항목을 기록할 파일을 지정합니다.|  
|`Lines`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 파일에 기록할 항목을 지정합니다.|  
|`Overwrite`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 작업에서 파일의 모든 기존 내용을 덮어씁니다.|  
|`Encoding`|선택적 `String` 매개 변수입니다.<br /><br /> 예를 들어, "유니코드"의 경우 문자 인코딩을 선택합니다.  <xref:System.Text.Encoding>을 참조하십시오.|  
  
## 설명  
 `Overwrite`가 `true`인 경우 새 파일을 만들고 파일에 내용을 쓴 다음 파일을 닫습니다.  대상 파일이 이미 있으면 덮어씁니다.  `Overwrite`가 `false`이면 내용을 파일에 추가하고 대상 파일이 아직 없으면 만듭니다.  
  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `WriteLinesToFile` 작업을 사용하여 `MyItems` 항목 컬렉션의 항목 경로를 `MyTextFile` 항목 컬렉션에 지정된 파일에 기록합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyTextFile Include="Items.txt"/>  
        <MyItems Include="*.cs"/>  
    </ItemGroup>  
  
    <Target Name="WriteToFile">  
        <WriteLinesToFile  
            File="@(MyTextFile)"  
            Lines="@(MyItems)"  
            Overwrite="true"  
            Encoding="Unicode"/>  
    </Target>  
  
</Project>  
```  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)