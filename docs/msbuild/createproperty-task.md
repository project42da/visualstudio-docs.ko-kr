---
title: "CreateProperty Task | Microsoft Docs"
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
  - "http://schemas.microsoft.com/developer/msbuild/2003#CreateProperty"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "CreateProperty task [MSBuild]"
  - "MSBuild, CreateProperty task"
ms.assetid: fbc31a88-62d4-43d2-b739-68ef3fac38f5
caps.latest.revision: 11
caps.handback.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# CreateProperty Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

전달된 값으로 속성을 채웁니다.  이렇게 하면 한 속성이나 문자열에서 다른 속성이나 문자열로 값을 복사할 수 있습니다.  
  
## 특성  
 다음 표에서는 `CreateProperty` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`Value`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 새 속성에 복사할 값을 지정합니다.|  
|`ValueSetByTask`|선택적 `String` 출력 매개 변수입니다.<br /><br /> `Value` 매개 변수와 동일한 값이 들어 있습니다.  이 매개 변수는 출력이 최신 상태여서 바깥쪽 대상을 생략하는 경우 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서 출력 속성을 설정하지 않도록 하려는 경우에만 사용합니다.|  
  
## 설명  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `SourceFilename` 및 `SourceFileExtension` 속성의 값을 조합하여 `NewFile` 속성을 만들기 위해 `CreateProperty` 작업을 사용합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <PropertyGroup>  
        <SourceFilename>Module1</SourceFilename>  
        <SourceFileExtension>vb</SourceFileExtension>  
    </PropertyGroup>  
  
    <Target Name="CreateProperties">  
  
        <CreateProperty  
            Value="$(SourceFilename).$(SourceFileExtension)">  
            <Output  
                TaskParameter="Value"  
                PropertyName="NewFile" />  
        </CreateProperty>  
  
    </Target>  
  
</Project>  
```  
  
 프로젝트를 실행한 후에 `NewFile` 속성의 값은 `Module1.vb`입니다.  
  
## 참고 항목  
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [작업](../msbuild/msbuild-tasks.md)