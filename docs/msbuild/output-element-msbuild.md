---
title: "Output Element (MSBuild) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/developer/msbuild/2003#Output"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<Output> Element [MSBuild]"
  - "Output Element [MSBuild]"
ms.assetid: 34bc7cd1-efd3-4b57-b691-4584eeb6a0e9
caps.latest.revision: 13
caps.handback.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Output Element (MSBuild)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

작업 출력 값을 항목과 속성에 저장합니다.  
  
## 구문  
  
```  
<Output TaskParameter="Parameter"  
    PropertyName="PropertyName"   
    Condition = "'String A' == 'String B'" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`TaskParameter`|필수 특성입니다.<br /><br /> 작업의 출력 매개 변수 이름입니다.|  
|`PropertyName`|`PropertyName` 또는 `ItemName` 특성이 필요합니다.<br /><br /> 작업의 출력 매개 변수 값을 전달받는 속성입니다.  다음 프로젝트에서 `$(`*PropertyName*`)` 구문을 사용하여 이 속성을 참조할 수 있습니다.  이 속성 이름은 새 속성 이름이거나 프로젝트에 이미 정의되어 있는 이름일 수 있습니다.<br /><br /> 이 특성은 `ItemName`과 함께 사용할 수 없습니다.|  
|`ItemName`|`PropertyName` 또는 `ItemName` 특성이 필요합니다.<br /><br /> 작업의 출력 매개 변수 값을 전달받는 항목입니다.  프로젝트에서는 `@(`*ItemName*`)` 구문을 사용하여 이 항목을 참조할 수 있습니다.  항목 이름은 새 항목 이름이거나 프로젝트에 이미 정의되어 있는 이름일 수 있습니다.<br /><br /> 이 특성은 `PropertyName`과 함께 사용할 수 없습니다.|  
|`Condition`|선택적 특성입니다.<br /><br /> 확인할 조건입니다.  자세한 내용은 [Conditions](../msbuild/msbuild-conditions.md)을 참조하십시오.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[Task](../msbuild/task-element-msbuild.md)|[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 작업의 인스턴스를 만들고 실행합니다.|  
  
## 예제  
 다음 코드 예제에서는 `Target` 요소 내에서 실행되는 `Csc` 작업을 보여 줍니다.  작업 매개 변수에 전달되는 항목과 속성은 이 예제의 범위 바깥에서 선언됩니다.  출력 매개 변수 `OutputAssembly`의 값은 `FinalAssemblyName` 항목에 저장되고, 출력 매개 변수 `BuildSucceeded`의 값은 `BuildWorked` 속성에 저장됩니다.  자세한 내용은 [작업](../msbuild/msbuild-tasks.md)을 참조하십시오.  
  
```  
<Target Name="Compile" DependsOnTargets="Resources">  
    <Csc  Sources="@(CSFile)"  
            TargetType="library"  
            Resources="@(CompiledResources)"  
            EmitDebugInformation="$(includeDebugInformation)"  
            References="@(Reference)"  
            DebugType="$(debuggingType)"  
            OutputAssembly="$(builtdir)\$(MSBuildProjectName).dll" >  
        <Output TaskParameter="OutputAssembly"  
                  ItemName="FinalAssemblyName" />  
        <Output TaskParameter="BuildSucceeded"  
                  PropertyName="BuildWorked" />  
    </Csc>  
</Target>  
```  
  
## 참고 항목  
 [Project File Schema Reference](../msbuild/msbuild-project-file-schema-reference.md)   
 [작업](../msbuild/msbuild-tasks.md)