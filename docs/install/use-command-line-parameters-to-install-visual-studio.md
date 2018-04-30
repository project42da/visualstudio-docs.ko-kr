---
title: 명령줄 매개 변수를 사용하여 Visual Studio 설치
description: 명령줄 매개 변수를 사용하여 Visual Studio 설치를 제어하거나 사용자 지정하는 방법을 알아봅니다.
ms.custom: ''
ms.date: 01/17/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- command-line parameters
- switches
- command prompt
ms.assetid: 480f3cb4-d873-434e-a8bf-82cff7401cf2
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 566e662c55589424f04e93d0dd182faed8a4b757
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="use-command-line-parameters-to-install-visual-studio-2017"></a>명령줄 매개 변수를 사용하여 Visual Studio 2017 설치

명령 프롬프트에서 Visual Studio 2017를 설치할 때 다양한 명령줄 매개 변수를 사용하여 설치를 제어하거나 사용자 지정할 수 있습니다. 명령줄에서 다음 작업을 수행할 수 있습니다.

- 특정 옵션이 미리 선택된 상태로 설치를 시작합니다.
- 설치 프로세스를 자동화합니다.
- 나중에 사용할 설치 파일의 캐시(레이아웃)를 만듭니다.

명령줄 옵션은 다운로드 프로세스를 시작하는 작은(약 1MB) 파일인 설치 부트스트래퍼와 함께 사용됩니다. 부트스트래퍼는 Visual Studio 사이트에서 다운로드할 때 첫 번째로 실행되는 실행 파일입니다. 다음 링크를 사용하여 설치 중인 제품 버전에 대한 최신 릴리스 부트스트래퍼에 직접 연결된 링크를 가져옵니다.

