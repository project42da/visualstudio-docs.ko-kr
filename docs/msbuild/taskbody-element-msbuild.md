---
title: "TaskBody Element (MSBuild) | Microsoft Docs"
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
helpviewer_keywords: 
  - "TaskBody element [MSBuild]"
  - "<TaskBody> element [MSBuild]"
ms.assetid: 49d8741b-f1ea-4470-94fd-a1ac27341a6a
caps.latest.revision: 7
caps.handback.revision: 7
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# TaskBody Element (MSBuild)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`UsingTask` `TaskFactory`로 전달된 데이터를 포함합니다. 자세한 내용은 [UsingTask Element \(MSBuild\)](../msbuild/usingtask-element-msbuild.md)을 참조합니다.  
  
## 구문  
  
```  
<TaskBody Evaluate="true/false" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`Evaluate`|선택적 부울 특성입니다.<br /><br /> `true`인 경우 MSBuild는 모든 내부 요소를 평가하고 작업이 인스턴스화될 때 정보가 `TaskFactory`로 전달되기 전에 항목과 속성을 확장합니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|데이터|`TaskBody` 태그 사이의 텍스트가 `TaskFactory`로 그대로 보내집니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[UsingTask](../msbuild/usingtask-element-msbuild.md)|[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 내에 작업을 등록할 수 있게 합니다.  프로젝트에 `UsingTask` 요소가 0개 이상 있을 수 있습니다.|  
  
## 예제  
 다음 예제에서는 `TaskBody` 요소를 `Evaluate` 특성과 함께 사용하는 방법을 보여 줍니다.  
  
```  
<UsingTask TaskName="MyTask" AssemblyName="My.Assembly" TaskFactory="MyTaskFactory">  
       <ParameterGroup>  
              <Parameter1 ParameterType="System.String" Required="False" Output="False"/>  
              <Parameter2 ParameterType="System.Int" Required="True" Output="False"/>  
              ...  
</ParameterGroup>  
       <TaskBody Evaluate="true">  
      ... Task factory-specific data ...  
       </TaskBody>  
</UsingTask>  
```  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [Project File Schema Reference](../msbuild/msbuild-project-file-schema-reference.md)