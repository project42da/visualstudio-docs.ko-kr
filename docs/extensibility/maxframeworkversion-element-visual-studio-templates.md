---
title: MaxFrameworkVersion 요소 (Visual Studio 템플릿) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- <MaxFrameworkVersion> Element (Visual Studio Templates)
- MaxFrameworkVersion Element (Visual Studio Templates)
ms.assetid: f732a9d3-fc29-405b-9298-01ea83fc58b8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4bc28fcc35a4a59852ef6864886acff4dc87ef60
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="maxframeworkversion-element-visual-studio-templates"></a>MaxFrameworkVersion 요소(Visual Studio 템플릿)

서식 파일에 필요한.NET Framework의 최대 버전을 지정 합니다. 사용할 수 있는 가장 높은 값을 결정는 **대상 프레임 워크 버전** 드롭다운의는 **새 프로젝트** 대화 상자. 사용자가 프레임 워크 버전을 선택할 수를 지정 해야 [RequiredFrameworkVersion](../extensibility/requiredframeworkversion-element-visual-studio-templates.md) 템플릿에 대 한 최소.NET Framework 버전으로 합니다.

> [!IMPORTANT]
> Visual Studio 2017 15.6 버전부터는 **대상 프레임 워크 버전** 드롭다운에 표시 된 서식 파일에 대 한 필터를 더 이상는 **템플릿** 의 섹션은 **새프로젝트** 대화 상자. 대신,는 **대상 프레임 워크 버전** 드롭다운에서 선택한 서식 파일에 대 한 프레임 워크 선택으로 작동 합니다.

 \<VSTemplate> \<TemplateData> \<MaxFrameworkVersion>

## <a name="syntax"></a>구문

```xml
<MaxFrameworkVersion> ... </MaxFrameworkVersion>
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 템플릿을 분류 하 고 하나에 표시 되는 방식을 정의 **새 프로젝트** 또는 **새 항목 추가** 대화 상자.|

## <a name="text-value"></a>텍스트 값
 텍스트 값은 필수입니다.

 텍스트는 템플릿에 의해 허용 되는.NET Framework의 가장 높은 버전 번호 여야 합니다.

## <a name="remarks"></a>설명

`MaxFrameworkVersion`는 선택적 요소입니다. `MaxFrameworkVersion` 를 하지 못하도록 템플릿에 대 한 지원 되는.NET Framework 버전을 실수로 제한 필요한 경우가 아니면 요소를 생략 해야 합니다. .NET Framework 서식 파일에 적용할 수 없는 경우도 생략 해야 합니다.

## <a name="example"></a>예제

다음 예제에서는 표준에 대 한 메타 데이터 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 클래스 템플릿을 합니다.

```xml
<VSTemplate Type="Item" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>MyClass</Name>
        <Description>My custom C# class template.</Description>
        <Icon>Icon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <RequiredFrameworkVersion>3.0</RequiredFrameworkVersion>
        <MaxFrameworkVersion>4.7.1</MaxFrameworkVersion>
        <DefaultName>MyClass</DefaultName>
    </TemplateData>
    <TemplateContent>
        <ProjectItem>MyClass.cs</ProjectItem>
    </TemplateContent>
</VSTemplate>
```

이 예제에서는 서식 파일을 여는 데 필요한.NET Framework의 최대 버전에에서도 표현 `MaxFrameworkVersion`, 4.7.1 됩니다. 이 템플릿을 사용 하 여 만든 프로젝트는.NET Framework 버전 4.7.1까지 지정할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)
- [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)
