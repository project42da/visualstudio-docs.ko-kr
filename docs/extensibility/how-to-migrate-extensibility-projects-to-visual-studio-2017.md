---
title: "방법: Visual Studio 2017 확장성 프로젝트 마이그레이션 | Microsoft 문서"
ms.custom: 
ms.date: 11/09/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ca07b00-a3ff-40ab-b647-c0a93b55e86a
caps.latest.revision: 1
author: gregvanl
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5b6334c38a6c058f274498c06f8e07c934931910
ms.openlocfilehash: efd17a3317302fedcb9bd42aded7a38adee2f75f
ms.lasthandoff: 03/22/2017

---
# <a name="how-to-migrate-extensibility-projects-to-visual-studio-2017"></a>방법: Visual Studio 2017 확장성 프로젝트 마이그레이션

이 문서에서는 Visual Studio 2017를 확장성 프로젝트를 업그레이드 하는 방법을 설명 합니다. 프로젝트 파일을 업데이트 하는 방법을 설명 하는 외에 확장 매니페스트 v2 버전 2 (VSIX)에서 새 버전 3 VSIX 매니페스트 형식 (VSIX v3)로 업그레이드 하는 방법을 설명 합니다.

## <a name="install-visual-studio-2017-with-required-workloads"></a>필요한 작업 부하와 Visual Studio 2017 설치

설치에는 다음과 같은 작업에 포함 되어 있는지 확인 합니다.

* .NET 데스크톱 개발
* Visual Studio 확장 개발

## <a name="open-vsix-solution-in-visual-studio-2017"></a>Visual Studio 2017에서 VSIX 솔루션을 열으십시오

모든 VSIX 프로젝트를 Visual Studio 2017을 지정 하는 주 버전 단방향 업그레이드가 필요 합니다.

프로젝트 파일 (예: *.csproj)을 업데이트 됩니다.

* MinimumVisualStudioVersion-이제 15.0로 설정 합니다.
* OldToolsVersion (하는 경우 이전에 존재)-이제 14.0으로 설정

## <a name="update-the-microsoftvssdkbuildtools-nuget-package"></a>Microsoft.VSSDK.BuildTools NuGet 패키지 업데이트

>**참고:** 솔루션 Microsoft.VSSDK.BuildTools NuGet 패키지를 참조 하지 않으면,이 단계를 건너뛸 수 있습니다.

새 VSIX v 3에서 확장 프로그램을 빌드하려면 (버전 3) 형식으로 새 VSSDK 빌드 도구를 사용 하 여 빌드한 수 하는 솔루션을 해야 합니다. Visual Studio 2017 년으로 설치 됩니다 하지만 VSIX v2 확장 NuGet 통해 이전 버전에 대 한 참조를 보유할 수 있습니다. 그렇다면 Microsoft.VSSDK.BuildTools NuGet 패키지를 솔루션에 대 한 업데이트를 수동으로 설치 해야 합니다.

NuGet을 업데이트 하려면 Microsoft.VSSDK.BuildTools 참조 합니다.

* 솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **솔루션에 대 한 NuGet 패키지 관리...**
* 탐색 하는 **업데이트** 탭 합니다.
* Microsoft.VSSDK.BuildTools (최신 버전)를 선택 합니다.
* 키를 눌러 **업데이트**합니다.

![VSSDK 빌드 도구](media/vssdk-build-tools.png)

## <a name="make-changes-to-the-vsix-extension-manifest"></a>VSIX 확장 매니페스트를 변경

사용자의 Visual Studio 설치에서 확장을 실행 하는 데 필요한 모든 어셈블리를 갖도록 확장 매니페스트 파일에 모든 필수 구성 요소 또는 패키지를 지정 합니다. 사용자가 확장을 설치 하려고는 VSIXInstaller 확인 모든 필수 구성 요소는 설치 되어 있는지 확인 합니다. 일부 값이 없는 경우 사용자는 확장 설치 과정의 일환으로 누락 된 구성 요소를 설치 하 라는 메시지가 표시 됩니다.

