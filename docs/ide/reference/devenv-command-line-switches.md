---
title: Visual Studio Devenv 명령줄 스위치 | Microsoft Docs
ms.date: 02/28/2018
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- switches, Devenv
- command-line switches, Devenv
- command line [Visual Studio], switches
- Devenv
ms.assetid: e12bc6ed-74fd-4bea-8d7c-89b99c20bad8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3adde520b76de347da025c819ec39dce50660f2b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="devenv-command-line-switches"></a>Devenv 명령줄 스위치

Devenv를 사용하면 IDE(통합 개발 환경)에 대한 다양한 옵션을 설정할 뿐만 아니라 명령줄에서 프로젝트를 빌드, 디버그 및 배포할 수도 있습니다. 이러한 스위치를 사용하여 스크립트 또는 .bat 파일(예: 야간 빌드 스크립트)에서 IDE를 실행하거나 특정 구성으로 IDE를 시작할 수 있습니다.

> [!NOTE]
> 빌드 관련 작업의 경우 devenv 대신 MSBuild를 사용하는 것이 좋습니다. 자세한 내용은 [MSBuild 명령줄 참조](../../msbuild/msbuild-command-line-reference.md)를 참조하세요.

## <a name="devenv-switch-syntax"></a>Devenv 스위치 구문

기본적으로 devenv 명령은 devenv.com 유틸리티에 스위치를 전달합니다. devenv.com 유틸리티는 `stdout` 및 `stderr`와 같은 표준 시스템 스트림을 통해 출력을 제공합니다. 유틸리티는 출력을 캡처할 때 적절한 I/O 리디렉션을 결정합니다(예: .txt 파일).

반면에 `devenv.exe`로 시작하는 명령은 동일한 스위치를 사용할 수 있지만 devenv.com 유틸리티는 무시됩니다.

`devenv` 스위치의 구문 규칙은 다른 DOS 명령줄 유틸리티의 구문 규칙과 비슷합니다. 다음 구문 규칙은 모든 `devenv` 스위치 및 해당 인수에 적용됩니다.

- 명령이 `devenv`로 시작합니다.

- 스위치가 대/소문자를 구분하지 않습니다.

- 솔루션 또는 프로젝트를 지정하는 경우 첫 번째 인수는 파일 경로를 포함하여 솔루션 파일 또는 프로젝트 파일의 이름입니다.

- 첫 번째 인수가 솔루션 또는 프로젝트가 아닌 파일인 경우 해당 파일이 새 IDE 인스턴스의 적절한 편집기에서 열립니다.

- 솔루션 파일 이름 대신 프로젝트 파일 이름을 제공하는 경우 `devenv` 명령은 프로젝트 파일의 부모 폴더에서 이름이 같은 솔루션 파일을 검색합니다. 예를 들어 `devenv /build myproject1.vbproj` 명령은 부모 폴더에서 이름이 "myproject1.sln"인 솔루션 파일을 검색합니다.

    > [!NOTE]
    > 이 프로젝트를 참조하는 솔루션 파일 하나만 해당 부모 폴더에 있어야 합니다. 부모 폴더에 이 프로젝트를 참조하는 솔루션 파일이 없거나 두 개 이상 있는 경우 임시 솔루션 파일이 생성됩니다.

- 파일 경로 및 파일 이름에 공백이 포함된 경우 큰따옴표("")로 묶어야 합니다. 예를 들어 "c:\project a\\"입니다.

- 동일한 줄에 있는 스위치와 인수 사이에 공백 문자를 하나 삽입합니다. 예를 들어 **devenv /log output.txt** 명령은 IDE를 열고 해당 세션에 대한 모든 로그 정보를 output.txt에 출력합니다.

- `devenv` 명령에서는 패턴 일치 구문을 사용할 수 없습니다.

## <a name="devenv-switches"></a>Devenv 스위치

다음 명령줄 스위치는 IDE를 표시하고 설명된 작업을 수행합니다.

