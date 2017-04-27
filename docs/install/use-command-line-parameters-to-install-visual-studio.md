---
title: "명령줄 매개 변수를 사용하여 Visual Studio 설치 | Microsoft 문서"
ms.custom: 
ms.date: 04/06/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- command-line parameters
- switches
- command prompt
ms.assetid: 480f3cb4-d873-434e-a8bf-82cff7401cf2
author: TerryGLee
ms.author: tglee
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 9328c347d548a03a536cea16bd5851817c03d5a2
ms.openlocfilehash: 09c6971e21e48d250e3a9869860459fd8cbbb50f
ms.lasthandoff: 04/10/2017

---
# <a name="use-command-line-parameters-to-install-visual-studio-2017"></a>명령줄 매개 변수를 사용하여 Visual Studio 2017 설치
명령 프롬프트에서 Visual Studio 2017를 설치할 때 다양한 명령줄 매개 변수를 사용하여 설치를 제어하거나 사용자 지정할 수 있습니다. 명령줄에서 다음을 수행할 수 있습니다.
- 특정 옵션이 미리 선택된 상태로 설치를 시작합니다.
- 설치 프로세스를 자동화합니다.
- 나중에 사용할 설치 파일의 캐시(레이아웃)를 만듭니다.

명령줄 옵션은 다운로드 프로세스를 시작하는 작은(약 1MB) 파일인 설치 부트스트래퍼와 함께 사용됩니다. 부트스트래퍼는 Visual Studio 사이트에서 다운로드할 때 첫 번째로 실행되는 실행 파일입니다. 다음 링크에서 설치 중인 제품 버전에 대한 최신 릴리스 부트스트래퍼에 직접 연결된 링크를 가져올 수 있습니다.

