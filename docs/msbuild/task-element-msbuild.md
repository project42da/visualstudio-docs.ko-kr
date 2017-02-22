---
title: "Task Element (MSBuild) | Microsoft Docs"
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
  - "Task element [MSBuild]"
  - "<Task> element [MSBuild]"
ms.assetid: d82e2485-e5f0-4936-a357-745bacccc299
caps.latest.revision: 22
caps.handback.revision: 22
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Task Element (MSBuild)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 작업의 인스턴스를 만들고 실행합니다.  요소 이름은 작성하려는 작업의 이름에 따라 결정됩니다.  
  
## 구문  
  
```  
<Task Parameter1="Value1"... ParameterN="ValueN"  
    ContinueOnError="WarnAndContinue/true/ErrorAndContinue/ErrorAndStop/false"  
    Condition="'String A' == 'String B'" >  
    <Output... />  
</Task>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`Condition`|선택적 특성입니다.  확인할 조건입니다.  자세한 내용은 [Conditions](../msbuild/msbuild-conditions.md)을 참조하십시오.|  
|`ContinueOnError`|선택적 특성입니다.  다음 값 중 하나가 포함 될 수 있습니다.<br /><br /> -   **WarnAndContinue** 또는  **true**.  작업이 실패할 경우, 후속 작업에서의  [대상](../msbuild/target-element-msbuild.md) 요소와 빌드를 계속 실행 하 고 작업의 모든 오류가 경고로 처리 됩니다.<br />-   **ErrorAndContinue**.  작업이 실패할 경우, 후속 작업에는 `Target` 요소와 빌드를 계속 실행 하 고 작업의 모든 오류를 오류로 처리 합니다.<br />-   **ErrorAndStop** 또는  **false** \(기본값\).  작업이 실패할 경우, 나머지 작업을는 `Target` 되지 않는 요소 및 빌드 실행 및 전체 `Target` 요소와 빌드는 실패 한 것으로 간주 합니다.<br /><br /> 버전 4.5 에서만 지원 하기 전에.NET Framework `true` 및 `false` 값입니다.<br /><br /> 자세한 내용은 [방법: 작업의 오류 무시](../Topic/How%20to:%20Ignore%20Errors%20in%20Tasks.md)을 참조하십시오.|  
|`Parameter`|`[Required]` 특성으로 레이블이 설정된 속성이 작업 클래스에 하나 이상 들어 있는 경우 필수적 요소입니다.<br /><br /> 매개 변수 값을 해당 값으로 포함하는 사용자 정의 작업 매개 변수입니다.  `Task` 요소에 포함되는 매개 변수의 수에는 제한이 없으며 각 특성은 작업 클래스의 .NET 속성에 매핑됩니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[Output](../msbuild/output-element-msbuild.md)|작업의 출력을 프로젝트 파일에 저장합니다.  작업에 `Output` 요소가 0개 이상 있을 수 있습니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[대상](../msbuild/target-element-msbuild.md)|[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 작업에 대한 컨테이너 요소입니다.|  
  
## 설명  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트 파일의 `Task` 요소는 작업의 인스턴스를 만들고, 속성을 설정하고, 이를 실행합니다.  `Output` 요소는 프로젝트 파일의 다른 곳에 사용할 속성이나 항목에 출력 매개 변수를 저장합니다.  
  
 작업의 부모 `Target` 요소에 [OnError](../msbuild/onerror-element-msbuild.md) 요소가 있으면 작업이 실패하고 `ContinueOnError`의 값이 `false`이더라도 이러한 요소를 확인합니다.  작업에 대한 자세한 내용은 [작업](../msbuild/msbuild-tasks.md)을 참조하십시오.  
  
## 예제  
 다음 코드 예제에서는 [Csc task](../msbuild/csc-task.md) 클래스의 인스턴스를 만들고 여섯 가지 속성을 설정하고 작업을 실행합니다.  작업을 실행한 후에 개체의 `OutputAssembly` 속성 값이 `FinalAssemblyName`이라는 항목 목록에 배치됩니다.  
  
```  
<Target Name="Compile" DependsOnTarget="Resources" >  
    <Csc Sources="@(CSFile)"  
          TargetType="library"  
          Resources="@(CompiledResources)"  
          EmitDebugInformation="$(includeDebugInformation)"  
          References="@(Reference)"  
          DebugType="$(debuggingType)" >  
        <Output TaskParameter="OutputAssembly"  
                  ItemName="FinalAssemblyName" />  
    </Csc>  
</Target>  
```  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [Project File Schema Reference](../msbuild/msbuild-project-file-schema-reference.md)