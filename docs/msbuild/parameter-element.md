---
title: "Parameter Element | Microsoft Docs"
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
  - "Parameter element [MSBuild]"
  - "<Parameter> element [MSBuild]"
ms.assetid: b273afff-b500-4e97-8cfd-31f39fa64a51
caps.latest.revision: 7
caps.handback.revision: 7
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Parameter Element
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`UsingTask` `TaskFactory`에서 생성한 작업의 특정 매개 변수가 들어 있습니다. 요소의 이름은 매개 변수의 이름입니다. 자세한 내용은 [UsingTask Element \(MSBuild\)](../msbuild/usingtask-element-msbuild.md)을 참조하십시오.  
  
## 구문  
  
```  
<ParameterGroup ParameterType="SystemType"  
    Output="true/false"  
    Required="true/false" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`ParameterType`|선택적 특성입니다.<br /><br /> 이 매개 변수의 .NET 형식입니다\(예: "System.String"\).|  
|`Output`|선택적 부울 특성입니다.<br /><br /> `true`인 경우 이 매개 변수는 작업의 출력 매개 변수입니다.  기본값은 `false`입니다.|  
|`Required`|선택적 부울 특성입니다.<br /><br /> `true`인 경우 이 매개 변수는 작업의 필수 매개 변수입니다.  기본값은 `false`입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[ParameterGroup](../msbuild/parametergroup-element.md)|`UsingTask` `TaskFactory`에서 생성한 작업에 있는 매개 변수의 선택적 목록이 들어 있습니다.|  
  
## 예제  
 다음 예제에서는 `Parameter` 요소를 사용하는 방법을 보여 줍니다.  
  
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