---
title: "Target 요소(MSBuild) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#Target"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Target 요소[MSBuild]"
  - "<Target> 요소[MSBuild]"
ms.assetid: 350f6fc2-86b3-45f2-a31e-ece0e6bd4dca
caps.latest.revision: 34
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 34
---
# Target 요소(MSBuild)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

순차적으로 실행할 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]의 작업 집합이 들어 있습니다.  
  
## 구문  
  
```  
<Target Name="Target Name"  
        Inputs="Inputs"  
        Outputs="Outputs"  
        Returns="Returns"  
        KeepDuplicateOutputs="true/false"  
        BeforeTargets="Targets"  
        AfterTargets="Targets"  
        DependsOnTargets="DependentTarget"  
        Condition="'String A' == 'String B'">  
        Label="Label">  
    <Task>... </Task>  
    <PropertyGroup>… </PropertyGroup>  
    <ItemGroup>… </ItemGroup>  
    <OnError... />  
</Target>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`Name`|필수 특성입니다.<br /><br /> 대상의 이름.|  
|`Condition`|선택적 특성입니다.<br /><br /> 확인할 조건입니다.  조건이 `false`로 확인되면 `DependsOnTargets` 특성에 설정된 대상이나 대상의 본문이 작업에서 실행되지 않습니다.  조건에 대한 자세한 내용은 [Conditions](../msbuild/msbuild-conditions.md)을 참조하십시오.|  
|`Inputs`|선택적 특성입니다.<br /><br /> 입력이이 대상에 작업을 구성 하는 파일입니다.  여러 파일을 세미콜론으로 구분 합니다.  파일의 타임 스탬프를 비교 하 여 파일의 타임 스탬프와 있습니다 `Outputs` 확인 하려면 여부는 `Target` 최신 버전입니다.  자세한 내용은 [증분 빌드](../msbuild/incremental-builds.md), [방법: 증분 빌드](../msbuild/how-to-build-incrementally.md) 및 [변환](../msbuild/msbuild-transforms.md)을 참조하십시오.|  
|`Outputs`|선택적 특성입니다.<br /><br /> 이 대상에 작업 폼을 출력 하는 파일입니다.  여러 파일을 세미콜론으로 구분 합니다.  파일의 타임 스탬프를 비교 하 여 파일의 타임 스탬프와 있습니다 `Inputs` 확인 하려면 여부는 `Target` 최신 버전입니다.  자세한 내용은 [증분 빌드](../msbuild/incremental-builds.md), [방법: 증분 빌드](../msbuild/how-to-build-incrementally.md) 및 [변환](../msbuild/msbuild-transforms.md)을 참조하십시오.|  
|`Returns`|선택적 특성입니다.<br /><br /> 이 대상을 호출하는 작업\(예: MSBuild 작업\)에 사용할 수 있게 될 항목의 집합입니다.  대상이 여러 개인 경우 세미콜론으로 구분할 수 있습니다.  에 대상 파일의 경우 `Returns` 특성, 출력 특성이이 목적을 위해 대신 사용 합니다.|  
|`KeepDuplicateOutputs`|선택적 부울 특성입니다.<br /><br /> 경우 `true`, 여러 참조 대상의 반환에 있는 같은 항목에 기록 됩니다.  기본적으로 이 특성은 `false`입니다.|  
|`BeforeTargets`|선택적 특성입니다.<br /><br /> 대상 이름을 세미콜론으로 구분한 목록입니다. 이 대상을 지정 된 대상 또는 대상 전에 실행 되도록 지정 하는 경우를 나타냅니다.  이 프로젝트 작성자가 직접 수정 하지 않고도 기존 대상 집합을 확장할 수 있습니다.  자세한 내용은 [대상 빌드 순서](../msbuild/target-build-order.md)을 참조하십시오.|  
|`AfterTargets`|선택적 특성입니다.<br /><br /> 대상 이름을 세미콜론으로 구분한 목록입니다.  이 대상을 지정 된 대상 또는 대상 후 실행 되도록 지정 하는 경우를 나타냅니다.  이 프로젝트 작성자가 직접 수정 하지 않고도 기존 대상 집합을 확장할 수 있습니다.  자세한 내용은 [대상 빌드 순서](../msbuild/target-build-order.md)을 참조하십시오.|  
|`DependsOnTargets`|선택적 특성입니다.<br /><br /> 이 대상을 실행하거나 최상위 종속성 분석을 수행하기 전에 실행해야 할 대상입니다.  대상이 여러 개인 경우 세미콜론으로 구분할 수 있습니다.|  
|`Label`|선택적 특성입니다.<br /><br /> 시스템 및 사용자 요소를 주문 하거나 식별 하는 식별자입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[Task](../msbuild/task-element-msbuild.md)|[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 작업의 인스턴스를 만들고 실행합니다.  대상에 작업이 0개 이상 있을 수 있습니다.|  
|[PropertyGroup](../msbuild/propertygroup-element-msbuild.md)|사용자 정의 집합이 들어 `Property` 요소.  .NET Framework 3.5에서 시작 하는 `Target` 요소가 포함 될 수 있습니다 `PropertyGroup` 요소.|  
|[ItemGroup](../msbuild/itemgroup-element-msbuild.md)|사용자 정의 집합이 들어 `Item` 요소.  .NET Framework 3.5에서 시작 하는 `Target` 요소가 포함 될 수 있습니다 `ItemGroup` 요소.  자세한 내용은 [항목](../msbuild/msbuild-items.md)을 참조하십시오.|  
|[OnError](../msbuild/onerror-element-msbuild.md)|경우 실행할 하나 이상의 대상에 게는 `ContinueOnError` 특성은 ErrorAndStop \(또는 `false`\) 실패 한 작업에 대 한.  대상에 `OnError` 요소가 0개 이상 있을 수 있습니다.  `OnError` 요소가 있는 경우 이 요소는 `Target` 요소의 마지막 요소여야 합니다.<br /><br /> 대 한 자세한 내용은 `ContinueOnError` 특성을 참조 하십시오 [Task Element \(MSBuild\)](../msbuild/task-element-msbuild.md).|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[프로젝트](../msbuild/project-element-msbuild.md)|[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트 파일의 필수 루트 요소입니다.|  
  
## 설명  
 실행할 첫 번째 대상은 런타임에 지정됩니다.  대상은 다른 대상에 종속될 수 있습니다.  예를 들어, 배포 대상은 컴파일 대상에 종속될 수 있습니다.  [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 엔진에서는 `DependsOnTargets` 특성에 나타나는 순서에 따라 왼쪽에서 오른쪽으로 종속 항목을 실행합니다.  자세한 내용은 [대상](../msbuild/msbuild-targets.md)을 참조하십시오.  
  
 여러 대상이 종속되어 있더라도 한 대상은 빌드 과정에서 한 번만 실행할 수 있습니다.  
  
 `Condition` 특성이 `false`로 확인되어 대상이 생략되더라도, 나중에 빌드에서 이 대상이 호출되었을 때 `Condition` 특성이 `true`로 확인되면 대상이 실행될 수 있습니다.  
  
 MSBuild 4 이전에는 `Target`이 `Outputs` 특성에 지정된 모든 항목을 반환했습니다.  그러려면 나중에 빌드의 작업이 이러한 항목을 요청하는 경우에 대비하여 MSBuild에서 이러한 항목을 기록해야 합니다.  호출자에게 필요한 출력을 어느 대상이 갖고 있는지 나타낼 수 있는 방법이 없으므로 MSBuild는 모든 `Outputs`의 모든 항목을 호출된 모든 `Target`에 누적합니다.  이는 출력 항목이 많은 빌드에 배율 문제를 일으킵니다.  
  
 사용자가 프로젝트에서 임의의 `Target`에 `Returns`를 지정하면 `Returns` 특성이 있는 `Target`만 해당 항목을 기록합니다.  
  
 `Target`에 `Outputs` 속성과 `Returns` 속성 둘 다를 포함할 수 있습니다.  대상이 최신인지 확인하기 위해 `Outputs`가 `Inputs`와 함께 사용됩니다.  `Returns`\(있는 경우\)가 `Outputs`의 값을 재정의하여 어느 항목이 호출자에게 반환되었는지를 확인합니다.  `Returns`가 없으면 위에 설명된 경우를 제외하고 호출자가 `Outputs`를 사용할 수 있게 됩니다.  
  
 MSBuild 4 이전에는 `Target`이 같은 항목에 대한 복수 참조를 `Outputs`에 포함할 때마다 해당 중복 항목이 기록되었습니다.  출력 수가 많고 프로젝트 간 종속성이 많은 매우 큰 빌드에서는 중복 항목이 소용이 없으므로 많은 양의 메모리가 낭비될 수 있습니다.  경우는 `KeepDuplicateOutputs` 특성을 설정 `true`, 이러한 중복 기록 됩니다.  
  
## 예제  
 다음 코드 예제에서는 `Csc` 작업을 실행하는 `Target` 요소를 보여 줍니다.  
  
```  
<Target Name="Compile" DependsOnTargets="Resources" Returns="$(TargetPath)">  
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
 [대상](../msbuild/msbuild-targets.md)   
 [Project File Schema Reference](../msbuild/msbuild-project-file-schema-reference.md)