---
title: "SupportsCodeSeparation 요소 (Visual Studio 템플릿) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#SupportsCodeSeparation
helpviewer_keywords:
- SupportsCodeSeparation element [Visual Studio Templates]
- <SupportsCodeSeparation> element [Visual Studio Templates]
ms.assetid: 8112aac8-a269-40e5-b92b-9b9a6ff5a542
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: affe4d6c73271bea467e373bd8100b3b7f06c0ea
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="supportscodeseparation-element-visual-studio-templates"></a>SupportsCodeSeparation 요소(Visual Studio 템플릿)
지정 여부는 **다른 파일에 코드를 입력** 확인란이 활성화 되는 **새 항목 추가** 대화 상자.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<SupportsCodeSeparation >  
  
## <a name="syntax"></a>구문  
  
```  
<SupportsCodeSeparation> true/false </SupportsCodeSeparation>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 템플릿을 분류 하 고 표시 하는 방법을 정의 **새 프로젝트** 또는 **새 항목** 대화 상자.|  
  
## <a name="text-value"></a>텍스트 값  
 텍스트 값은 필수입니다.  
  
 텍스트 중 하나 여야 합니다 `true` 또는 `false`한다는 표시 이므로 여부는 **다른 파일에 코드를 입력** 확인란이 활성화 되는 **새 항목 추가** 대화 상자.  
  
## <a name="remarks"></a>설명  
 `SupportsCodeSeparation`는 선택적 요소입니다. 기본값은 `false`입니다.  
  
 `SupportsCodeSeparation` 요소는 웹 항목 템플릿을 사용할 수 있습니다.  
  
 코드 분리 또는 코드 숨김 페이지 모델을 한 개의 파일과 다른 파일에 프로그래밍 코드에 태그를 유지할 수 있습니다. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]및 다른.NET 언어는이 모델을 사용 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 표시 하도록 지정는 **별도 파일에 코드 입력** 옵션입니다.  
  
```  
<VSTemplate Version="3.0.0" Type="Project"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">>  
    <TemplateData>  
        <Name>MyWebProjecStarterKit</Name>  
        <Description>A simple Web template</Description>  
        <Icon>icon.ico</Icon>  
        <ProjectType>Web</ProjectType>  
        <ProjectSubType>CSharp</ProjectSubType>  
        <DefaultName>WebSite</DefaultName>  
        <SupportsCodeSeparation>true</SupportsCodeSeparation>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="WebApplication.webproj">  
            <ProjectItem>icon.ico</ProjectItem>  
            <ProjectItem OpenInEditor="true">Default.aspx</ProjectItem>  
            <ProjectItem>Default.aspx.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)