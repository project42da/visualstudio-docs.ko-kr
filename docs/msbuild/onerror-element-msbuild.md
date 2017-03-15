---
title: "OnError Element (MSBuild) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#OnError"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "OnError Element [MSBuild]"
  - "<OnError Element [MSBuild]"
ms.assetid: 765767d3-ecb7-4cd9-ba1e-d9468964dddc
caps.latest.revision: 14
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# OnError Element (MSBuild)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

실패한 작업에 대해 `ContinueOnError` 특성이 `false`인 경우 하나 이상의 대상이 실행되도록 합니다.  
  
## 구문  
  
```  
<OnError ExecuteTargets="TargetName"  
    Condition="'String A'=='String B'" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`Condition`|선택적 특성입니다.<br /><br /> 확인할 조건입니다.  자세한 내용은 [Conditions](../msbuild/msbuild-conditions.md)을 참조하십시오.|  
|`ExecuteTargets`|필수 특성입니다.<br /><br /> 작업이 실패하는 경우 실행할 대상입니다.  대상이 여러 개이면 세미콜론으로 구분합니다.  여러 대상은 지정 순서대로 실행됩니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[대상](../msbuild/target-element-msbuild.md)|[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 작업에 대한 컨테이너 요소입니다.|  
  
## 설명  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]실행은 `OnError` 요소 중 하나의 `Target` 요소의 작업 실패 한다는 `ContinueOnError` 특성을 설정 `ErrorAndStop` \(또는 `false`\).  작업에 실패하면 `ExecuteTargets` 특성에서 지정한 대상이 실행됩니다.  대상의 `OnError` 요소가 하나 이상인 경우 작업에 실패하면 `OnError` 요소가 순차적으로 실행됩니다.  
  
 에 대 한 정보는 `ContinueOnError` 특성을 참조 하십시오 [Task Element \(MSBuild\)](../msbuild/task-element-msbuild.md).  대상에 대 한 내용은 [대상](../msbuild/msbuild-targets.md).  
  
## 예제  
 다음 코드에서는 `TaskOne` 및 `TaskTwo` 작업을 실행합니다.  `TaskOne`에 실패하면 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서 `OnError` 요소를 확인하고 `OtherTarget` 대상을 실행합니다.  
  
```  
<Target Name="ThisTarget">  
    <TaskOne ContinueOnError="ErrorAndStop">  
    </TaskOne>  
    <TaskTwo>  
    </TaskTwo>  
    <OnError ExecuteTargets="OtherTarget" />  
</Target>  
```  
  
## 참고 항목  
 [Project File Schema Reference](../msbuild/msbuild-project-file-schema-reference.md)   
 [대상](../msbuild/msbuild-targets.md)