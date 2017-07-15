---
title: "ItemGroup 요소(MSBuild) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ItemGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ItemGroup element [MSBuild]
- <ItemGroup> element [MSBuild]
ms.assetid: aac894e3-a9f1-4bbc-a796-6ef07001f35b
caps.latest.revision: 24
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 38c6099f912424d21df2aeea4cfdd0401ba57465
ms.openlocfilehash: e63c0dd4e201ef83f84f01148aacd4458806103d
ms.contentlocale: ko-kr
ms.lasthandoff: 07/14/2017

---
# ItemGroup 요소(MSBuild)
<a id="itemgroup-element-msbuild" class="xliff"></a>
사용자 정의 [Item](../msbuild/item-element-msbuild.md) 요소 집합을 포함합니다. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트에서 사용되는 모든 항목은 `ItemGroup` 요소의 자식으로 지정해야 합니다.  
  
 \<Project>  
 \<ItemGroup>  
  
## 구문
<a id="syntax" class="xliff"></a>  
  
```xml  
<ItemGroup Condition="'String A' == 'String B'">  
    <Item1>... </Item1>  
    <Item2>... </Item2>  
</ItemGroup>  
```  
  
## 특성 및 요소
<a id="attributes-and-elements" class="xliff"></a>  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성
<a id="attributes" class="xliff"></a>  
  
|특성|설명|  
|---------------|-----------------|  
|`Condition`|선택적 특성입니다. 평가할 조건입니다. 자세한 내용은 [조건](../msbuild/msbuild-conditions.md)을 참조하세요.|  
  
### 자식 요소
<a id="child-elements" class="xliff"></a>  
  
|요소|설명|  
|-------------|-----------------|  
|[Item](../msbuild/item-element-msbuild.md)|빌드 프로세스에 대한 입력을 정의합니다. `ItemGroup`에는 0개 이상의 `Item` 요소가 있을 수 있습니다.|  
  
### 부모 요소
<a id="parent-elements" class="xliff"></a>  
  
|요소|설명|  
|-------------|-----------------|  
|[프로젝트](../msbuild/project-element-msbuild.md)|[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트 파일의 필수 루트 요소입니다.|  
|[Target](../msbuild/target-element-msbuild.md)|.NET Framework 3.5부터 `ItemGroup` 요소는 `Target` 요소 내에 표시될 수 있습니다. 자세한 내용은 [대상](../msbuild/msbuild-targets.md)을 참조하세요.|  
  
## 설명
<a id="remarks" class="xliff"></a>  
  
## 예제
<a id="example" class="xliff"></a>  
 다음 코드 예제에서는 사용자 정의 항목 컬렉션 `Res` 및 `ItemGroup` 요소 내에 선언된 `CodeFiles`를 보여 줍니다. `Res` 항목 컬렉션의 각 항목은 사용자 정의 자식 [ItemMetadata](../msbuild/itemmetadata-element-msbuild.md) 요소를 포함합니다.  
  
```xml  
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
<a id="see-also" class="xliff"></a>  
 [프로젝트 파일 스키마 참조](../msbuild/msbuild-project-file-schema-reference.md)   
 [항목](../msbuild/msbuild-items.md)   
 [일반적인 MSBuild 프로젝트 항목](../msbuild/common-msbuild-project-items.md)
