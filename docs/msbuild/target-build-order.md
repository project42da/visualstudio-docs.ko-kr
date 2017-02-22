---
title: "대상 빌드 순서 | Microsoft Docs"
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
  - "msbuild, 빌드 순서"
ms.assetid: f4a26339-9f9a-497a-9aa6-0797183d450d
caps.latest.revision: 18
caps.handback.revision: 18
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 대상 빌드 순서
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

한 대상에 대한 입력이 다른 대상 출력에 따라 다른 경우 대상의 순서를 지정해야 합니다.  으로 대상 실행 순서를 지정 하려면이 특성을 사용할 수 있습니다.  
  
-   `InitialTargets`.  이 `Project` 특성 대상 또는 명령줄에 지정 된 경우에 먼저 실행 하는 대상 지정 된 `DefaultTargets` 특성.  
  
-   `DefaultTargets`.  이 `Project` 특성이 지정 하는 대상 실행 대상 명령줄에 명시적으로 지정 되지 않은 경우.  
  
-   `DependsOnTargets`.  이 `Target` 특성이이 대상을 실행 하기 전에 실행 해야 하는 대상을 지정 합니다.  
  
-   `BeforeTargets`과\(와\) `AfterTargets`입니다.  이러한 `Target` 특성 지정이 대상 이전 또는 이후에 지정 된 대상 \(MSBuild 4.0\)를 실행 해야 합니다.  
  
 대상은 빌드 내의 후속 대상이 해당 대상에 종속되는 경우에도 빌드 과정에서 두 번 이상 실행되지 않습니다.  대상이 실행되면 더 이상 빌드에 영향을 주지 않습니다.  
  
 대상에 `Condition` 특성이 포함될 수 있습니다.  지정 된 조건이 있는 경우 `false`를 실행 하지 않으면 대상과 빌드에는 영향을 주지 않습니다.  조건에 대한 자세한 내용은 [Conditions](../msbuild/msbuild-conditions.md)을 참조하십시오.  
  
## 초기 대상  
 `InitialTargets` 특성의  [프로젝트](../msbuild/project-element-msbuild.md) 요소 대상 또는 명령줄에 지정 된 경우에 먼저 실행 하는 대상 지정은 `DefaultTargets` 특성.  초기 대상은 일반적으로 오류 검사에 사용됩니다.  
  
 값은 `InitialTargets` 특성 대상 세미콜론으로 구분 된, 순서가 지정 된 목록이 될 수 있습니다.  다음 예제는 `Warm` 대상 실행 다음의 `Eject` 대상 실행.  
  
```  
<Project InitialTargets="Warm;Eject" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
```  
  
 가져온 프로젝트에는 자체 `InitialTargets` 특성이 포함될 수 있습니다.  모든 초기 대상이 함께 집계되고 순서대로 실행됩니다.  
  
 자세한 내용은 [방법: 먼저 빌드할 대상 지정](../msbuild/how-to-specify-which-target-to-build-first.md)을 참조하십시오.  
  
## 기본 대상  
 `DefaultTargets` 특성은  [프로젝트](../msbuild/project-element-msbuild.md) 요소 지정 대상을 빌드 대상 명령줄에 명시적으로 지정 하지 않을 경우.  
  
 값은 `DefaultTargets` 특성에 기본 대상 세미콜론으로 구분 된, 순서가 지정 된 목록이 될 수 있습니다.  다음 예제는 `Clean` 대상 실행 다음의 `Build` 대상 실행.  
  