>**참고:** 여기에 최소한 모든 확장으로 지정 해야 Visual Studio core 편집기 구성 요소의 필수 구성 요소입니다.

* 확장 매니페스트 파일 (일반적으로 source.extension.vsixmanifest 이라고 함)을 편집 합니다.
* 확인 `InstallationTarget` 15.0 포함 됩니다.
* 아래 예제에서는 같이 필요한 설치 필수 구성 요소를 추가 합니다.
  * 설치 필수 구성 요소에 대 한 구성 요소 Id를 지정 하는 것이 좋습니다.
  * 이 문서의 끝에 있는 섹션을 참조 하십시오 [식별 하는 구성 요소 Id에 대 한 지침](#finding-component-ids)합니다.

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

### <a name="option-use-the-designer-to-make-changes-to-the-vsix-extension-manifest"></a>옵션: 디자이너를 사용 하 여 VSIX 확장 매니페스트를 변경 하려면

매니페스트 XML을 직접 편집 하는 대신 사용할 수 있습니다 새 **필수 구성 요소** XML 필수 구성 요소를 선택 하는 매니페스트 디자이너의 탭 수에 대 한 업데이트 됩니다.

>**참고:** 매니페스트 디자이너만 하면 (작업 부하 또는 패키지) 설치 된 구성 요소는 현재 Visual Studio 인스턴스에 선택할 수 있습니다. 작업, 패키지 또는 현재 설치 되어 있지 않은 구성 요소에 대 한 필수 구성 요소를 추가 해야 하는 경우 직접 XML 매니페스트를 편집 합니다.

* [디자인] source.extension.vsixmanifest 파일을 엽니다.
* 선택 **필수 구성 요소** 탭 및 키를 눌러 **새로** 단추입니다.

  ![VSIX 매니페스트 디자이너](media/vsix-manifest-designer.png)

* **추가 새 필수 구성 요소** 창이 열립니다.

  ![vsix 필수 구성 요소를 추가 합니다.](media/add-vsix-prerequisite.png)

* 에 대 한 드롭다운 목록에서 클릭 **이름** 하 고 원하는 필수 구성 요소를 선택 합니다.
* 필요한 경우에 버전을 업데이트 합니다.

  >참고: 버전 필드는 최대 범위에 걸쳐 (포함 하지 않음)와 현재 설치 된 구성 요소를 미리 채울 수는 구성 요소의 다음 주 버전입니다.

  ![roslyn 필수 구성 요소를 추가 합니다.](media/add-roslyn-prerequisite.png)

* Press **OK**.

## <a name="if-migrating-from-preview-4-or-preview-5"></a>미리 보기 4 또는 5 미리 보기에서 마이그레이션하는 경우

* 대체 `SetupDependencies` 와 `Prerequisites` 의 요소를 이동 하 고는 `Installer` 요소입니다. `Prerequisites`직접 안쪽에 배치 되어 이제는 `PackageManifest` 요소입니다.
* [옵션] 제거는 `GenerateVsixV3` 요소입니다. (이 된 5 미리 보기에에서만 필요 합니다.) `GenerateVsixV3` 요소는 미리 보기 5 이상 버전에서 무시 됩니다.

## <a name="update-debug-settings-for-project"></a>프로젝트에 대 한 디버그 설정을 업데이트 합니다.

Visual Studio의 실험적 인스턴스에서 확장 프로그램을 디버깅 하려는 경우 다음 사항을 확인에 대 한 프로젝트 설정 **디버그** > **시작 작업** 에 **시작 외부 프로그램:** 값 devenv.exe 파일에서는 Visual Studio 2017 설치로 설정 합니다.

것 같습니다.

```
C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\devenv.exe
```

![시작 외부 프로그램](media/start-external-program.png)

>**참고:** 디버그 시작 작업은 일반적으로에 저장 되는. csproj.user 파일입니다. 이 파일은 일반적으로.gitignore 파일에 포함 되어 있으며, 따라서 일반적으로 함께 저장 되지 않습니다 소스 제어 하고자 하는 경우 다른 프로젝트 파일. 따라서 솔루션에 소스 제어에서 새가 가져오는 경우 되었을 프로젝트 시작 작업에 대 한 설정 값을 갖습니다. 새 VSIX 프로젝트를 Visual Studio 2017를 사용 하 여 만든 것을. 현재 Visual Studio 설치 디렉터리를 가리키는 기본값을 사용 하 여 만든 csproj.user 파일입니다. 그러나 VSIX v2 확장을 마이그레이션하는 경우 가능성이 하에서. csproj.user 파일에는 이전 Visual Studio 버전의 설치 디렉터리에 대 한 참조가 포함 됩니다. 값을 설정 **디버그** > **시작 작업** 확장 프로그램을 디버깅 하려고 할 때 실행 하는 올바른 Visual Studio 실험적 인스턴스를 허용 합니다.

## <a name="check-that-the-extension-builds-correctly-as-a-vsix-v3"></a>확장 (것으로 잘못 VSIX v3) 빌드 되었는지 확인 하십시오.

* VSIX 프로젝트를 빌드하십시오.
* 생성 된 VSIX를 압축을 풉니다.
  * 기본적으로 VSIX 파일 삶을 안에 bin/Debug 또는 bin/Release [YourCustomExtension].vsix로 합니다.
  * .Vsix를.zip 내용을 쉽게 확인 하 고 이름을 바꿉니다.
* 세 개의 파일이 있는지 확인 합니다.
  * extension.vsixmanifest
  * manifest.json
  * catalog.json

## <a name="check-when-all-required-prerequisites-are-installed"></a>필요한 모든 필수 구성 요소가 설치 될 때 검사

VSIX 필요한 모든 필수 구성 요소가 설치 된 컴퓨터에서 성공적으로 설치 하는 테스트입니다.

>**참고:** 모든 확장을 설치 하기 전에 Visual Studio의 모든 인스턴스를 종료 하십시오.

확장을 설치 하려고 합니다.

* Visual Studio 2017에

![Visual Studio 2017에서 VSIX 설치 관리자](media/vsixinstaller-vs-2017.png)

* 선택 사항: 이전 버전의 Visual Studio를 확인 합니다.
  * 이전 버전과 호환성을 증명합니다.
  * Visual Studio 2012, Visual Studio 2013, Visual Studio 2015에 대해 작동 합니다.
* 선택 사항: VSIX 설치 관리자 버전 검사 버전 중 하나를 선택할 수 있는지 확인 합니다.
  * (설치) 하는 경우에 이전 버전의 Visual Studio에 포함 됩니다.
  * Visual Studio 2017 포함 되어 있습니다.

Visual Studio 최근에 열려 있으면 다음과 같은 대화 상자가 나타날 수 있습니다.

![프로세스를 실행 하는 vs](media/vs-running-processes.png)

프로세스 종료를 표시 될 때까지 기다리거나 작업을 수동으로 종료 합니다. 나열 된 이름 또는 PID 괄호 안에 나열 된 프로세스를 찾을 수 있습니다.

>**참고:** 이러한 프로세스는 종료 되지 않습니다 자동으로 Visual Studio의 인스턴스로 실행 되는 동안. -포함 하 여 다른 사용자의 컴퓨터에 Visual Studio의 모든 인스턴스를 종료 한 후 다시 시도 하 함을 확인 합니다.

## <a name="check-when-missing-the-required-prerequisites"></a>필요한 필수 구성 요소를 누락 하는 경우를 확인 합니다.

* 확장을 설치 하는 컴퓨터에 Visual Studio 2017 해당 하지 않는 포함 된 필수 구성 요소 (위 참조)에 정의 된 모든 구성 요소 시도 합니다.
* 설치가 누락 된 구성 요소/s를 식별 하는 VSIXInstaller 시 필수 구성 요소로 나열 하는지 확인 합니다.
* 참고: 모든 필수 구성 요소 확장으로 설치 해야 할 경우 권한 상승이 필요한 됩니다 있습니다.

![vsixinstaller 누락 된 필수 구성 요소](media/vsixinstaller-missing-prerequisite.png)

## <a name="deciding-on-components"></a>구성 요소 결정

종속성을 조회할 때 여러 구성 요소를 한 종속성을 매핑할 수 있는지를 찾을 수 있습니다. 종속성을 확인 하려면에 비슷한 기능을 확장 하는 구성 요소를 선택 하 고도 사용자 및 어떤 유형의 구성 요소를 고려해 야 할 가능성이 설치한 프로그램 필수 구성 요소로 지정 해야 하거나 설치 상관이 없습니다. 또한 확장에 필요한 필수 구성 요소, 확장을 실행할 수 있는 최소만을 충족 하는 방법 및 추가 기능에 대 한 특정 구성 요소는 검색 되지 않는 경우에 유휴 상태로 들 건물을 권장 합니다.

추가 지침을 제공 하려면 몇 가지 일반적인 확장 프로그램 유형 및 해당 제안 된 필수 구성 요소 확인 하였습니다.

확장 형식 | 표시 이름 |    ID
--- | --- | ---
편집기 | Visual Studio core 편집기    | Microsoft.VisualStudio.Component.CoreEditor
Roslyn | C# 및 Visual Basic | Microsoft.VisualStudio.Component.Roslyn.LanguageServices
WPF | 관리 되는 데스크톱 작업 코어 | Microsoft.VisualStudio.Component.ManagedDesktop.Core
디버거 | 적시에 디버거 | Microsoft.VisualStudio.Component.Debugger.JustInTime

## <a name="finding-component-ids"></a>구성 요소 Id 찾기

Visual Studio 제품으로 정렬 하는 구성 요소 목록에는 [Visual Studio 2017 작업 부하 및 구성 요소 Id](https://aka.ms/vs2017componentIDs)합니다. 매니페스트에 트 필수 구성 요소 Id에 대 한 이러한 구성 요소 Id를 사용 합니다.

확실 하지 않은 경우 구성 요소를 특정 이진 다운로드를 포함 하는 [-> 이진 매핑 스프레드시트 구성 요소](https://aka.ms/vs2017componentid-binaries)합니다.

### <a name="vs2017-componentbinarymappingxlsx"></a>vs2017 ComponentBinaryMapping.xlsx

Excel 시트에&4; 개의 열이: **구성 요소 이름**, **ComponentId**, **버전**, 및 **이진 / 파일 이름을**합니다.  검색 하 고 특정 구성 요소와 이진 파일을 찾을에 필터를 사용할 수 있습니다.

에 대 한 모든 참조를 먼저 코어 편집기 (Microsoft.VisualStudio.Component.CoreEditor) 구성 요소에서 무엇 인지 확인 합니다.  최소한의 핵심 편집기 구성 요소를 모든 확장에 대 한 전제 조건으로 지정할 필요 합니다. 참조가 남아 있는 코어 편집기에 있지 않은에서 필터를 추가할는 **이진 파일 / 파일 이름을** 해당 참조의 하위 집합 중 하나라도 있는 구성 요소를 찾을 섹션입니다.

예를 들면 다음과 같습니다.

* 디버거 확장을 한 프로젝트에 VSDebugEng.dll VSDebug.dll에 대 한 참조를 알고 있는 경우에 필터 단추를 클릭는 **이진 파일 / 파일 이름을** 헤더입니다.  "VSDebugEng.dll"를 검색 하 고 확인을 선택 합니다.  그런 다음 필터 단추를 클릭는 **이진 파일 / 파일 이름** 다시 머리글과 "VSDebug.dll"를 검색 합니다.  "추가 현재 선택 영역을 필터링" 확인란을 선택 하 고 확인을 선택 합니다.  이제을 통해 표시는 **구성 요소 이름** 가장 하는 구성 요소를 찾으려고 확장 유형과 관련 된. 이 예제에서는 시간에만 선택한 것 디버거 vsixmanifest 프로그램에 추가 합니다.
* 디버거 요소 다루는 프로젝트를 알고 있는 경우 "디버거에서" 필터 검색 상자에 이름에는 디버거를 포함 하는 구성 요소를 검색할 수 있습니다.

