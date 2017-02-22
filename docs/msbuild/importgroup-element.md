---
title: "ImportGroup Element | Microsoft Docs"
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
  - "<ImportGroup> element [MSBuild]"
  - "ImportGroup element [MSBuild]"
ms.assetid: dac3fa2d-6678-4017-af35-93686f53f302
caps.latest.revision: 4
caps.handback.revision: 4
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# ImportGroup Element
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

옵션 조건 하에 그룹화된 `Import` 요소의 컬렉션을 포함합니다.  자세한 내용은 [Import 요소\(MSBuild\)](../msbuild/import-element-msbuild.md)를 참조하십시오.  
  
## 구문  
  
```  
<ImportGroup Condition="'String A' == 'String B'">  
    <Import ... />  
    <Import ... />  
</ImportGroup>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`Condition`|선택적 특성입니다.<br /><br /> 확인할 조건입니다.  자세한 내용은 [Conditions](../msbuild/msbuild-conditions.md)을 참조하십시오.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[Import](../msbuild/import-element-msbuild.md)|한 프로젝트 파일의 내용을 다른 프로젝트 파일로 가져옵니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[프로젝트](../msbuild/project-element-msbuild.md)|[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트 파일의 필수 루트 요소입니다.|  
  
## 설명  
  
## 예제  
 다음 코드 예제에서는 `ImportGroup` 요소를 보여 줍니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ImportGroup>  
        <Import Project="$(Targets1.targets) />  
        <Import Project="$(Targets2.targets) />  
    </ImportGroup>  
...  
</Project>  
```  
  
## 참고 항목  
 [Project File Schema Reference](../msbuild/msbuild-project-file-schema-reference.md)   
 [항목](../msbuild/msbuild-items.md)