```  
<Project DefaultTargets="Clean;Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
```  
  
 기본 대상을 사용 하 여 재정의할 수 있는 **\/target** 명령줄에 전환 합니다.  다음 예제는 `Build` 대상 실행 다음의 `Report` 대상 실행.  대상이 이러한 방식으로 지정 하면 기본 대상이 무시 됩니다.  
  
 `msbuild /target:Build;Report`  
  
 초기 대상과 기본 대상이 지정 되 고 명령줄 대상이 지정 되지 않은 경우 MSBuild 먼저 초기 대상을 실행 하 고 기본 대상을 실행 합니다.  
  
 가져온 프로젝트에는 자체 `DefaultTargets` 특성이 포함될 수 있습니다.  발견된 첫 번째 `DefaultTargets` 특성은 실행할 기본 대상을 지정합니다.  
  
 자세한 내용은 [방법: 먼저 빌드할 대상 지정](../msbuild/how-to-specify-which-target-to-build-first.md)을 참조하십시오.  
  
## 첫 번째 대상  
 초기 대상, 기본 대상 또는 명령줄 대상이 없는 경우 MSBuild에서는 프로젝트 파일 또는 가져온 프로젝트 파일에서 처음 발견한 대상을 실행합니다.  
  
## 대상 종속성  
 대상은 서로 간의 종속성 관계를 설명할 수 있습니다.  `DependsOnTargets` 특성은 대상이 다른 대상에 종속됨을 나타냅니다.  다음 예제를 참조하십시오.  
  
```  
<Target Name="Serve" DependsOnTargets="Chop;Cook" />  
```  
  
 Msbuild에 지시 된 `Serve` 대상에 따라 달라 집니다를 `Chop` 대상 및 `Cook` 대상.  Msbuild를 실행은 `Chop` 대상 및 실행은 `Cook` 실행 하기 전에 대상의 `Serve` 대상.  
  
## 대상 대상 전 후  
 MSBuild 4.0에서는 `BeforeTargets` 및 `AfterTargets` 특성을 사용하여 대상 순서를 지정할 수 있습니다.  
  
 다음 스크립트를 살펴보십시오.  
  
```  
<Project DefaultTargets="Compile;Link" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="Compile">  
        <Message Text="Compiling" />  
    </Target>  
    <Target Name="Link">  
        <Message Text="Linking" />  
    </Target>  
</Project>  
```  
  
 중간 대상으로 만드는 데 `Optimize` 이후에 실행은 `Compile` 하기 전에 대상의 `Link` 대상, 다음과 같은 대상 위치에 추가 `Project` 요소.  
  
```  
<Target Name="Optimize"   
    AfterTargets="Compile" BeforeTargets="Link">  
    <Message Text="Optimizing" />  
</Target>  
```  
  
## 대상 빌드 순서 지정  
 MSBuild에서는 다음과 같이 대상 빌드 순서를 지정합니다.  
  
1.  `InitialTargets`대상이 실행 됩니다.  
  
2.  **\/target** 스위치에 의해 명령줄에 지정된 대상이 실행됩니다.  명령줄에 대상을 지정 하는 경우는 `DefaultTargets` 대상을 실행 합니다.  다음 둘 다 있는 경우 처음 발견 된 대상이 실행 됩니다.  
  
3.  대상의 `Condition` 특성이 계산됩니다.  경우는 `Condition` 특성이 있고 계산 `false`를 실행 하지 않으면 대상과 빌드에 더 이상 효과가 없습니다.  
  
4.  대상을 실행하기 전에 해당 `DependsOnTargets` 대상이 실행됩니다.  
  
5.  대상을 실행하기 전에 `BeforeTargets` 특성에 대상을 나열하는 대상이 실행됩니다.  
  
6.  대상을 실행하기 전에 해당 `Inputs` 특성과 `Outputs` 특성이 비교됩니다.  출력 파일이 해당 입력된 파일 또는 파일을 기준으로 만료 된 MSBuild 판단 하는 경우 Msbuild는 대상을 실행 합니다.  그렇지 않으면 대상을 건너뜁니다.  
  
7.  대상을 실행하거나 건너뛰고 나면 `AfterTargets` 특성에 대상을 나열하는 대상이 실행됩니다.  
  
## 참고 항목  
 [대상](../msbuild/msbuild-targets.md)