---
title: "ItemDefinitionGroup Element (MSBuild) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/developer/msbuild/2003#ItemDefinitionGroup"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "ItemDefinitionGroup Element [MSBuild]"
  - "<ItemDefinitionGroup> Element [MSBuild]"
ms.assetid: 4e9fb04b-5148-4ae5-a394-42861dd62371
caps.latest.revision: 5
caps.handback.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# ItemDefinitionGroup Element (MSBuild)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`ItemDefinitionGroup` 요소를 사용하면 기본적으로 프로젝트의 모든 항목에 적용되는 메타데이터 값인 항목 정의 집합을 정의할 수 있습니다.  ItemDefinitionGroup을 사용하면 [CreateItem Task](../msbuild/createitem-task.md) 및 [CreateProperty Task](../msbuild/createproperty-task.md)을 사용하지 않아도 됩니다.  자세한 내용은 [항목 정의](../msbuild/item-definitions.md)를 참조하십시오.  
  
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
|[항목](../msbuild/item-element-msbuild.md)|빌드 프로세스의 입력을 정의합니다.  `ItemDefinitionGroup`에는 `Item` 요소가 0개 이상 있을 수 있습니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[프로젝트](../msbuild/project-element-msbuild.md)|[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트 파일의 필수 루트 요소입니다.|  
  
## 예제  
 다음 코드 예제에서는 ItemDefinitionGroup 두 개의 메터데이터 항목, m과 n을 정의합니다.  이 예제에서 기본 메타데이터 "m"은 항목 "i"에 의해 명시적으로 정의되지 않으므로 항목 "i"에 적용됩니다.  그러나 기본 메타데이터 "n"은 항목 "i"에 의해 이미 정의되어 있으므로 항목 "i"에 적용되지 않습니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemDefinitionGroup>  
        <i>  
            <m>m1</m>  
            <n>n1</n>  
        </i>        
    </ItemDefinitionGroup>  
    <ItemGroup>  
        <i Include="a">  
            <o>o1</o>  
            <n>n2</n>  
        </i>  
    </ItemGroup>  
    ...  
</Project>  
```  
  
## 참고 항목  
 [Project File Schema Reference](../msbuild/msbuild-project-file-schema-reference.md)   
 [항목](../msbuild/msbuild-items.md)