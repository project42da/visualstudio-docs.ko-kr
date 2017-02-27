---
title: "ItemMetadata Element (MSBuild) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "ItemMetadata Element [MSBuild]"
  - "<ItemMetadata> Element [MSBuild]"
ms.assetid: e3db5122-202d-43a9-b2f4-3e0ec4ed3d08
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# ItemMetadata Element (MSBuild)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

항목 메타데이터 값이 포함된 사용자 정의 항목 메타데이터 키가 들어 있습니다.  항목에 포함될 수 있는 메타데이터 키\-값 쌍의 수에는 제한이 없습니다.  
  
## 구문  
  
```  
<ItemMetadataName> Item Metadata value </ItemMetadataName>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`Condition`|선택적 특성입니다.<br /><br /> 확인할 조건입니다.  자세한 내용은 [Conditions](../msbuild/msbuild-conditions.md)을 참조하십시오.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[항목](../msbuild/item-element-msbuild.md)|빌드 프로세스에 대한 입력을 정의하는 사용자 정의 요소입니다.|  
  
## 텍스트 값  
 텍스트 값은 선택적입니다.  
  
 이 텍스트는 텍스트나 XML일 수 있는 항목 메타데이터 값을 지정합니다.  
  
## 설명  
  
## 예제  
 다음 코드 예제에서는 값이 `fr`인 `Culture` 메타데이터를 `CSFile` 항목에 추가하는 방법을 보여 줍니다.  
  
```  
<ItemGroup>  
    <CSFile Include="main.cs" >  
        <Culture>fr</Culture>  
    </CSFile>  
</ItemGroup>  
```  
  
## 참고 항목  
 [Project File Schema Reference](../msbuild/msbuild-project-file-schema-reference.md)   
 [항목](../msbuild/msbuild-items.md)