---
title: Visual Studio 설치에 대한 명령줄 매개 변수 예
description: 이러한 예제를 사용자 지정하여 Visual Studio의 고유한 명령줄 설치를 만듭니다.
ms.date: 05/07/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 837F31AA-F121-46e9-9996-F8BCE768E579
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e011dfd56adeaa832a1925e20e246fb66ce7979
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="command-line-parameter-examples-for-visual-studio-2017-installation"></a>Visual Studio 2017 설치에 대한 명령줄 매개 변수 예

[명령줄 매개 변수를 사용하여 Visual Studio를 설치](use-command-line-parameters-to-install-visual-studio.md)하는 방법을 보여 주기 위해 사용자의 요구에 맞게 사용자 지정할 수 있는 몇 가지 예를 제공합니다.

각 예에서 `vs_enterprise.exe`, `vs_professional.exe` 및 `vs_community.exe`는 다운로드 프로세스를 시작하는 1MB 정도 크기의 작은 파일인 Visual Studio 부트스트래퍼의 해당 버전을 나타냅니다. 다른 버전을 사용하는 경우에는 적절한 부트스트래퍼 이름으로 대체합니다.

> [!NOTE]
> 모든 명령에는 관리자 권한 상승이 필요하며 상승된 프롬프트에서 프로세스가 시작되지 않는 경우 사용자 계정 컨트롤 프롬프트가 표시됩니다.
>
> [!NOTE]
>  명령줄의 끝에 `^` 문자를 사용하여 여러 줄을 하나의 명령으로 연결할 수 있습니다. 또는 이러한 줄을 한꺼번에 단일 행에 배치할 수도 있습니다. PowerShell에서 일치하는 항목은 억음 악센트(`` ` ``) 문자입니다.

## <a name="using---installpath"></a>--installPath 사용

* 대화형 프롬프트 없이 진행률이 표시되는 Visual Studio의 최소 인스턴스를 설치합니다.

 ```cmd
 vs_enterprise.exe --installPath C:\minVS ^
   --add Microsoft.VisualStudio.Workload.CoreEditor ^
   --passive --norestart
 ```

* 대화형 프롬프트 없이 진행률이 표시되는 명령줄을 사용하여 Visual Studio 인스턴스를 업데이트합니다.

 ```cmd
 vs_enterprise.exe --update --quiet --wait
 vs_enterprise.exe update --wait --passive --norestart --installPath "C:\installPathVS"
 ```

 > [!NOTE]
 > 두 명령이 모두 필요합니다. 첫 번째 명령은 Visual Studio 설치 관리자를 업데이트합니다. 두 번째 명령은 Visual Studio 인스턴스를 업데이트합니다. [사용자 계정 컨트롤] 대화 상자를 사용하지 않으려면 명령 프롬프트를 관리자 권한으로 실행합니다.

* 제품을 설치해야만 반환되는 프랑스어 언어 팩을 포함한 Visual Studio의 데스크톱 인스턴스를 자동으로 설치합니다.

 ```cmd
 vs_enterprise.exe --installPath C:\desktopVS ^
   --addProductLang fr-FR ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --includeRecommended --quiet --wait
 ```

 > [!NOTE]
 > `--wait` 매개 변수는 배치 파일에서 사용하도록 설계되었습니다. 배치 파일에서 다음 명령의 실행은 설치가 완료될 때까지 계속되지 않습니다. `%ERRORLEVEL%` 환경 변수는 [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md) 페이지에 나오는 대로 명령의 반환 값을 포함합니다.

## <a name="using---layout"></a>--layout 사용

* Visual Studio 핵심 편집기를 다운로드합니다(최소한의 Visual Studio 구성). 영어 언어 팩만 포함:

 ```cmd
 vs_community.exe --layout C:\VS2017
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.CoreEditor
 ```

* .NET 데스크톱 및 .NET 웹 워크로드를 모든 권장 구성 요소 및 GitHub 확장명과 함께 다운로드합니다. 영어 언어 팩만 포함:

 ```cmd
 vs_community.exe --layout C:\VS2017 ^
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.NetWeb ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --add Component.GitHub.VisualStudio ^
   --includeRecommended
 ```

## <a name="using---includerecommended"></a>--includeRecommended 사용

* Visual Studio 2017 Enterprise Edition에서 사용할 수 있는 모든 워크로드 및 구성 요소의 대화형 설치를 시작합니다.

 ```cmd
 vs_enterprise.exe --all --includeRecommended --includeOptional
 ```

* Node.js 개발 지원을 통해 Visual Studio 2017 Community Edition이 이미 설치된 컴퓨터에 Visual Studio 2017 Professional의 두 번째 명명된 인스턴스를 설치합니다.

 ```cmd
 vs_professional.exe --installPath C:\VSforNode ^
   --add Microsoft.VisualStudio.Workload.Node --includeRecommended --nickname VSforNode
 ```

## <a name="using---remove"></a>--remove 사용

* 기본 설치된 Visual Studio 인스턴스에서 프로파일링 도구 구성 요소를 제거합니다.

 ```cmd
 vs_enterprise.exe modify ^
   --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" ^
   --remove Microsoft.VisualStudio.Component.DiagnosticTools ^
   --passive
 ```

## <a name="using---path"></a>--path 사용

이러한 명령줄 매개 변수는 **15.7의 새로운 기능**입니다. 이에 대한 자세한 내용은 [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md) 페이지를 참조하세요.

* 설치, 캐시 및 공유 경로 사용:

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS" --path cache="C:\VS\cache" --path shared="C:\VS\shared"`

* 설치 및 캐시 경로만 사용:

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS" --path cache="C:\VS\cache"`

* 설치 및 공유 경로만 사용:

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS" --path shared="C:\VS\shared"`

* 설치 경로만 사용:

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS"`

## <a name="get-support"></a>지원 받기

때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지를 참조하세요. 문제 해결 단계가 도움이 되지 않는 경우 라이브 채팅을 통해 Microsoft에 설치 지원을 문의할 수 있습니다(영어만 가능). 자세한 내용은 [Visual Studio 지원 페이지](https://www.visualstudio.com/vs/support/#talktous)를 참조하세요.

몇 가지 추가 지원 옵션은 다음과 같습니다.

* Visual Studio 설치 관리자와 Visual Studio IDE에 모두 표시되는 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 Microsoft에 제품 문제를 보고할 수 있습니다.
* [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 Microsoft와 제품 제안을 공유할 수 있습니다.
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고, 답변을 찾을 수 있습니다.
* [Gitter 커뮤니티의 Visual Studio 관련 대화](https://gitter.im/Microsoft/VisualStudio)를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다. (이 옵션을 사용하려면 [GitHub](https://github.com/) 계정이 필요합니다.)

## <a name="see-also"></a>참고 항목

* [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio 2017의 오프라인 설치 만들기](create-an-offline-installation-of-visual-studio.md)
