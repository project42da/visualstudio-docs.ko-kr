---
title: SortOrder 요소 (Visual Studio 템플릿) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#SortOrder
helpviewer_keywords:
- SortOrder element [Visual Studio Templates]
- <SortOrder> element [Visual Studio Templates]
ms.assetid: 151932c1-f08a-4f78-a8d0-bd2f32211a9c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b963b6e74b7c24d31ddc611407df22380ff8bb60
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="sortorder-element-visual-studio-templates"></a>SortOrder 요소(Visual Studio 템플릿)
중 하나에 표시 된 대로 동일한 범주에 다른 템플릿 간에 템플릿을 정렬 하는 데 사용 되는 값을 지정 된 **새 프로젝트** 또는 **새 항목 추가** 대화 상자.  
  
 \<VSTemplate>  
 \<TemplateData>  
 \<SortOrder >  
  
## <a name="syntax"></a>구문  
  
```  
<SortOrder> ... </SortOrder>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 템플릿을 분류하고 **새 프로젝트** 또는 **새 항목 추가** 대화 상자에서 템플릿이 표시되는 방식을 정의합니다.|  
  
## <a name="text-value"></a>텍스트 값  
 텍스트 값은 필수입니다.  
  
 `integer` 정렬 순서 값을 나타내는입니다.  
  
## <a name="remarks"></a>설명  
 `SortOrder`는 선택적 요소입니다. 기본값은 100, 및 모든 값에 10의 배수 여야 합니다.  
  
 `SortOrder` 사용자가 만든 템플릿에 대 한 요소는 무시 됩니다. 모든 사용자가 만든 서식 파일은 사전순으로 정렬 됩니다.  
  
 템플릿이 낮은 정렬 순서 값 중 하나에 표시 되는 **새 프로젝트** 또는 **새 항목 추가** 높은 정렬 순서 값이 있는 템플릿 하기 전에 대화 상자.  
  
## <a name="example"></a>예제  
 다음 예제에서는 표준에 대 한 메타 데이터 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 클래스 템플릿을 합니다.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class template.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <SortOrder>290</SortOrder>  
        <DefaultName>MyClass</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem>MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 이 예제는 `SortOrder` 요소는 상대적으로 높습니다. 가능성이 있는 다른 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 항목 템플릿의 `SortOrder` 보다 낮은 값 `290` 에서이 템플릿을 앞에 표시 되 고는 **새 항목** 대화 상자.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)