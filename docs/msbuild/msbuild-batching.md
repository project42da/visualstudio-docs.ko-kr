---
title: "MSBuild 일괄 처리 | Microsoft Docs"
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
  - "MSBuild, 일괄 처리"
ms.assetid: d35c085b-27b8-49d7-b6f8-8f2f3a0eec38
caps.latest.revision: 9
caps.handback.revision: 9
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# MSBuild 일괄 처리
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에는 항목 목록을 항목 메타데이터에 따라 다양한 범주 또는 배치로 나눈 다음, 대상이나 작업을 각 배치와 함께 하나씩 실행하는 기능이 있습니다.  
  
## 작업 일괄 처리  
 작업 일괄 처리 방법에서는 항목 목록을 여러 개의 배치로 나누고 그러한 배치를 각각 하나씩 작업으로 전달하므로 프로젝트 파일을 단순화할 수 있습니다.  이는 프로젝트 파일은 여러 번 실행될 수 있지만 프로젝트 파일에는 작업과 해당 특성을 한 번만 선언하면 된다는 뜻입니다.  
  
 작업 특성 중 하나에 %\(*ItemMetaDataName*\) 표기법을 사용하여 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]가 작업과 함께 일괄 처리를 수행하도록 지정할 수 있습니다.  다음 예제에서는 `Example` 항목 목록을 `Color` 항목 메타데이터 값에 따라 배치로 나누고 각각의 배치를 하나씩 `MyTask` 작업으로 전달합니다.  
  
> [!NOTE]
>  작업 특성의 어떤 위치에서도 항목 목록을 참조하지 않거나 메타데이터 이름이 모호할 가능성이 있는 경우 %\(*ItemCollection.ItemMetaDataName*\) 표기법을 사용하여 일괄 처리에 사용할 항목 메타데이터 값을 정규화할 수 있습니다.  
  
```  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Example Include="Item1">  
            <Color>Blue</Color>  
        </Example>  
        <Example Include="Item2">  
            <Color>Red</Color>  
        </Example>  
    </ItemGroup>  
  
    <Target Name="RunMyTask">  
        <MyTask  
            Sources = "@(Example)"  
            Output = "%(Color)\MyFile.txt"/>  
    </Target>  
  
</Project>  
```  
  
 보다 구체적인 일괄 처리 예제는 [작업 일괄 처리의 항목 메타데이터](../msbuild/item-metadata-in-task-batching.md)를 참조하십시오.  
  
## 대상 일괄 처리  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 대상을 실행하기 전에 대상의 입력과 출력이 최신 상태인지 확인합니다.  입력과 출력 모두 최신 상태이면 대상을 건너뜁니다.  대상 내의 작업이 일괄 처리를 사용하는 경우 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]는 항목의 각 배치에 대한 입력과 출력이 최신 상태인지 확인해야 합니다.  그렇지 않으면 대상은 적중될 때마다 실행됩니다.  
  
 다음 예제에서는 %\(*ItemMetaDataName*\) 표기법을 사용한 `Outputs` 특성을 포함하는 `Target` 요소를 보여 줍니다.  [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 `Example` 항목 목록을 `Color` 항목 메타데이터에 따라 배치로 나누고 각 배치에 대해 출력 파일의 타임스탬프를 분석합니다.  배치의 출력이 최신 상태가 아니면 대상이 실행됩니다.  그렇지 않으면 대상을 건너뜁니다.  
  
```  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Example Include="Item1">  
            <Color>Blue</Color>  
        </Example>  
        <Example Include="Item2">  
            <Color>Red</Color>  
        </Example>  
    </ItemGroup>  
  
    <Target Name="RunMyTask"  
        Inputs="@(Example)"  
        Outputs="%(Color)\MyFile.txt">  
        <MyTask  
            Sources = "@(Example)"  
            Output = "%(Color)\MyFile.txt"/>  
    </Target>  
  
</Project>  
```  
  
 대상 일괄 처리의 다른 예제는 [대상 일괄 처리의 항목 메타데이터](../msbuild/item-metadata-in-target-batching.md)를 참조하십시오.  
  
## 메타데이터를 사용하는 속성 함수  
 메타데이터를 포함하는 속성 함수로 일괄 처리를 제어할 수 있습니다.  다음 예제를 참조하십시오.  
  
 `$([System.IO.Path]::Combine($(RootPath),%(Compile.Identity)))`  
  
 이 예제에서는 <xref:System.IO.Path.Combine%2A>을 사용하여 루트 폴더 경로와 컴파일 항목 경로를 결합합니다.  
  
 속성 함수는 메타데이터 값 내에 나타낼 수 없습니다.  다음 예제를 참조하십시오.  
  
 `%(Compile.FullPath.Substring(0,3))`  
  
 이 예제는 허용되지 않습니다.  
  
 속성 함수에 대한 자세한 내용은 [속성 함수](../msbuild/property-functions.md)를 참조하십시오.  
  
## 참고 항목  
 [ItemMetadata Element \(MSBuild\)](../msbuild/itemmetadata-element-msbuild.md)   
 [MSBuild 개념](../msbuild/msbuild-concepts.md)   
 [MSBuild Reference](../msbuild/msbuild-reference.md)   
 [고급 개념](../msbuild/msbuild-advanced-concepts.md)