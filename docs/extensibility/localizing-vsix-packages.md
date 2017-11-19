---
title: "VSIX 패키지 지역화 | Microsoft Docs"
ms.custom: 
ms.date: 10/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- localize package
- localize extension
- localized deployment
ms.assetid: 10e80b13-b39e-466c-a7c8-774a862355af
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6a8bb9332b30e5dbc410bdacea3800713b25b10f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="localizing-vsix-packages"></a>VSIX 패키지 지역화

각 대상 언어에 대 한 Extension.vsixlangpack 파일을 만들고 해당 폴더에 놓습니다 하 여 VSIX 패키지를 지역화할 수 있습니다. 지역화 된 패키지가 설치 되 면 확장의 지역화 된 이름은 지역화 된 설명과 함께 표시 됩니다. 지역화 된 라이선스 파일 또는 지역화 된 정보를 가리키는 URL을 제공 하면도 표시 됩니다.

콘텐츠 VSIX 패키지에 추가 하는 VSPackage에 포함 되어 있으면 메뉴 명령 또는 다른 UI 참조 [메뉴 명령을 지역화](../extensibility/localizing-menu-commands.md) 새 UI 요소를 지역화 하는 방법에 대 한 정보에 대 한 합니다.

## <a name="directory-structure"></a>디렉터리 구조

 사용자가 확장을 설치 하면 **확장명 및 업데이트** VSIX 패키지 이름이 대상 컴퓨터의 Visual Studio 로캘과 일치 하는 폴더에 대 한 최상위 수준 검사 합니다. 경우 **확장명 및 업데이트** .vsixlangpack 하는 항목이 발견 폴더에 파일,.vsixmanifest 파일의 해당 값에 대 한 해당 파일에서 지역화 된 값을 대체 합니다. 이러한 값에는 확장을 설치 하는 경우 표시 됩니다. 다음 예제에서는 스페인어 (es ES) 및 프랑스어 (FR-FR)로 지역화 된 VSIX 패키지에 대 한 디렉터리 구조를 보여 줍니다.  

```text
.
├── MyExtension.dll
├── Extension.vsixmanifest
├── [Content_Types].xml
├── es-ES
│   └── Extension.vsixlangpack
└── fr-FR
    └── Extension.vsixlangpack
```

> [!NOTE]
> VSIX에서 지 원하는 프로젝트 템플릿을 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] VSIX 매니페스트를 생성 하 고 source.extension.vsixmanifest 라는 이름을 지정 합니다. Visual Studio에서 프로젝트를 빌드할 때 해당 파일의 콘텐츠를 복사 Extension.VsixManifest VSIX 패키지에 있습니다.

## <a name="the-extensionvsixlangpack-file"></a>Extension.vsixlangpack 파일

Extension.vsixlangpack 파일은 다음과 같습니다는 [VSIX 언어 팩 스키마 2.0](../extensibility/vsix-language-pack-schema-2-0-reference.md)합니다. 이 스키마에는 `PackageLanguagePackManifest`는 바로 다음에 `Metadata` 자식 요소입니다. 메타 데이터 요소에 최대 6 자식 요소가 포함 될 수 있습니다 `DisplayName`, `Description`, `MoreInfo`, `License`, `ReleaseNotes`, 및 `Icon`합니다. 이러한 자식 요소에 해당 하는 `DisplayName`, `Description`, `MoreInfo`, `License`, `ReleaseNotes`, 및 `Icon` 의 자식 요소는 `Metadata` Extension.vsixmanifest 파일의 요소입니다.

Vsixlangpack 파일을 만들 때 설정 해야는 `Include in Vsix` 속성을 `true`합니다. 그렇지 않은 경우 지역화 된 설치 텍스트는 무시 됩니다.

### <a name="to-set-the-include-in-vsix-property"></a>포함 된 Vsix 속성에 설정 하려면

1. **솔루션 탐색기**Extension.vsixlangpack 파일을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다.

2.  속성 그리드에서 클릭 **Vsix에 포함**, 해당 값을 설정 하 고 `true`합니다.

## <a name="example"></a>예제

### <a name="description"></a>설명

다음 예제에서는 Extension.vsixmanifest 파일을 스페인어 해당 Extension.vsixlangpack 파일과 함께 관련 부분을 보여 줍니다. 언어 팩의 값은 대상 컴퓨터의 Visual Studio 로캘 스페인어로 설정 된 경우 매니페스트에서 값을 대체 합니다.

### <a name="code"></a>코드

 [Extension.vsixmanifest]

```xml
<?xml version="1.0" encoding="utf-8"?>
<PackageManifest ...>
  <Metadata ...>
    <DisplayName>Family Tree</DisplayName>
    <Description>This extension places a custom treeview control in the toolbox that is optimized for handling family tree information.</Description>
    <MoreInfo>http://www.contoso.com/products/FamilyTree.htm</MoreInfo>
    <License>Eula.rtf</License>
    <ReleaseNotes>ReleaseNotes.rtf</ReleaseNotes>
    <Icon>Icon.png</Icon>
  </Metadata>
  <Installation .../>
  <Dependencies .../>
  <Prerequisites .../>
  <Assets .../>
</PackageManifest>
```

 [Extension.vsixlangpack]

```xml
<?xml version="1.0" encoding="utf-8"?>
<PackageLanguagePackManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011">
  <Metadata>
    <DisplayName>Arbol de Familia</DisplayName>
    <Description> Esta extensión pone control personalizado en la caja de herramientas por manejar información de familia.</Description>
    <MoreInfo> http://www.contoso.com/products/es/ArbolDeFamilia.htm</MoreInfo>
    <License>Eula.rtf</License>
    <ReleaseNotes>ReleaseNotes.rtf</ReleaseNotes>
    <Icon>Icon.png</Icon>
  </Metadata>
</PackageLanguagePackManifest>
```

## <a name="see-also"></a>참고 항목

|제목|설명|
|-----------|-----------------|
|[VSIX LanguagePack 스키마 2.0 참조](../extensibility/vsixlanguagepack-element-vsix-language-pack-schema.md)|VSIX 언어 팩.vsix 배포 파일의 지역화 정보를 설명합니다.|
|[VSIX 패키지 분석](../extensibility/anatomy-of-a-vsix-package.md)|구조 및 vsix 패키지의 내용에 설명합니다.|
|[메뉴 명령 지역화](../extensibility/localizing-menu-commands.md)|확장의 다른 텍스트 리소스를 지역화 하는 방법을 보여 줍니다.|