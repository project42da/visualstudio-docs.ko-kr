---
title: "컨테이너에 대한 알려진 문제 | Microsoft Docs"
ms.custom: 
ms.date: 10/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 140083f1-05bc-4014-949e-fb5802397c7a
author: heaths
ms.author: heaths
manager: ghogen
ms.openlocfilehash: 75825d368d0098c466c44a23fa18ac1af7b06e64
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2017
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
때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지에서 문제 해결 팁을 참조하세요. 또한 Visual Studio IDE의 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 제품 문제를 보고하거나 [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 제안을 공유할 수 있습니다. [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고 질문을 하고 답을 찾을 수 있습니다. [Gitter 커뮤니티](https://gitter.im/Microsoft/VisualStudio)([GitHub](https://github.com/) 계정 필요)의 Visual Studio 관련 대화를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다.

## <a name="see-also"></a>참고 항목

* [빌드 도구를 컨테이너에 설치](build-tools-container.md)
* [컨테이너의 고급 예](advanced-build-tools-container.md)