|명령줄 스위치|설명|
|-------------------------|-----------------|
|[/Command](../../ide/reference/command-devenv-exe.md)|IDE를 시작하고 지정한 명령을 실행합니다.|
|[/DebugExe](../../ide/reference/debugexe-devenv-exe.md)|디버거의 제어로 C++ 실행 파일을 로드합니다. 이 스위치는 Visual Basic 또는 C# 실행 파일에 제공되지 않습니다. 자세한 내용은 [디버거에서 자동으로 프로세스 시작](../../debugger/debug-multiple-processes.md#BKMK_Automatically_start_an_process_in_the_debugger)을 참조하세요.|
|[/LCID 또는 /l](../../ide/reference/lcid-devenv-exe.md)|IDE의 기본 언어를 설정합니다. 지정한 언어가 Visual Studio 설치에 포함되어 있지 않은 경우 이 설정은 무시됩니다.|
|[/Log](../../ide/reference/log-devenv-exe.md)|Visual Studio를 시작하고 모든 작업을 로그 파일에 기록합니다.|
|[/Run 또는 /r](../../ide/reference/run-devenv-exe.md)|지정한 솔루션을 컴파일하고 실행합니다.|
|[/Runexit](../../ide/reference/runexit-devenv-exe.md)|지정한 솔루션을 컴파일 및 실행하고, 솔루션 실행 시 IDE를 최소화하고, 솔루션 실행이 완료되면 IDE를 닫습니다.|
|[/UseEnv](../../ide/reference/useenv-devenv-exe.md)|IDE가 **옵션** 대화 상자에 있는 **프로젝트** 옵션의 VC++ 디렉터리 섹션에 지정된 설정 대신 PATH, INCLUDE 및 LIB 환경 변수를 C++ 컴파일에 사용하도록 합니다. **C++ 워크로드로 데스크톱 개발**을 사용하여 이 스위치를 설치합니다. 자세한 내용은 [명령줄 빌드에서 경로 및 환경 변수 설정](/cpp/build/setting-the-path-and-environment-variables-for-command-line-builds)을 참조하세요.|
|[/Edit](../../ide/reference/edit-devenv-exe.md)|이 응용 프로그램의 실행 중인 인스턴스에서 지정한 파일을 엽니다. 실행 중인 인스턴스가 없으면 간단한 창 레이아웃을 사용하여 새 인스턴스를 시작합니다.|
|[/SafeMode](../../ide/reference/safemode-devenv-exe.md)|안전 모드로 Visual Studio를 시작하고 기본 환경 및 서비스와 타사 패키지의 배송된 버전만 로드합니다.|
|[/ResetSkipPkgs](../../ide/reference/resetskippkgs-devenv-exe.md)|문제 VSPackage를 로드하지 않으려는 사용자가 VSPackage에 추가한 SkipLoading 태그를 모두 지웁니다.|
|[/Setup](../../ide/reference/setup-devenv-exe.md)|Visual Studio가 사용 가능한 모든 VSPackage에서 메뉴, 도구 모음 및 명령 그룹을 설명하는 리소스 메타데이터를 강제로 병합하도록 합니다. 관리자 권한으로 이 명령을 실행해야 합니다.|

다음 명령줄 스위치는 IDE를 표시하지 않습니다.

|명령줄 스위치|설명|
|-------------------------|-----------------|
|[/?](../../ide/reference/q-devenv-exe.md)|**명령 프롬프트 창**에 devenv 스위치에 대한 도움말을 표시합니다.<br /><br /> **Devenv /?**|
|[/Build](../../ide/reference/build-devenv-exe.md)|지정한 솔루션의 구성에 따라 지정한 솔루션 또는 프로젝트를 빌드합니다.<br /><br /> **Devenv myproj.csproj /build**|
|[/Clean](../../ide/reference/clean-devenv-exe.md)|소스 파일에 영향을 주지 않고 빌드 명령에 의해 생성된 파일을 삭제합니다.<br /><br /> **Devenv myproj.csproj /clean**|
|[/Deploy](../../ide/reference/deploy-devenv-exe.md)|솔루션 구성에 따라 배포에 필요한 파일과 함께 솔루션을 빌드합니다.<br /><br /> **Devenv myproj.csproj /deploy**|
|[/Diff](../../ide/reference/diff.md)|두 파일을 비교합니다. SourceFile, TargetFile, SourceDisplayName(선택 사항), TargetDisplayName(선택 사항)이라는 네 개의 매개 변수를 사용합니다.|
|[/Out](../../ide/reference/out-devenv-exe.md)|빌드 시 오류를 받을 파일을 지정할 수 있습니다.<br /><br /> **Devenv myproj.csproj /build /out log.txt**|
|[/Project](../../ide/reference/project-devenv-exe.md)|빌드, 정리 또는 배포할 프로젝트입니다. /build, /rebuild, /clean 또는 /deploy 스위치도 제공한 경우에만 이 스위치를 사용할 수 있습니다.|
|[/ProjectConfig](../../ide/reference/projectconfig-devenv-exe.md)|빌드 또는 배포할 프로젝트 구성을 지정합니다. /project 스위치도 제공한 경우에만 이 스위치를 사용할 수 있습니다.|
|[/Rebuild](../../ide/reference/rebuild-devenv-exe.md)|지정한 솔루션의 구성에 따라 지정한 솔루션 또는 프로젝트를 정리한 후 빌드합니다.|
|[/ResetSettings](../../ide/reference/resetsettings-devenv-exe.md)|Visual Studio 기본 설정을 복원합니다. 필요에 따라 설정을 지정한 .vssettings 파일로 초기화합니다.|
|[/Upgrade](../../ide/reference/upgrade-devenv-exe.md)|지정한 솔루션 파일 및 모든 프로젝트 파일이나 지정한 프로젝트 파일을 이러한 파일의 현재 Visual Studio 형식으로 업그레이드합니다.|

## <a name="see-also"></a>참고 항목

* [옵션 대화 상자, 환경, 일반](../../ide/reference/general-environment-options-dialog-box.md)