* [Visual Studio 2017 Enterprise](https://aka.ms/vs/15/release/vs_enterprise.exe)
* [Visual Studio 2017 Professional](https://aka.ms/vs/15/release/vs_professional.exe)
* [Visual Studio 2017 Community](https://aka.ms/vs/15/release/vs_community.exe)

## <a name="list-of-command-line-parameters"></a>명령줄 매개 변수 목록  
 Visual Studio 명령줄 매개 변수는 대/소문자를 구분하지 않습니다.

>  구문: `vs_enterprise.exe [command] <options>...`

(설치 중인 제품 버전에 적합하게 `vs_enterprise.exe` 바꿉니다. 예를 보려면 [명령줄 매개 변수 예제](command-line-parameter-examples.md) 페이지를 참조하세요.)


| **명령** | **설명** |
| ----------------------- | --------------- |
| (비어 있음) | 제품을 설치합니다. |
| ```modify``` | 설치된 제품을 수정합니다. |
| ```update``` | 설치된 제품을 업데이트합니다. |
| ```repair``` | 설치된 제품을 복구합니다. |
| ```uninstall``` | 설치된 제품을 제거합니다. |


| **설치 옵션** | **설명** |
| ----------------------- | --------------- |  
| ```--installPath <dir>``` | 작업할 인스턴스에 대한 설치 디렉터리입니다. 설치 명령의 경우 인스턴스를 설치할 위치입니다. 다른 명령의 경우 이전에 설치한 인스턴스가 설치된 위치입니다. |
| ```--layout <dir>``` | **선택 사항**: 오프라인 설치 캐시를 만들 디렉터리를 지정합니다. 이 옵션을 선택하면 '--wait' 옵션도 암시적으로 추가됩니다. 배치 파일에서 호출한 경우에는 배치 파일에서 다음 명령에 실행이 전달되기 전에 이 명령이 완료됩니다. |
| ```--lang <language-locale>``` *[&#60;언어 로캘&#62; ...]* | **선택 사항**: --layout과 함께 사용하여 지정된 언어의 리소스 패키지와 함께 오프라인 설치 캐시를 준비합니다. 자세한 내용은 이 페이지의 [언어 로캘 목록](#list-of-language-locales) 섹션을 참조하세요.|
| ```--addProductLang <language-locale>``` | **선택 사항**: 설치 또는 수정 작업을 하는 동안 제품에 설치될 UI 언어 팩을 결정합니다. 여러 언어 팩을 추가하려면 명령줄에 여러 번 나타날 수 있습니다. 없는 경우 설치에 컴퓨터 로캘이 사용됩니다. 자세한 내용은 이 페이지의 [언어 로캘 목록](#list-of-language-locales) 섹션을 참조하세요.|
| ```--removeProductLang <language-locale>``` | **선택 사항**: 설치 또는 수정 작업을 하는 동안 제품에서 제거할 UI 언어 팩을 결정합니다. 여러 언어 팩을 추가하려면 명령줄에 여러 번 나타날 수 있습니다. 자세한 내용은 이 페이지의 [언어 로캘 목록](#list-of-language-locales) 섹션을 참조하세요.|
| ```--add <workload or component ID>``` *[&#60;작업 또는 구성 요소 ID&#62; ...]* | **선택 사항**: 추가할 하나 이상의 작업 또는 구성 요소 ID입니다. 아티팩트의 필수 구성 요소가 설치되지만 권장 또는 선택적 구성 요소는 설치되지 않습니다. '--includeRecommended' 및/또는 '--includeOptional'을 사용하여 추가 구성 요소를 전체적으로 제어할 수 있습니다. 세부적인 제어를 위해 ';includeRecommended' 및/또는 ';includeOptional'을 artifactId에 추가할 수 있습니다(예: '--add Workload1;includeRecommended' 또는 '--add Workload2;includeOptional;includeRecommended'). 자세한 내용은 [작업 및 구성 요소 ID](workload-and-component-ids.md) 페이지를 참조하세요.|
| ```--remove <workload or component ID>``` *[&#60;작업 또는 구성 요소 ID&#62; ...]* | **선택 사항**: 제거할 하나 이상의 작업 또는 구성 요소 ID입니다. 자세한 내용은 [작업 및 구성 요소 ID](workload-and-component-ids.md) 페이지를 참조하세요.|
| ```--in <path>``` | **선택 사항**: 응답 파일의 URI 또는 경로입니다.  |
| ```--all``` | **선택 사항**: 제품에 대한 모든 작업 및 구성 요소를 설치할지의 여부입니다. |
| ```--allWorkloads``` | **선택 사항**: 모든 작업 및 관련 필수 구성 요소를 설치하고, 권장 또는 선택적 구성 요소는 설치하지 않습니다. |
| ```--includeRecommended``` | **선택 사항**: 설치된 모든 작업에 대한 권장 구성 요소를 포함하지만, 선택적 구성 요소는 포함하지 않습니다. --allWorkloads 또는 --add를 사용하여 작업을 지정합니다. |
| ```--includeOptional``` | **선택 사항**: 설치된 모든 작업에 대한 선택적 구성 요소를 포함하지만, 권장 구성 요소는 포함하지 않습니다. --allWorkloads 또는 --add를 사용하여 작업을 지정합니다.  |
| ```--quiet, -q``` | **선택 사항**: 설치를 수행하는 동안 사용자 인터페이스를 표시하지 않습니다. |
| ```--passive, -p``` | **선택 사항**: 사용자 인터페이스를 표시하지만 사용자 조작을 요청하지 않습니다. |
| ```--norestart``` | **선택 사항**: 이 옵션이 있는 경우 --passive 또는 --quiet가 포함된 명령은 컴퓨터를 자동으로 다시 시작하지 않습니다(필요한 경우). --passive 또는 --quiet가 지정되지 않은 경우에는 무시됩니다.  |
| ```--nickname <name>``` | **선택 사항**: 설치된 제품에 할당할 애칭을 정의합니다. 애칭은 10자를 초과할 수 없습니다.  |
| ```--productKey``` | **선택 사항**: 설치된 제품에 사용할 제품 키를 정의합니다. 제품 키는 'xxxxx-xxxxx-xxxxx-xxxxx-xxxxx' 또는 'xxxxxxxxxxxxxxxxxxxxxxxxx' 형식의 영숫자 25자로 구성됩니다. |
| ```--help, --?, -h, -?``` | 이 페이지의 오프라인 버전을 표시합니다. |

> 참고: 여러 작업과 구성 요소를 지정할 경우 각 항목에 대해 `--add` 또는 `--remove` 명령줄 스위치를 반복해야 합니다.

| **고급 설치 옵션** | **설명** |
| ----------------------- | --------------- |  
| ```--channelId <id>``` | **선택 사항**: 설치할 인스턴스의 채널 ID입니다. 설치 명령에 필요하며, --installPath가 지정된 경우 다른 명령에서는 무시됩니다. |
| ```--channelUri <uri>``` | **선택 사항**: 채널 매니페스트의 URI입니다. 설치 명령에 사용할 수 있습니다. 다른 명령에서는 무시됩니다. |
| ```--installChannelUri <uri>``` | **선택 사항**: 설치에 사용할 채널 매니페스트의 URI입니다. -channelUri(--installChannelUri가 지정된 경우 지정해야 함)로 지정된 URI는 업데이트를 검색하는 데 사용됩니다. 업데이트를 원하지 않는 경우 인수 없이 --channelUri를 지정해야 합니다. 설치 명령에 사용할 수 있습니다. 다른 명령에서는 무시됩니다. |
| ```--installCatalogUri <uri>``` | **선택 사항**: 설치에 사용할 카탈로그 매니페스트의 URI입니다. 지정된 경우 채널 관리자는 설치 채널 매니페스트의 URI를 사용하기 전에 이 URI에서 카탈로그 매니페스트를 다운로드하려고 합니다. 이 매개 변수는 이미 다운로드한 제품 카탈로그를 사용하여 레이아웃 캐시가 생성되는 오프라인 설치를 지원하는 데 사용됩니다. 설치 명령에 사용할 수 있습니다. 다른 명령에서는 무시됩니다. |
| ```--productId <id>``` | 설치할 인스턴스에 대한 제품 ID입니다. 설치 명령에 필요하며, --installPath가 지정된 경우 다른 명령에서는 무시됩니다. |
| ```--wait``` | **선택 사항**: 프로세스에서 설치가 완료될 때까지 기다린 후에 종료 코드를 반환합니다. 이 기능은 설치의 반환 코드를 처리하기 위해 설치가 완료할 때까지 기다려야 하는 설치를 자동화할 경우 유용합니다. |
| ```--locale <language-locale>``` | **선택 사항**: 설치 관리자의 사용자 인터페이스 표시 언어를 변경합니다. 설정은 유지됩니다. 자세한 내용은 이 페이지의 [언어 로캘 목록](#list-of-language-locales) 섹션을 참조하세요.|

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

| **Value** | **결과** |
| --------- | ---------- |
| 0 | 작업이 완료되었습니다. |
| 3010 | 작업이 완료되었지만, 사용하려면 다시 부팅해야 합니다. |
| 기타 | 오류 조건 발생 - 자세한 내용은 로그를 확인하세요. |

각 작업은 `%TEMP%` 디렉터리에 설치 진행률을 나타내는 여러 로그 파일을 생성합니다. 폴더를 날짜별로 정렬하고 부트스트래퍼, 설치 관리자 앱 및 설치 엔진 각각에 대해 `dd_bootstrapper`, `dd_client` 및 `dd_setup`으로 시작하는 파일을 찾습니다.

## <a name="see-also"></a>참고 항목

 * [Visual Studio 2017 설치](install-visual-studio.md)
 * [Visual Studio 2017의 오프라인 설치 만들기](create-an-offline-installation-of-visual-studio.md)
 * [Visual Studio 2017 설치에 대한 명령줄 매개 변수 예](command-line-parameter-examples.md)
 * [Visual Studio 2017의 문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md)

