---
title: "방법: Visual Studio 2017로 확장성 프로젝트 마이그레이션 | Microsoft Docs"
ms.custom: 
ms.date: 11/09/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ca07b00-a3ff-40ab-b647-c0a93b55e86a
caps.latest.revision: "1"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bb00d2c338ac1ef9e2be6d77d68ebfe2a246d807
ms.sourcegitcommit: 5f5587a1bcf4aae995c80d54a67b4b461f8695f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/29/2017
---
# <a name="how-to-migrate-extensibility-projects-to-visual-studio-2017"></a>방법: Visual Studio 2017로 확장성 프로젝트 마이그레이션

이 문서에서는 Visual Studio 2017을 확장성 프로젝트를 업그레이드 하는 방법을 설명 합니다. 프로젝트 파일을 업데이트 하는 방법을 설명 하는 외에도 또한 확장 매니페스트 버전 2 (VSIX v2)에서 새 버전 3 VSIX 매니페스트 형식 (VSIX v3)로 업그레이드 하는 방법을 설명 합니다.

## <a name="install-visual-studio-2017-with-required-workloads"></a>필요한 작업이 있는 Visual Studio 2017 설치

설치에는 다음과 같은 작업을 포함 되어 있는지 확인 합니다.

* .NET 데스크톱 개발
* Visual Studio 확장 개발

## <a name="open-vsix-solution-in-visual-studio-2017"></a>Visual Studio 2017에서 VSIX 솔루션을 열으십시오

모든 VSIX 프로젝트를 Visual Studio 2017을 지정 하는 주 버전 단방향 업그레이드가 필요 합니다.

프로젝트 파일 (예: *.csproj) 업데이트 됩니다.

* MinimumVisualStudioVersion-현재 15.0로 설정 합니다.
* OldToolsVersion (하는 경우 이전에 존재)-이제 14.0으로 설정

## <a name="update-the-microsoftvssdkbuildtools-nuget-package"></a>Microsoft.VSSDK.BuildTools NuGet 패키지를 업데이트 합니다.

>**참고:** 솔루션 Microsoft.VSSDK.BuildTools NuGet 패키지를 참조 하지 않는 경우이 단계를 건너뛸 수 있습니다.

새 VSIX v3에서 확장 프로그램을 작성 하기 위해 (버전 3) 형식으로 솔루션은 새 VSSDK 빌드 도구와 함께 빌드될 필요 합니다. 이 Visual Studio 2017 함께 설치할 수는 있지만 VSIX v2 확장 NuGet 통해 이전 버전에 대 한 참조를 보유 될 수 있습니다. 이 경우 Microsoft.VSSDK.BuildTools NuGet 패키지를 솔루션에 대 한 업데이트를 수동으로 설치 해야 합니다.

NuGet을 업데이트 하려면 Microsoft.VSSDK.BuildTools 참조 합니다.

* 솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **솔루션에 대 한 NuGet 패키지 관리...**
* 탐색 하 고 **업데이트** 탭 합니다.
* Microsoft.VSSDK.BuildTools (최신 버전)을 선택 합니다.
* 키를 눌러 **업데이트**합니다.

![VSSDK 빌드 도구](media/vssdk-build-tools.png)

## <a name="make-changes-to-the-vsix-extension-manifest"></a>VSIX 확장 매니페스트를 변경 합니다.

사용자의 Visual Studio 설치에서 확장을 실행 하는 데 필요한 모든 어셈블리를 갖도록 확장 매니페스트 파일에 모든 필수 구성 요소 또는 패키지를 지정 합니다. 사용자가 확장을 설치 하려고 하는 경우는 VSIXInstaller 모든 필수 조건이 설치 된 경우를 확인 합니다. 누락 된 일부 경우에 사용자 확장 설치 과정의 일환으로 누락 된 구성 요소를 설치 하려면 나타납니다.

>**참고:** 여기에 최소한 모든 확장으로 지정 해야 Visual Studio 핵심 편집기 구성 요소의 필수 구성 요소입니다.

