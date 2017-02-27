---
title: "ItemGroup 요소(MSBuild) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#ItemGroup"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "ItemGroup 요소[MSBuild]"
  - "<ItemGroup> 요소[MSBuild]"
ms.assetid: aac894e3-a9f1-4bbc-a796-6ef07001f35b
caps.latest.revision: 24
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 24
---
# ItemGroup 요소(MSBuild)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

사용자 정의 [Item](../msbuild/item-element-msbuild.md) 요소 집합이 들어 있습니다.  [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트에 사용되는 모든 항목은 `ItemGroup` 요소의 자식으로 지정해야 합니다.  
  
## 구문  
  
```  
<ItemGroup Condition="'String A' == 'String B'">  
    <Item1>... </Item1>  
    <Item2>... </Item2>  
</ItemGroup>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`Condition`|선택적 특성입니다.  확인할 조건입니다.  자세한 내용은 [Conditions](../msbuild/msbuild-conditions.md)을 참조하십시오.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[항목](../msbuild/item-element-msbuild.md)|빌드 프로세스의 입력을 정의합니다.  `ItemGroup`에는 `Item` 요소가 0개 이상 있을 수 있습니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[프로젝트](../msbuild/project-element-msbuild.md)|[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트 파일의 필수 루트 요소입니다.|  
|[대상](../msbuild/target-element-msbuild.md)|.NET Framework 3.5부터는 `ItemGroup` 요소가 `Target` 요소 내부에 나타날 수 있습니다.  자세한 내용은 [대상](../msbuild/msbuild-targets.md)을 참조하십시오.|  
  
## 설명  
  
## 예제  
 다음 코드 예제에서는 `ItemGroup` 요소 안에 선언된 사용자 정의 항목 컬렉션 `Res` 및 `CodeFiles`를 보여 줍니다.  `Res` 항목 컬렉션의 각 항목에는 사용자 정의된 자식 [ItemMetadata](../msbuild/itemmetadata-element-msbuild.md) 요소가 들어 있습니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Res Include = "Strings.fr.resources" >  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include = "Dialogs.fr.resources" >  
            <Culture>fr</Culture>  
        </Res>  
  
        <CodeFiles Include="**\*.cs" Exclude="**\generated\*.cs" />  
        <CodeFiles Include="..\..\Resources\Constants.cs" />  
    </ItemGroup>  
...  
</Project>  
```  
  
## 참고 항목  
 [Project File Schema Reference](../msbuild/msbuild-project-file-schema-reference.md)   
 [항목](../msbuild/msbuild-items.md)   
 [Common MSBuild Project Items](../msbuild/common-msbuild-project-items.md)