* [Visual Studio 2017 Enterprise](https://aka.ms/vs/15/release/vs_enterprise.exe)
* [Visual Studio 2017 Professional](https://aka.ms/vs/15/release/vs_professional.exe)
* [Visual Studio 2017 Community](https://aka.ms/vs/15/release/vs_community.exe)

## <a name="list-of-command-line-parameters"></a>명령줄 매개 변수 목록

 Visual Studio 명령줄 매개 변수는 대/소문자를 구분하지 않습니다.

> 구문: `vs_enterprise.exe [command] <options>...`

(설치 중인 제품 버전에 적합하게 `vs_enterprise.exe`를 바꿉니다.)

>[!TIP]
> 명령줄을 사용하여 Visual Studio 2017을 설치하는 방법에 대한 자세한 예제는 [명령줄 매개 변수 예제](command-line-parameter-examples.md) 페이지를 참조하세요.

| **명령** | **설명** |
| ----------------------- | --------------- |
| (비어 있음) | 제품을 설치합니다. |
| `modify` | 설치된 제품을 수정합니다. |
| `update` | 설치된 제품을 업데이트합니다. |
| `repair` | 설치된 제품을 복구합니다. |
| `uninstall` | 설치된 제품을 제거합니다. |

| **설치 옵션** | **설명** |
| ----------------------- | --------------- |
| `--installPath <dir>` | 작업할 인스턴스에 대한 설치 디렉터리입니다. 설치 명령의 경우 이 디렉터리는 **선택 사항**이고 인스턴스가 설치될 위치입니다. 다른 명령의 경우 이 디렉터리는 **필수**이고 이전에 설치한 인스턴스가 설치된 위치입니다. |
| `--addProductLang <language-locale>` | **선택 사항**: 설치 또는 수정 작업을 하는 동안 제품에 설치되는 UI 언어 팩을 결정합니다. 여러 언어 팩을 추가하려면 명령줄에 여러 번 나타날 수 있습니다. 없는 경우 설치에 컴퓨터 로캘이 사용됩니다. 자세한 내용은 이 페이지의 [언어 로캘 목록](#list-of-language-locales) 섹션을 참조하세요.|
| `--removeProductLang <language-locale>` | **선택 사항**: 설치 또는 수정 작업을 하는 동안 제품에서 제거할 UI 언어 팩을 결정합니다. 여러 언어 팩을 추가하려면 명령줄에 여러 번 나타날 수 있습니다. 자세한 내용은 이 페이지의 [언어 로캘 목록](#list-of-language-locales) 섹션을 참조하세요.|
| `--add <one or more workload or component IDs>` | **선택 사항**: 추가할 하나 이상의 작업 또는 구성 요소 ID입니다. 아티팩트의 필수 구성 요소가 설치되지만 권장 또는 선택적 구성 요소는 설치되지 않습니다. `--includeRecommended` 및/또는 `--includeOptional`을 사용하여 추가 구성 요소를 전체적으로 제어할 수 있습니다. 더 세부적으로 제어하기 위해 `;includeRecommended` 또는 `;includeOptional`을 ID에 추가할 수 있습니다(예: `--add Workload1;includeRecommended` 또는 `--add Workload2;includeRecommended;includeOptional`). 자세한 내용은 [작업 및 구성 요소 ID](workload-and-component-ids.md) 페이지를 참조하세요. 필요에 따라 이 옵션을 반복할 수 있습니다.|
| `--remove <one or more workload or component IDs>` | **선택 사항**: 제거할 하나 이상의 작업 또는 구성 요소 ID입니다. 자세한 내용은 [작업 및 구성 요소 ID](workload-and-component-ids.md) 페이지를 참조하세요. 필요에 따라 이 옵션을 반복할 수 있습니다.|
| `--in <path>` | **선택 사항**: 응답 파일의 URI 또는 경로입니다.  |
| `--all` | **선택 사항**: 제품에 대한 모든 작업 및 구성 요소를 설치할지의 여부입니다. |
| `--allWorkloads` | **선택 사항**: 모든 워크로드 및 구성 요소를 설치하고, 권장 또는 선택적 구성 요소는 설치하지 않습니다. |
| `--includeRecommended` | **선택 사항**: 설치된 모든 작업에 대한 권장 구성 요소를 포함하지만, 선택적 구성 요소는 포함하지 않습니다. 워크로드는 `--allWorkloads` 또는 `--add`를 사용하여 지정됩니다. |
| `--includeOptional` | **선택 사항**: 설치된 모든 작업에 대한 선택적 구성 요소를 포함하지만, 권장 구성 요소는 포함하지 않습니다. 워크로드는 `--allWorkloads` 또는 `--add`를 사용하여 지정됩니다.  |
| `--quiet, -q` | **선택 사항**: 설치를 수행하는 동안 사용자 인터페이스를 표시하지 않습니다. |
| `--passive, -p` | **선택 사항**: 사용자 인터페이스를 표시하지만 사용자 조작을 요청하지 않습니다. |
| `--norestart` | **선택 사항**: 이 옵션이 있는 경우 `--passive` 또는 `--quiet`가 포함된 명령은 컴퓨터를 자동으로 다시 시작하지 않습니다(필요한 경우).  `--passive` 및 `--quiet`가 지정되지 않은 경우에는 무시됩니다.  |
| `--nickname <name>` | **선택 사항**: 설치된 제품에 할당할 애칭을 정의합니다. 애칭은 10자를 초과할 수 없습니다.  |
| `--productKey` | **선택 사항**: 설치된 제품에 사용할 제품 키를 정의합니다. 제품 키는 `xxxxx-xxxxx-xxxxx-xxxxx-xxxxx` 또는 `xxxxxxxxxxxxxxxxxxxxxxxxx` 형식의 영숫자 25자로 구성됩니다. |
| `--help, --?, -h, -?` | 이 페이지의 오프라인 버전을 표시합니다. |

> 참고: 여러 워크로드와 구성 요소를 지정할 경우 각 항목에 대해 `--add` 또는 `--remove` 명령줄 스위치를 반복해야 합니다.

| **레이아웃 옵션** | **설명** |
| ----------------------- | --------------- |
| `--layout <dir>` | 오프라인 설치 캐시를 만들 디렉터리를 지정합니다. 자세한 내용은 [Visual Studio의 네트워크 기반 설치 만들기](create-a-network-installation-of-visual-studio.md)를 참조하세요.|
| `--lang <one or more language-locales>` | **선택 사항**: `--layout`과 함께 사용하여 지정된 언어의 리소스 패키지와 함께 오프라인 설치 캐시를 준비합니다. 자세한 내용은 이 페이지의 [언어 로캘 목록](#list-of-language-locales) 섹션을 참조하세요.|
| `--add <one or more workload or component IDs>` | **선택 사항**: 추가할 하나 이상의 작업 또는 구성 요소 ID입니다. 아티팩트의 필수 구성 요소가 설치되지만 권장 또는 선택적 구성 요소는 설치되지 않습니다. `--includeRecommended` 및/또는 `--includeOptional`을 사용하여 추가 구성 요소를 전체적으로 제어할 수 있습니다. 더 세부적으로 제어하기 위해 `;includeRecommended` 또는 `;includeOptional`을 ID에 추가할 수 있습니다(예: `--add Workload1;includeRecommended` 또는 `--add Workload2;includeOptional`). 자세한 내용은 [작업 및 구성 요소 ID](workload-and-component-ids.md) 페이지를 참조하세요. <br/>**참고**: `--add`를 사용하면 지정된 워크로드 및 구성 요소와 해당 종속성이 다운로드됩니다. `--add`가 지정되지 않으면 모든 워크로드 및 구성 요소가 레이아웃에 다운로드됩니다.|
| `--includeRecommended` | **선택 사항**: 설치된 모든 작업에 대한 권장 구성 요소를 포함하지만, 선택적 구성 요소는 포함하지 않습니다. 워크로드는 `--allWorkloads` 또는 `--add`를 사용하여 지정됩니다. |
| `--includeOptional` | **선택 사항**: 레이아웃에 포함되는 모든 워크로드에 대한 권장 *및* 선택적 명령을 포함합니다. 워크로드는 `--add`를 사용하여 지정됩니다.  |
| `--keepLayoutVersion` | **15.3의 새로운 기능, 선택 사항**: 레이아웃의 버전을 업데이트하지 않고 레이아웃에 변경 내용을 적용합니다. |
| `--verify` | **15.3의 새로운 기능, 선택 사항**: 레이아웃의 콘텐츠를 확인합니다.  손상되거나 누락된 파일이 모두 나열됩니다. |
| `--fix` | **15.3의 새로운 기능, 선택 사항**: 레이아웃의 콘텐츠를 확인합니다.  손상되거나 누락된 파일이 있는 경우 다시 다운로드됩니다.  레이아웃을 수정하려면 인터넷 액세스가 필요합니다. |
| `--clean <one or more paths to catalogs>` | **15.3의 새로운 기능, 선택 사항**: 최신 버전으로 업데이트된 레이아웃에서 이전 버전의 구성 요소를 제거합니다. |

| **고급 설치 옵션** | **설명** |
| ----------------------- | --------------- |
| `--channelId <id>` | **선택 사항**: 설치할 인스턴스의 채널 ID입니다. 설치 명령에 필요하며, `--installPath`가 지정된 경우 다른 명령에서는 무시됩니다. |
| `--channelUri <uri>` | **선택 사항**: 채널 매니페스트의 URI입니다. 업데이트가 필요하지 않으면 `--channelUri`는 존재하지 않는 파일을 가리킬 수 있습니다. 예를 들어 --channelUri C:\doesntExist.chman과 같습니다. 이 옵션은 install 명령에 사용할 수 있으며, 다른 명령에서는 무시됩니다. |
| `--installChannelUri <uri>` | **선택 사항**: 설치에 사용할 채널 매니페스트의 URI입니다. `--channelUri`(`--installChannelUri`가 지정된 경우 지정해야 함)로 지정된 URI는 업데이트를 검색하는 데 사용됩니다. 설치 명령에 사용할 수 있습니다. 다른 명령에서는 무시됩니다. |
| `--installCatalogUri <uri>` | **선택 사항**: 설치에 사용할 카탈로그 매니페스트의 URI입니다. 지정된 경우 채널 관리자는 설치 채널 매니페스트의 URI를 사용하기 전에 이 URI에서 카탈로그 매니페스트를 다운로드하려고 합니다. 이 매개 변수는 이미 다운로드한 제품 카탈로그를 사용하여 레이아웃 캐시가 생성되는 오프라인 설치를 지원하는 데 사용됩니다. 설치 명령에 사용할 수 있습니다. 다른 명령에서는 무시됩니다. |
| `--productId <id>` | **선택 사항**: 설치할 인스턴스에 대한 제품 ID입니다. 이는 일반적인 설치 조건에서 미리 채워져 있습니다. |
| `--wait` | **선택 사항**: 프로세스에서 설치가 완료될 때까지 기다린 후에 종료 코드를 반환합니다. 이 기능은 설치의 반환 코드를 처리하기 위해 설치가 완료할 때까지 기다려야 하는 설치를 자동화할 경우 유용합니다. |
| `--locale <language-locale>` | **선택 사항**: 설치 관리자의 사용자 인터페이스 표시 언어를 변경합니다. 설정은 유지됩니다. 자세한 내용은 이 페이지의 [언어 로캘 목록](#list-of-language-locales) 섹션을 참조하세요.|
| `--cache` | **15.2의 새로운 기능, 선택 사항**: 있는 경우 패키지가 이후 복구를 위해 설치된 후에도 유지됩니다. 이는 이후 설치, 복구 또는 수정에 사용할 전역 정책 설정을 재정의합니다. 기본 정책은 패키지를 캐시하는 것입니다. 제거 명령의 경우 무시됩니다. 자세한 내용은 [패키지 캐시를 사용하지 않도록 설정 또는 이동](disable-or-move-the-package-cache.md)하는 방법을 참조하세요. |
| `--nocache` | **15.2의 새로운 기능, 선택 사항**: 패키지가 있는 경우 설치 또는 복구된 후에 삭제됩니다. 필요한 경우에만 다시 다운로드되고 사용한 후 다시 삭제됩니다. 이는 이후 설치, 복구 또는 수정에 사용할 전역 정책 설정을 재정의합니다. 기본 정책은 패키지를 캐시하는 것입니다. 제거 명령의 경우 무시됩니다. 자세한 내용은 [패키지 캐시를 사용하지 않도록 설정 또는 이동](disable-or-move-the-package-cache.md)하는 방법을 참조하세요. |
| `--noUpdateInstaller` | **15.2의 새로운 기능, 선택 사항**: 있는 경우 quiet가 지정되었으면 설치 프로그램이 자기 자신을 업데이트하지 않습니다. quiet와 함께 noUpdateInstaller가 지정되었는데 설치 프로그램 업데이트가 필요한 경우 설치 프로그램에서 명령을 실패로 처리하고 0이 아닌 종료 코드를 반환합니다. |
| `--noWeb` | **15.3의 새로운 기능, 선택 사항**: 설치 프로그램이 이제 설치하는 콘텐츠를 인터넷에서 다운로드합니다.  설치되는 모든 콘텐츠를 오프라인 레이아웃에서 사용할 수 있어야 합니다.  레이아웃에 콘텐츠에 없으면 설치에 실패합니다.  자세한 내용은 [네트워크 설치에서 배포](create-a-network-installation-of-visual-studio.md)를 참조하세요. |

## <a name="list-of-workload-ids-and-component-ids"></a>작업 ID 및 구성 요소 ID 목록

Visual Studio 제품별로 정렬된 워크로드 및 구성 요소 ID 목록은 [Visual Studio 2017 워크로드 및 구성 요소 ID](workload-and-component-ids.md) 페이지를 참조하세요.

## <a name="list-of-language-locales"></a>언어 로캘 목록

| **언어 로캘** | **언어** |
| ----------------------- | --------------- |
| cs-CZ | 체코어 |
| de-DE | 독일어 |
| ko-KR | 영어 |
| es-ES | 스페인어 |
| fr-FR | 프랑스어 |
| it-IT | 이탈리아어 |
| ja-JP | 일본어 |
| ko-KR | 한국어 |
| pl-PL | 폴란드어 |
| pt-BR | 포르투갈어 - 브라질 |
| ru-RU | 러시아어 |
| tr-TR | 터키어 |
| zh-CN | 중국어 - 간체 |
| zh-TW | 중국어 - 번체 |

## <a name="error-codes"></a>오류 코드

작업 결과에 따라 `%ERRORLEVEL%` 환경 변수는 다음 값 중 하나로 설정됩니다.

| **값** | **결과** |
| --------- | ---------- |
| 0 | 작업이 완료되었습니다. |
| 1602 | 작업이 취소되었습니다. |
| 3010 | 작업이 완료되었지만, 사용하려면 다시 부팅해야 합니다. |
| 5004 | 작업이 취소되었습니다. |
| 5007 | 작업이 차단되었습니다. 컴퓨터가 요구 사항에 맞지 않습니다. |
| 기타 | 오류 조건 발생 - 자세한 내용은 로그를 확인하세요. |

각 작업은 `%TEMP%` 디렉터리에 설치 진행률을 나타내는 여러 로그 파일을 생성합니다. 폴더를 날짜별로 정렬하고 부트스트래퍼, 설치 관리자 앱 및 설치 엔진 각각에 대해 `dd_bootstrapper`, `dd_client` 및 `dd_setup`으로 시작하는 파일을 찾습니다.

## <a name="get-support"></a>지원 받기

때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지를 참조하세요. 문제 해결 단계가 도움이 되지 않는 경우 라이브 채팅을 통해 Microsoft에 설치 지원을 문의할 수 있습니다(영어만 가능). 자세한 내용은 [Visual Studio 지원 페이지](https://www.visualstudio.com/vs/support/#talktous)를 참조하세요.

몇 가지 추가 지원 옵션은 다음과 같습니다.

* Visual Studio 설치 관리자와 Visual Studio IDE에 모두 표시되는 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 Microsoft에 제품 문제를 보고할 수 있습니다.
* [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 Microsoft와 제품 제안을 공유할 수 있습니다.
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고, 답변을 찾을 수 있습니다.
* [Gitter 커뮤니티의 Visual Studio 관련 대화](https://gitter.im/Microsoft/VisualStudio)를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다. (이 옵션을 사용하려면 [GitHub](https://github.com/) 계정이 필요합니다.)

## <a name="see-also"></a>참고 항목

* [Visual Studio 2017 설치에 대한 명령줄 매개 변수 예](command-line-parameter-examples.md)
* [Visual Studio 2017의 오프라인 설치 만들기](create-an-offline-installation-of-visual-studio.md)
* [지시 파일을 사용하여 Visual Studio 설치 자동화](automated-installation-with-response-file.md)
