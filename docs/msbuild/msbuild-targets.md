---
title: "MSBuild 대상 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSBuild, 대상"
ms.assetid: 8060b4d2-e4a9-48cf-a437-852649ceb417
caps.latest.revision: 26
caps.handback.revision: 26
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# MSBuild 대상
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

대상은 작업을 특정한 순서로 그룹화하며 빌드 프로세스를 더 작은 단위로 구성할 수 있도록 합니다.  예를 들어, 한 대상에서 출력 디렉터리의 모든 파일을 삭제하여 빌드를 준비하는 동안 다른 대상에서는 프로젝트의 입력을 컴파일한 다음 빈 디렉터리에 넣을 수 있습니다.  작업에 대한 자세한 내용은 [작업](../msbuild/msbuild-tasks.md)을 참조하십시오.  
  
## 프로젝트 파일에서 대상 선언  
 [Target](../msbuild/target-element-msbuild.md) 요소를 사용하여 프로젝트 파일에 대상을 선언합니다.  예를 들어, 다음 XML은 Construct라는 대상을 만들며, 이 대상은 Compile 항목 형식을 사용하여 Csc 작업을 호출합니다.  
  
```  
<Target Name="Construct">  
    <Csc Sources="@(Compile)" />  
</Target>  
```  
  
 MSBuild 속성과 마찬가지로 대상도 다시 정의할 수 있습니다.  다음 예제를 참조하십시오.  
  
```  
<Target Name="AfterBuild" >  
    <Message Text="First occurrence" />  
</Target>  
<Target Name="AfterBuild" >  
    <Message Text="Second occurrence" />  
</Target>  
```  
  
 AfterBuild가 실행되면 "Second occurrence"만 표시됩니다.  
  
## 대상 빌드 순서  
 한 대상에 대한 입력이 다른 대상 출력에 따라 다른 경우 대상의 순서를 지정해야 합니다.  다음과 같은 여러 가지 방법으로 대상 실행 순서를 지정할 수 있습니다.  
  
-   초기 대상  
  
-   기본 대상  
  
-   첫 번째 대상  
  
-   대상 종속성  
  
-   `BeforeTargets` 및 `AfterTargets`\(MSBuild 4.0\)  
  
 대상은 빌드 내의 후속 대상이 해당 대상에 종속되는 경우에도 한 번의 빌드 과정에서 두 번 실행되지 않습니다.  대상이 실행되면 더 이상 빌드에 영향을 주지 않습니다.  
  
 대상 빌드 순서에 대한 자세한 내용은 [대상 빌드 순서](../msbuild/target-build-order.md)를 참조하십시오.  
  
## 대상 일괄 처리  
 대상 요소에 %\(Metadata\) 형식으로 메타데이터를 지정하는 `Outputs` 특성이 있을 수 있습니다.  이 경우 MSBuild는 해당 메타데이터 값이 있는 항목들을 그룹화하거나 "일괄 처리"함으로써 각 메타데이터 값에 대해 대상을 한 번만 실행합니다.  다음 예제를 참조하십시오.  
  
```  
<ItemGroup>  
    <Reference Include="System.Core">  
      <RequiredTargetFramework>3.5</RequiredTargetFramework>  
    </Reference>  
    <Reference Include="System.Xml.Linq">  
      <RequiredTargetFramework>3.5</RequiredTargetFramework>  
    </Reference>  
    <Reference Include="Microsoft.CSharp">  
      <RequiredTargetFramework>4.0</RequiredTargetFramework>  
    </Reference>  
</ItemGroup>  
<Target Name="AfterBuild"  
    Outputs="%(Reference.RequiredTargetFramework)">  
    <Message Text="Reference:  
      @(Reference->'%(RequiredTargetFramework)')" />  
</Target>  
```  
  
 이 예제에서는 RequiredTargetFramework 메타데이터를 기준으로 Reference 항목을 일괄 처리합니다.  대상의 출력은 다음과 같습니다.  
  
```  
Reference: 3.5;3.5  
Reference: 4.0  
  
```  
  
 실제 빌드에서 대상 일괄 처리가 수행되는 경우는 드물며,  대개는 작업 일괄 처리가 수행됩니다.  자세한 내용은 [일괄 처리](../msbuild/msbuild-batching.md)을 참조하십시오.  
  
## 증분 빌드  
 증분 빌드는 해당 입력 파일과 비교했을 때 최신 상태인 출력 파일이 있는 대상은 실행되지 않도록 최적화된 빌드입니다.  대상 요소에는 대상이 입력으로 예상하는 항목을 나타내는 `Inputs` 특성과 대상이 출력으로 생성하는 항목을 나타내는 `Outputs` 특성이 모두 포함될 수 있습니다.  
  
 출력 항목이 모두 최신 상태이면 MSBuild가 대상을 건너뛰므로 빌드 속도가 크게 향상됩니다.  이를 대상 증분 빌드라고 합니다.  일부 파일만 최신 상태이면 MSBuild는 최신 항목을 제외하고 대상을 실행하는데  이를 대상 부분 증분 빌드라고 합니다.  자세한 내용은 [증분 빌드](../msbuild/incremental-builds.md)을 참조하십시오.  
  
## 참고 항목  
 [MSBuild 개념](../msbuild/msbuild-concepts.md)   
 [방법: 여러 프로젝트 파일에서 동일한 대상 사용](../Topic/How%20to:%20Use%20the%20Same%20Target%20in%20Multiple%20Project%20Files.md)