---
title: 컨테이너에 대한 알려진 문제 | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 140083f1-05bc-4014-949e-fb5802397c7a
author: heaths
ms.author: tglee
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 94b3acaeffc709978cc9c49645fd7e788abef177
ms.sourcegitcommit: fb1fede41d8c5e459dd222755b0497b9d361bc51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="known-issues-for-containers"></a>컨테이너에 대한 알려진 문제

Visual Studio를 Docker 컨테이너에 설치하는 데 몇 가지 문제가 있습니다.

## <a name="windows-container"></a>Windows 컨테이너

다음 알려진 문제는 Windows 컨테이너에 Visual Studio Build Tools 2017을 설치할 경우 발생합니다.

* 이미지 microsoft/windowsservercore:10.0.14393.1593에 기반한 컨터이너에는 Visual Studio를 설치할 수 없습니다. 이전 또는 최신 Windows 버전으로 태그가 지정된 이미지가 작동합니다.
* 10.0.14393 이전의 Windows SDK 버전은 설치할 수 없습니다. 특정 패키지는 설치되지 않으며 이러한 패키지에 종속된 워크로드는 작동하지 않습니다.
* 이미지 빌드 시 `-m 2GB`(또는 이상)를 전달해야 합니다. 일부 워크로드는 설치 시 기본 1GB 이상의 메모리가 필요합니다.
* 기본값 20GB보다 큰 디스크를 사용하도록 Docker를 구성해야 합니다.
* 명령줄에서 `--norestart`를 전달해야 합니다. 이 문서 작성 당시, 컨테이너 내부에서 Windows 컨테이너를 다시 시작하려면 `ERROR_TOO_MANY_OPEN_FILES`가 호스트여야 합니다.

## <a name="build-tools-container"></a>빌드 도구 컨테이너

빌드 도구 컨테이너를 사용하는 경우 다음과 같은 알려진 문제가 발생할 수 있습니다. 문제가 해결되었는지 또는 다른 알려진 문제가 있는지 확인하려면 https://developercommunity.visualstudio.com에 방문하세요.

* IntelliTrace는 컨테이너 내의 [일부 시나리오](https://github.com/Microsoft/vstest/issues/940)에서는 작동하지 않습니다.

## <a name="get-support"></a>지원 받기
때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지를 참조하세요. 문제 해결 단계가 도움이 되지 않는 경우 라이브 채팅을 통해 Microsoft에 설치 지원을 문의할 수 있습니다(영어만 가능). 자세한 내용은 [Visual Studio 지원 페이지](https://www.visualstudio.com/vs/support/#talktous)를 참조하세요.

몇 가지 추가 지원 옵션은 다음과 같습니다.
* Visual Studio 설치 관리자와 Visual Studio IDE에 모두 표시되는 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 Microsoft에 제품 문제를 보고할 수 있습니다.
* [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 Microsoft와 제품 제안을 공유할 수 있습니다.
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고 질문을 하고 답을 찾을 수 있습니다.
* [Gitter 커뮤니티의 Visual Studio 관련 대화](https://gitter.im/Microsoft/VisualStudio)를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다.  (이 옵션을 사용하려면 [GitHub](https://github.com/) 계정이 필요합니다.)

## <a name="see-also"></a>참고 항목

* [Build Tools를 컨테이너에 설치](build-tools-container.md)
* [고급 컨테이너 예제](advanced-build-tools-container.md)
* [Visual Studio Build Tools 2017 워크로드 및 구성 요소 ID](workload-component-id-vs-build-tools.md)
