---
title: "방법: Visual Studio에 대 한 왕복 확장 | Microsoft Docs"
ms.custom: 
ms.date: 06/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d6cf53c-011e-4c9e-9935-417edca8c486
caps.latest.revision: "1"
author: willbrown
ms.author: willbrown
manager: justinclareburt
ms.openlocfilehash: 99bdd5a0f31b9cbccd84a7c05f6d3cdcc0c267f6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-make-extensions-compatible-with-visual-studio-2017-and-visual-studio-2015"></a>방법: 확장을 Visual Studio 2017 및 Visual Studio 2015와 호환 되도록

이 문서에서는 확장성 프로젝트를 Visual Studio 2015 및 Visual Studio 2017 간의 왕복 하는 방법에 설명 합니다. 이 업그레이드를 완료 한 후 프로젝트를 열고, 빌드, 설치 및 Visual Studio 2015와 Visual Studio 2017 모두에서 실행 하는 작업을 할 수 있습니다.  Visual Studio 2015 및 Visual Studio 2017 간의 왕복 수 있는 일부 확장을 찾지 대 한 참조로 [여기](https://github.com/Microsoft/VSSDK-Extensibility-Samples) Microsoft의 확장성 예제입니다.

만 Visual Studio 2017 년에 작성 하지만 Visual Studio 2015와 Visual Studio 2017 모두에서 실행 되도록 VSIX 출력 하려는 경우 다음을 참조는 [확장 마이그레이션 문서](how-to-migrate-extensibility-projects-to-visual-studio-2017.md)합니다.

>**참고:** Visual Studio의 버전 간에 변경으로 인 한 버전에서 작동 되는 일부의 원인 작동 하지 것입니다 다른 합니다. 두 버전 모두에서 사용할 수 있는 액세스 하려고 하는 기능 또는 확장 갖습니다 확인 예기치 않은 결과입니다.

이 문서 라운드트립 VSIX 완료 하는 단계의 개요는 다음과 같습니다.

1. 올바른 NuGet 패키지를 가져옵니다.
2. 확장 매니페스트를 업데이트 합니다.
    * 설치 대상
    * 필수 구성 요소
3. CSProj를 업데이트 합니다.
    * 업데이트 `<MinimumVisualStudioVersion>`합니다.
    * 추가 `<VsixType>` 속성입니다.
    * 디버깅 속성 추가 `($DevEnvDir)` 3 회입니다.
    * 빌드 도구 및 목표를 가져오기 위한 조건을 추가 합니다.

4. 빌드 및 테스트

## <a name="environment-setup"></a>환경 설치

이 문서에서는 다음이 컴퓨터에 설치 되어 있다고 가정 합니다.

* Visual Studio 2015 및 VS SDK가 설치 되어
* Visual Studio 2017 설치 확장성 작업의

## <a name="recommended-approach"></a>권장 되는 방법

Visual Studio 2017 대신 Visual Studio 2015와 함께이 업그레이드를 시작 하는 것이 좋습니다. Visual Studio 2015에서 개발의 주요 장점은 Visual Studio 2015에서 사용할 수 없는 어셈블리를 참조 하지 않는 것입니다. Visual Studio 2017에서 개발을 수행 하는 경우 Visual Studio 2017에만 존재 하는 어셈블리에 대 한 종속성을 발생할 수 있는 위험이 있습니다.

## <a name="ensure-there-is-no-reference-to-projectjson"></a>Project.json에 대 한 참조 확인

이 문서의 뒷부분에 *.csproj 파일에 조건부 import 문을 삽입 합니다.  이 NuGet 참조 project.json에 저장 된 경우 작동 하지 않습니다. 따라서 모든 NuGet 참조 packages.config 파일을 이동 하는 것이 좋습니다.
Project.json 파일 포함:

* Project.json에 대 한 참조 기록해 둡니다.
* 솔루션 탐색기에서 프로젝트의 project.json 파일을 삭제 합니다.
    * 이 project.json 파일을 삭제 하 고 프로젝트에서 제거 합니다.
* NuGet 참조 프로젝트에 다시 추가 합니다.
    * 솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **솔루션에 대 한 NuGet 패키지 관리...**
    * Visual Studio를 packages.config 파일을 자동으로 만듭니다.

>**참고:** 프로젝트 EnvDTE 패키지에 포함 된 경우 마우스 오른쪽 단추로 클릭 하 여 추가할 수 해야 할 수 있습니다 **참조** 선택 **참조 추가** 적절 한 참조를 추가 합니다.  NuGet 패키지를 사용 하 여 프로젝트를 빌드해야 하는 동안 오류를 만들 수 있습니다.

## <a name="adding-appropriate-build-tools"></a>적절 한 빌드 도구 추가

빌드하고 적절 하 게 디버깅할 수 있도록 빌드 도구 추가를 내기 위해서는 필요 합니다. Microsoft는이 호출된 Microsoft.VisualStudio.Sdk.BuildTasks에 대 한 어셈블리를 만들었습니다.

를 빌드하고 Visual Studio 2015와 2017 VSIXv3를 배포 하려면 다음 NuGet 패키지가 필요 합니다.

버전 | 기본 제공된 도구
--- | ---
Visual Studio 2015 | Microsoft.VisualStudio.Sdk.BuildTasks.14.0
Visual Studio 2017 | Microsoft.VSSDK.BuildTool

이렇게 하려면

* NuGet 패키지 Microsoft.VisualStudio.Sdk.BuildTasks.14.0 프로젝트를 추가 합니다.
* 프로젝트에 Microsoft.VSSDK.BuildTools 찾을 수 없는 경우이 추가 합니다.
* 되는지 15.x Microsoft.VSSDK.BuildTools 버전 이상.

## <a name="update-extension-manifest"></a>확장 매니페스트를 업데이트 합니다.

### <a name="1-installation-targets"></a>1. 설치 대상

Visual Studio는 VSIX를 구축 하기 위한 대상으로 어떤 버전에 지시할이 필요 합니다.  일반적으로 이러한 참조는 14.0 (Visual Studio 2015) 버전 또는 버전 15.0 (Visual Studio 2017).  경우에 두 버전을 대상으로 해야 하므로 확장 동시에 설치 된 VSIX를 작성 하려고 합니다.  프로그램 VSIX를 빌드 및 14.0 보다 이전 버전에서 설치 하려는 경우 이렇게는 이전 버전 번호를 설정 하 여 그러나 버전 10.0 및 이전 버전 더 이상 사용할 수 없습니다.

* Visual Studio에서 source.extension.vsixmanifest 파일을 엽니다.
* 열기는 **설치 대상** 탭 합니다.
* 변경 된 **버전 범위** 를 [14.0, 16.0).  ' [' 지난 것 14.0 및 모든 버전을 포함 하도록 Visual Studio를 알려 줍니다.  ')' Visual Studio 15.0 버전 16.0 점을 포함 하지 않고 까지의 모든 버전을 포함 하도록 지시 합니다.
* 모든 변경 내용을 저장 하 고 Visual Studio의 모든 인스턴스를 닫습니다.

![설치 대상 이미지](media/visual-studio-installation-targets-example.png)

### <a name="2-adding-prerequisites-to-the-extensionvsixmanifest-file"></a>2. Extension.vsixmanifest 파일을 필수 구성 요소 추가

필수 구성 요소는 Visual Studio 2017 된 새로운 기능입니다.  이 경우 Visual Studio 핵심 편집기 필수 구성 요소로 필요합니다. Visual Studio 2015 VSIX 디자이너 새 처리 하지 않는 이후 `Prerequisites` 섹션 XML 코드에서 수동으로이 부분을 편집 하려면 필요 합니다.  또는 Visual Studio 2017를 열고 업데이트 된 매니페스트 디자이너를 사용 하 여 필수 구성 요소를 삽입할 수 있습니다.

수동으로 수행할 작업:

* 파일 탐색기에서 프로젝트 디렉터리로 이동 합니다.
* 열기는 `extension.vsixmanifest` 파일 텍스트 편집기를 사용 합니다.
* 다음 태그를 추가 합니다.

```xml
<Prerequisites>
    <Prerequisite Id="Microsoft.VisualStudio.Component.CoreEditor" Version="[15.0,16.0)" DisplayName="Visual Studio core editor" />
</Prerequisites>
```

* 파일을 저장한 후 닫습니다.

>**참고:** Visual Studio 2017에 VSIX 디자이너를 사용 하 여이 수행할 하기로 선택한 경우 모든 버전의 Visual Studio 2017와 호환 되도록 필수 구성 요소 버전을 수동으로 편집 해야 합니다.  디자이너는 최소 버전 (예를 들어 15.0.26208.0) Visual Studio의 현재 버전으로 삽입 때문입니다.  그러나 다른 사용자가 이전 버전을 가질 수 있으므로 수동으로 편집 하려는이 15.0를 합니다.

이 시점에서 매니페스트 파일에 다음과 같이 표시 됩니다.

![필수 구성 요소 예제](media/visual-studio-prerequisites-example.png)

## <a name="modify-the-project-file-myprojectcsproj"></a>프로젝트 파일 (myproject.csproj)을 수정

이 단계를 수행 하는 동안 열려는 수정 된.csproj에 대 한 참조 하는 것이 좋습니다.  몇 가지 예제를 찾을 수 있습니다 [여기](https://github.com/Microsoft/VSSDK-Extensibility-Samples)합니다.  확장성 샘플 선택한 참조에 대 한.csproj 파일을 찾을 다음 단계를 실행 합니다.

* 파일 탐색기에서 프로젝트 디렉터리로 이동 합니다.
* 텍스트 편집기로 myproject.csproj 파일을 엽니다.

### <a name="1-update-the-minimumvisualstudioversion"></a>1. 업데이트는 MinimumVisualStudioVersion

* 최소 visual studio 버전을 설정 `$(VisualStudioVersion)` 조건문을 추가 합니다.  존재 하지 않는 경우 이러한 태그를 추가 합니다.  태그는 아래와 같이 설정 되어 있는지 확인 합니다.

```xml
<VisualStudioVersion Condition="'$(VisualStudioVersion)' == ''">14.0</VisualStudioVersion>
<MinimumVisualStudioVersion>$(VisualStudioVersion)</MinimumVisualStudioVersion>
```

### <a name="2-add-the-vsixtype-property"></a>2. VsixType 속성 추가

* 다음 태그를 추가 `<VsixType>v3</VsixType>` 속성 그룹에 있습니다.

>**참고:** 이 추가 하는 것이 좋습니다. 아래에서 `<OutputType></OutputType>` 태그입니다.

### <a name="3-add-the-debugging-properties"></a>3. 디버깅 속성 추가

* 다음 속성 그룹을 추가 합니다.

```xml
<PropertyGroup>
    <StartAction>Program</StartAction>
    <StartPrograms>$(DevEnvDir)devenv.exe</StartPrograms>
    <StartArguments>/rootsuffix Exp</StartArguments>
</PropertyGroup>
```

* .Csproj 파일에서 다음의 모든 인스턴스를 삭제 합니다. csproj.user 파일:

```xml
<StartAction>Program</StartAction>
<StartPrograms>$(ProgramFiles)\Microsoft Visual Studio 14.0\Common7\IDE\devenv.exe</StartPrograms>
<StartArguments>/rootsuffix Exp</StartArguments>
```

### <a name="4-add-conditions-to-the-build-tools-imports"></a>4. 빌드 도구 가져오기에 조건 추가

* 에 추가 조건부 문을 추가 하는 `<import>` Microsoft.VSSDK.BuildTools 참조 하는 태그입니다.  삽입 하 여이 작업을 수행 `'$(VisualStudioVersion)' != '14.0' And` 조건 문으로 앞에 있습니다.  이러한 문은 머리글 및 csproj 파일의 바닥글에 표시 됩니다.

예:

```xml
<Import Project="packages\Microsoft.VSSDK.BuildTools.15.0.26201… Condition="'$(VisualStudioVersion)' != '14.0' And Exists(…/>
```

* 에 추가 조건부 문을 추가 하는 `<import>` 는 Microsoft.VisualStudio.Sdk.BuildTasks.14.0 있는 태그입니다.  삽입 하 여이 작업을 수행 `'$(VisualStudioVersion)' == '14.0' And` 조건 문으로 앞에 있습니다. 이러한 문은 머리글 및 csproj 파일의 바닥글에 표시 됩니다.

예:

```xml
<Import Project="packages\ Microsoft.VisualStudio.Sdk.BuildTasks.14.0.14.0… Condition="'$(VisualStudioVersion)' == '14.0' And Exists(…/>
```

* 에 추가 조건부 문을 추가 하는 `<Error>` Microsoft.VSSDK.BuildTools 참조 하는 태그입니다.  삽입 하 여이 작업을 수행 `'$(VisualStudioVersion)' != '14.0' And` 조건 문으로 앞에 있습니다. 이러한 문은 csproj 파일의 바닥글에 표시 됩니다.

예:

```xml
<Error Condition="'$(VisualStudioVersion)' != '14.0' And Exists('packages\Microsoft.VSSDK.BuildTools.15.0.26201…/>
```

* 에 추가 조건부 문을 추가 하는 `<Error>` 는 Microsoft.VisualStudio.Sdk.BuildTasks.14.0 있는 태그입니다.  삽입 하 여이 작업을 수행 `'$(VisualStudioVersion)' == '14.0' And` 조건 문으로 앞에 있습니다. 이러한 문은 csproj 파일의 바닥글에 표시 됩니다.

예:

```xml
<Error Condition="'$(VisualStudioVersion)' == '14.0' And Exists('packages\ Microsoft.VisualStudio.Sdk.BuildTasks.14.0.14.0…/>
```

* Csproj 파일을 저장 하 고 닫습니다.

## <a name="test-the-extension-installs-in-visual-studio-2015-and-visual-studio-2017"></a>Visual Studio 2015 및 Visual Studio 2017에서 확장 설치를 테스트 합니다.

이 시점에서 프로젝트를 Visual Studio 2015와 Visual Studio 2017 모두에 설치할 수 있는 VSIXv3 빌드하기 위한 준비 해야 합니다.

* Visual Studio 2015의 프로젝트를 열으십시오
* 프로젝트를 빌드하고 확인 VSIX 올바르게 빌드 출력에
* 프로젝트 디렉터리로 이동 합니다.
* -> 엽니다 저장소 시간 디버그 폴더
* Visual Studio 2015 및 Visual Studio 2017에 확장을 설치 하 고 VSIX 파일을 두 번 클릭
* 확장명 및 업데이트 "설치" 섹션에서-> 도구에서 확장을 볼 수 있는지 확인 하십시오.
* 확장 작업 하는지를 점검을 실행/사용 하려고

![한 VSIX 찾기](media/finding-a-VSIX-example.png)

>**참고:** 프로젝트 디렉터리로 프로젝트와 Visual Studio를 종료 메시지 "파일을 열어" 강제 중지 하는 경우 숨겨진된 폴더를 표시 한.vs 폴더를 삭제 합니다.
