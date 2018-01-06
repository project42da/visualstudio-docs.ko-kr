---
title: "ProvideDefaultName 요소 (Visual Studio 템플릿) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#ProvideDefaultName
helpviewer_keywords: ProvideDefaultName element [Visual Studio project templates]
ms.assetid: 7b0e7b20-fd6b-42e2-81d0-e5100cea0528
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 48dbc92687a813dcd2a99659b9c2a8cc26129c79
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="providedefaultname-element-visual-studio-templates"></a>ProvideDefaultName 요소(Visual Studio 템플릿)
지정 여부는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트 시스템에서 서식 파일에 대 한 기본 이름이 생성 됩니다는 **새 항목 추가** 또는 **새 프로젝트** 대화 상자.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<ProvideDefaultName >  
  
## <a name="syntax"></a>구문  
  
```  
<ProvideDefaultName> true/false </ProvideDefaultName>  
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
  
 텍스트 중 하나 여야 합니다 `true` 또는 `false`에서 서식 파일에 대 한 기본 이름을 생성 여부를 나타내는 **새 항목 추가** 또는 **새 프로젝트** 대화 상자.  
  
## <a name="remarks"></a>설명  
 `ProvideDefaultName`는 선택적 요소입니다. 기본값은 `true`입니다.  
  
 경우는 `ProvideDefaultName` 요소는 `false`, **이름** 의 상자는 **새 항목 추가** 및 **새 프로젝트** 대화 상자에 값이 포함 되어 `<Enter_name>`합니다.  
  
 사용 하 여는 [DefaultName](../extensibility/defaultname-element-visual-studio-templates.md) 요소를 프로젝트의 기본 이름을 지정 하거나 항목에 **새 항목 추가** 및 **새 프로젝트** 대화 상자.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 `ProvideDefaultName` 요소의 `false`합니다.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <ProvideDefaultName>false</ProvideDefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem>MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)