* (일반적으로 source.extension.vsixmanifest 라고 함)에서 확장 매니페스트 파일을 편집 합니다.
* 확인 `InstallationTarget` 15.0 포함 됩니다.
* (아래 예에 나와 있는 것) 처럼 필요한 설치 필수 구성 요소를 추가 합니다.
  * 설치 필수 구성 요소에 대 한 구성 요소 Id를 지정 하는 것이 좋습니다.
  * 부분에 대 한이 문서의 끝에 있는 참조 [식별 하는 구성 요소 Id에 대 한 지침](#finding-component-ids)합니다.

예제:

```xml
<PackageManifest>
 ...
    <Prerequisites>
        <Prerequisite Id="Microsoft.VisualStudio.Component.CoreEditor" Version="[15.0,16.0)" />
        <Prerequisite Id="Microsoft.VisualStudio.Component.DiagnosticTools" Version="[15.0.25814.0,16.0)" />
        <Prerequisite Id="Microsoft.VisualStudio.Shell.12.0" Version="[12.0]" />
    </Prerequisites>
 ...
</PackageManifest>
```

### <a name="option-use-the-designer-to-make-changes-to-the-vsix-extension-manifest"></a>VSIX 확장 매니페스트를 변경 하려면 디자이너를 사용 하는 옵션:

매니페스트 XML을 직접 편집 하는 대신 사용할 수 있습니다 새 **필수 구성 요소** 매니페스트 디자이너의 필수 구성 요소를 선택 하는 XML의 탭 수에 대 한 업데이트 됩니다.

>**참고:** 매니페스트 디자이너에서만 수 (작업 부하 또는 패키지) 설치 된 구성 요소는 현재 Visual Studio 인스턴스에서 선택할 수 있습니다. 작업, 패키지 또는 현재 설치 되어 있지 않은 구성 요소에 대 한 필수 구성 요소를 추가 해야 하는 경우 매니페스트 XML을 직접 편집 합니다.

* [디자인] source.extension.vsixmanifest 파일을 엽니다.
* 선택 **필수 구성 요소** 탭 및 키를 눌러 **새로** 단추입니다.

  ![VSIX 매니페스트 디자이너](media/vsix-manifest-designer.png)

* **새 필수 추가** 창이 열립니다.

  ![vsix 필수 구성 요소를 추가 합니다.](media/add-vsix-prerequisite.png)

* 에 대 한 드롭다운 목록에서 클릭 **이름** 하 고 원하는 필수 구성 요소를 선택 합니다.
* 필요한 경우 버전을 업데이트 합니다.

  >참고: 버전 필드 됩니다는 범위까지 스패닝 (시간은 포함 되지 않음)와 현재 설치 된 구성 요소 버전으로 미리 채워진 다음 주 버전의 구성 요소입니다.

  ![roslyn 필수 구성 요소를 추가 합니다.](media/add-roslyn-prerequisite.png)

* Press **OK**.

## <a name="update-debug-settings-for-project"></a>프로젝트에 대 한 디버그 설정 업데이트

Visual Studio의 실험적 인스턴스에서 확장 프로그램을 디버깅 하려는 경우에 대 한 프로젝트 설정을 **디버그** > **시작 작업** 에 **외부 시작 프로그램:** 값 Visual Studio 2017 설치의 devenv.exe 파일으로 설정 합니다.

것 같을 수 있습니다.

```
C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\devenv.exe
```

![시작 외부 프로그램](media/start-external-program.png)

>**참고:** 디버그 시작 작업은 일반적으로에 저장에서. csproj.user 파일입니다. 이 파일은 일반적으로.gitignore 파일에 포함 됩니다 하 고 따라서 일반적으로 함께 저장 되지 않습니다 소스 제어 영역 집합에 있을 때 다른 프로젝트 파일입니다. 따라서 솔루션에 소스 제어에서 새가 가져오는 경우가 작업할 가능성 프로젝트 시작 작업에 대 한 설정 값이 없는 됩니다. Visual Studio 2017을 사용 하 여 만든 새 VSIX 프로젝트는 것입니다는. 현재 Visual Studio 설치 디렉터리를 가리키는 기본값을 사용 하 여 만든 csproj.user 파일입니다. 그러나 VSIX v2 확장을 마이그레이션하는 호스팅되고 하는. csproj.user 파일에는 이전 Visual Studio 버전의 설치 디렉터리에 대 한 참조가 포함 됩니다. 값을 설정 하면 **디버그** > **시작 작업** 확장 프로그램을 디버깅 하려고 할 때 실행 하는 올바른 Visual Studio 실험적 인스턴스를 허용 합니다.

## <a name="check-that-the-extension-builds-correctly-as-a-vsix-v3"></a>확장 (것으로 잘못 VSIX v3) 빌드 되었는지 확인 하십시오.

* VSIX 프로젝트를 빌드하십시오.
* 생성 된 VSIX를 압축을 풉니다.
  * 기본적으로 bin/Debug 내 VSIX 파일 생활 또는 bin/Release와 [YourCustomExtension].vsix로 합니다.
  * 내용을 쉽게 보려고.zip.vsix를 이름을 바꿉니다.
* 3 개의 파일의 존재 여부를 확인 합니다.
  * extension.vsixmanifest
  * manifest.json
  * catalog.json

## <a name="check-when-all-required-prerequisites-are-installed"></a>필요한 모든 필수 조건이 설치 된 경우를 확인 합니다.

VSIX 설치 필요한 모든 필수 구성 요소와 함께 컴퓨터에 성공적으로 설치 되는 테스트입니다.

>**참고:** 서비스나 확장을 설치 하기 전에 Visual Studio의 모든 인스턴스를 종료 하십시오.

확장을 설치 하려고 시도 합니다.

* Visual Studio 2017에

![Visual Studio 2017에 VSIX 설치 관리자](media/vsixinstaller-vs-2017.png)

* 선택 사항: 이전 버전의 Visual Studio에서 확인 합니다.
  * 이전 버전과 호환성을 증명합니다.
  * Visual Studio 2012, Visual Studio 2013, Visual Studio 2015에 대해 작동 해야 합니다.
* 선택 사항: VSIX 설치 관리자 버전 검사기 버전 중 하나를 선택할 수 있는지 확인 합니다.
  * (설치) 하는 경우 이전 버전의 Visual Studio에 포함 되어 있습니다.
  * Visual Studio 2017 포함 되어 있습니다.

Visual Studio를 열면 최근에 다음과 같은 대화 상자가 표시 될 수 있습니다.

![vs 실행 중인 프로세스](media/vs-running-processes.png)

프로세스 종료를 표시 될 때까지 기다리거나 작업을 중단 합니다. 괄호에 나열 된 PID 또는 나열 된 이름을 사용 하 여 프로세스를 찾을 수 있습니다.

>**참고:** 이러한 프로세스 종료 되지 않는 자동으로 Visual Studio의 인스턴스에서 실행 되는 동안 합니다. -다른 사용자를 포함 하 여 컴퓨터에 Visual Studio의 모든 인스턴스를 종료 한 다음 다시 시도 하 있습니다를 확인 합니다.

## <a name="check-when-missing-the-required-prerequisites"></a>필요한 필수 구성 요소를 누락 하는 경우를 확인 합니다.

* 확장을 설치 하는 컴퓨터에서 Visual Studio 2017 해당 하지 않는 포함 된 필수 구성 요소 (위)에 정의 된 모든 구성 요소를 시도 합니다.
* 설치 식별 누락 된 구성 요소/s는 VSIXInstaller 시 필수 구성 요소로 나열 하는지 확인 합니다.
* 참고: 모든 필수 구성 요소 확장명으로 설치 해야 할 경우 상승 필요한 됩니다 있습니다.

![vsixinstaller 누락 된 필수 구성 요소](media/vsixinstaller-missing-prerequisite.png)

## <a name="deciding-on-components"></a>구성 요소 결정

종속성을 조회할 때 종속성을 하나 여러 구성 요소에 매핑될 수를 알 수 있습니다. 확인 하 여 필수 조건으로 지정 해야 하는 종속성은와 유사한 기능을 확장 하는 구성 요소를 선택 하는 것이 좋습니다 고도 사용자 및 어떤 유형의 구성 요소를 고려해 야 할 가능성이 설치 되어 또는 가 설치 염두에 두어야 합니다. 필요한 필수 구성 요소, 확장을 실행할 수 있는 최소만을 만족 하는 방식에서 및 추가 기능에 대 한 사용자 확장에는 특정 구성 요소 검색 되지 않는 경우에 유휴 상태로 해당 건물을 좋습니다.

추가 지침을 제공 하려면 몇 가지 일반적인 확장 형식 및 해당 제안 된 필수 구성 요소 확인 했습니다.

확장 형식 | 표시 이름 | ID
--- | --- | ---
편집기 | Visual Studio 핵심 편집기  | Microsoft.VisualStudio.Component.CoreEditor
Roslyn | C# 및 Visual Basic | Microsoft.VisualStudio.Component.Roslyn.LanguageServices
WPF | 관리되는 데스크톱 워크로드 핵심 | Microsoft.VisualStudio.Component.ManagedDesktop.Core
디버거 | Just-In-Time 디버거 | Microsoft.VisualStudio.Component.Debugger.JustInTime

## <a name="finding-component-ids"></a>구성 요소 Id 찾기

에 Visual Studio 제품으로 정렬 하는 구성 요소 목록이 [Visual Studio 2017 작업 및 구성 요소 Id](https://aka.ms/vs2017componentIDs)합니다. 이러한 구성 요소 Id를 사용 하 여 매니페스트에 하 여 필수 구성 요소 Id에 대 한 합니다.

확실 하지 않은 경우 구성 요소를 특정 이진 다운로드를 포함 하는 [구성 요소 이진 매핑 스프레드시트->](https://aka.ms/vs2017componentid-binaries)합니다.

### <a name="vs2017-componentbinarymappingxlsx"></a>vs2017 ComponentBinaryMapping.xlsx

Excel 시트에 4 개의 열이 없는: **구성 요소 이름**, **ComponentId**, **버전**, 및 **이진 / 파일 이름은**합니다.  검색 하 고 특정 구성 요소 및 이진 파일을 찾을에 필터를 사용할 수 있습니다.

모든 참조에 대 한 먼저 핵심 편집기 (Microsoft.VisualStudio.Component.CoreEditor) 구성 요소에서 무엇 인지 확인 합니다.  최소한의 핵심 편집기 구성 요소를 모든 확장에 대 한 필수 조건으로 지정할 필요 합니다. 필터를 추가 하 고 참조 중 남아 있는 코어 편집기에 없는 **이진 파일 / 파일 이름을** 해당 참조의 하위 집합을 포함 하는 구성 요소를 찾을 섹션.

예를 들면 다음과 같습니다.

* 필터 단추를 클릭 디버거 확장이 있고 프로젝트가 VSDebugEng.dll VSDebug.dll에 대 한 참조를 갖고 있을 경우는 **이진 파일 / 파일 이름을** 헤더입니다.  "VSDebugEng.dll" 검색 하 고 확인을 선택 합니다.  필터 단추를 클릭는 **이진 파일 / 파일 이름을** 헤더 다시 고 "VSDebug.dll"를 검색 합니다.  "추가 현재 선택 영역을 필터링" 확인란을 선택 하 고 확인을 선택 합니다.  통해 이제 표시는 **구성 요소 이름을** 가장 하는 구성 요소를 찾으려고 확장 유형과 관련 된 합니다. 이 예제에서는 시간에만 선택한는 디버거를 프로그램 vsixmanifest에 추가 합니다.
* 프로젝트 디버거 요소 다루는 알고 있는 경우 "디버거" 필터 검색 상자에 포함 된 이름에는 디버거 구성 요소 확인을 검색할 수 있습니다.

## <a name="specifying-a-visual-studio-2017-release"></a>Visual Studio 2017 릴리스를 지정합니다.

확장 프로그램이 특정 버전의 Visual Studio 2017이 필요한 경우 예를 들어 15.3에 릴리스된 기능에 종속, 프로그램 VSIX에 빌드 번호를 지정 해야 **InstallationTarget**합니다. 예를 들어, 릴리스 15.3 '15.0.26730.3'의 빌드 번호를 있습니다. 릴리스 빌드 번호를 매핑 나타나면 [여기](../install/visual-studio-build-numbers-and-release-dates.md)합니다. 릴리스 번호 '15.3'를 사용 하 여 제대로 작동 하지 않습니다.

확장 해야 15.3 하거나 선언 합니다 이상 경우는 **InstallationTarget 버전** 으로 [15.0.26730.3, 16.0):

```xml
<Installation>
  <InstallationTarget Id="Microsoft.VisualStudio.Community" Version="[15.0.26730.3, 16.0)" />
</Installation>
```