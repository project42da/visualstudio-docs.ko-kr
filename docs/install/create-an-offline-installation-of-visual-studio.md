---
title: Visual Studio의 오프라인 설치 만들기
description: Visual Studio를 오프라인으로 설치하는 방법을 알아봅니다.
ms.custom: ''
ms.date: 01/17/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- offline installation [Visual Studio]
- offline install [Visual Studio]
- layout [Visual Studio]
ms.assetid: f8625d5e-f6ea-4db0-83c0-619b77fab3cf
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6d70005a7e876b299e93ac2891ce6774a6300792
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="create-an-offline-installation-of-visual-studio-2017"></a>Visual Studio 2017의 오프라인 설치 만들기

Visual Studio 2017 설치 관리자는 매우 다양한 네트워크 및 컴퓨터 조건에서 제대로 작동하도록 구성되어 있습니다.

- 새 워크로드 기반 모델에서는 Visual Studio의 이전 버전을 포함한 것보다 적게 다운로드해야 합니다(최소 규모 설치의 경우 300MB에 불과함).
- 일반 "ISO" 또는 zip 파일에 비해, 컴퓨터에 필요한 패키지만 다운로드합니다. 예를 들어, 필요하지 않은 경우 64비트 파일을 다운로드하지 않습니다.
- 설치하는 동안 바이러스 백신 및 프록시 소프트웨어의 간섭을 최소화하기 위해 세 가지 다운로드 기술(WebClient, BITS 및 WinInet)이 시도됩니다.
- Visual Studio 설치에 필요한 파일은 전역 배달 네트워크에 배포되므로 로컬 서버에서 해당 파일을 가져올 수 있습니다.

따라서 [Visual Studio 웹 설치 관리자](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocsOL)&mdash;를 시도하는 것이 좋습니다. 좋은 경험이 될 것입니다.

 > [!div class="button"]
 > [Visual Studio 2017 다운로드](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocsOL)

인터넷 연결을 사용할 수 없거나 인터넷 연결이 불안정하여 오프라인으로 설치하려는 경우 [낮은 대역폭 또는 불안정한 네트워크 환경에 Visual Studio 2017 설치](../install/install-vs-inconsistent-quality-network.md)를 참조하세요. 명령줄을 사용하여 오프라인 설치를 완료하기 필요한 파일의 로컬 캐시를 만들 수 있습니다. 이 프로세스는 이전 버전에 사용 가능한 ISO 파일을 대체합니다.

> [!NOTE]
> 인터넷에서 방화벽이 사용되는 클라이언트 워크스테이션의 네트워크에 대해 Visual Studio 2017의 배포를 수행하려고 하는 엔터프라이즈 관리자인 경우 [Visual Studio 2017의 네트워크 설치 만들기](../install/create-a-network-installation-of-visual-studio.md) 및 [Visual Studio 오프라인 설치에 필요한 인증서 설치](../install/install-certificates-for-visual-studio-offline.md) 페이지를 참조하세요.

## <a name="get-support"></a>지원 받기

때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지를 참조하세요. 문제 해결 단계가 도움이 되지 않는 경우 라이브 채팅을 통해 Microsoft에 설치 지원을 문의할 수 있습니다(영어만 가능). 자세한 내용은 [Visual Studio 지원 페이지](https://www.visualstudio.com/vs/support/#talktous)를 참조하세요.

몇 가지 추가 지원 옵션은 다음과 같습니다.

* Visual Studio 설치 관리자와 Visual Studio IDE에 모두 표시되는 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 Microsoft에 제품 문제를 보고할 수 있습니다.
* [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 Microsoft와 제품 제안을 공유할 수 있습니다.
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고, 답변을 찾을 수 있습니다.
* [Gitter 커뮤니티의 Visual Studio 관련 대화](https://gitter.im/Microsoft/VisualStudio)를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다. (이 옵션을 사용하려면 [GitHub](https://github.com/) 계정이 필요합니다.)
