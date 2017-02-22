---
title: "대상 일괄 처리의 항목 메타데이터 | Microsoft Docs"
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
  - "일괄 처리[MSBuild]"
  - "MSBuild, 대상 일괄 처리"
  - "대상 일괄 처리[MSBuild]"
ms.assetid: f3cc4186-6a4c-4161-bbe5-1ec638b4925b
caps.latest.revision: 6
caps.handback.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 대상 일괄 처리의 항목 메타데이터
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에는 빌드 대상의 입력과 출력에 대해 종속성 분석을 수행하는 기능이 있습니다.  대상의 입력이나 출력이 최신 상태로 확인되면 해당 대상을 건너뛰고 빌드가 계속됩니다.  `Target` 요소는 `Inputs` 및 `Outputs` 특성을 사용하여 종속성 분석 중에 검사할 항목을 지정합니다.  
  
 일괄 처리되는 항목을 입력이나 출력으로 사용하는 작업이 대상에 포함되어 있으면 대상의 `Target` 요소는 해당 `Inputs` 또는 `Outputs` 특성에 일괄 처리를 사용하여 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]가 이미 최신 상태인 항목의 일괄 처리를 건너뛸 수 있도록 해야 합니다.  
  
## 대상 일괄 처리  
 다음 예제에는 `Culture` 항목 메타데이터에 따라 두 개의 배치로 나뉘는 `Res` 항목 목록이 포함되어 있습니다.  이러한 일괄 처리는 각 일괄 처리에 대해 출력 어셈블리를 만드는 `AL` 작업으로 하나씩 전달됩니다.  `Target` 요소의 `Outputs` 특성에 대해 일괄 처리를 사용하여 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 대상을 실행하기 전에 개별 일괄 처리가 각각 최신 상태인지 여부를 확인할 수 있습니다.  대상 일괄 처리를 사용하지 않으면 항목의 두 일괄 처리는 모두 대상이 실행될 때마다 작업에 의해 실행됩니다.  
  
```  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Res Include="Strings.fr.resources">  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include="Strings.jp.resources">  
            <Culture>jp</Culture>  
        </Res>  
        <Res Include="Menus.fr.resources">  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include="Dialogs.fr.resources">  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include="Dialogs.jp.resources">  
            <Culture>jp</Culture>  
        </Res>  
        <Res Include="Menus.jp.resources">  
            <Culture>jp</Culture>  
        </Res>  
    </ItemGroup>  
  
    <Target Name="Build"  
        Inputs="@(Res)"  
        Outputs="%(Culture)\MyApp.resources.dll">  
  
        <AL Resources="@(Res)"  
            TargetType="library"  
            OutputAssembly="%(Culture)\MyApp.resources.dll"  
  
    </Target>  
  
</Project>  
```  
  
## 참고 항목  
 [방법: 증분 빌드](../msbuild/how-to-build-incrementally.md)   
 [일괄 처리](../msbuild/msbuild-batching.md)   
 [Target 요소\(MSBuild\)](../msbuild/target-element-msbuild.md)   
 [작업 일괄 처리의 항목 메타데이터](../msbuild/item-metadata-in-task-batching.md)