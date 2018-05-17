---
title: Visual Studio 2017에서의 설치 위치 변경
description: 다운로드 캐시, 공유 구성 요소, 일부 SDK 및 도구의 위치를 변경하여 시스템 드라이브의 설치 공간을 줄이는 방법을 알아봅니다.
ms.date: 05/07/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- change installation locations for Visual Studio
- move installation files to different drives
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0460e61fea7e617e497a46c55f8af811ba2e24fe
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="change-the-installation-locations-in-visual-studio-2017"></a>Visual Studio 2017에서의 설치 위치 변경

**15.7의 새로운 기능**: 다운로드 캐시, 공유 구성 요소, SDK 및 도구를 다른 드라이브로 이동하여 시스템 드라이브의 설치 공간을 줄였습니다.

방법은 다음과 같습니다.

1. Visual Studio를 설치할 때 **설치 옵션** 탭을 선택합니다.

  ![Visual Studio 2017 - 설치 위치 변경](media/installation-options-by-location.png "설치 위치 변경")

  > [!IMPORTANT]
  > 설치를 일시 중지하고 나중에 계속하는 경우 Visual Studio는 중단했던 위치를 선택하게 됩니다. 즉 다운로드하고 설치해야 할 잔여 항목에 진행률이 적용되고, 이전 개수에서 시작되지 않습니다.

2. **Visual Studio** 섹션에서 기본값을 적용합니다. 이 설치에서는 핵심 제품을 설치하고 이 Visual Studio 버전에 특정한 파일을 포함합니다.

 > [!IMPORTANT]
 > 시스템 드라이브가 SSD(반도체 드라이브)라면 Visual Studio를 통한 개발에서 많은 파일 읽기 및 쓰기가 있어 디스크 I/O 작업이 늘어나므로 시스템 드라이브의 기본 위치를 적용하는 것이 좋습니다.  로드를 처리하기 위해 가장 빠른 드라이브를 선택하는 것이 좋습니다.

2. **다운로드 캐시** 섹션에서 다운로드 캐시를 유지할지 여부를 결정한 다음, **다운로드 캐시 유지**를 그에 따라 선택하거나 선택 취소합니다. <br><br>다운로드 캐시를 유지하지 않도록 설정하면 위치를 일시적으로만 사용합니다. 또 이전 설치에서의 파일에는 영향이 없고 해당 파일을 삭제하지도 않습니다. 모든 설치 패키지를 정리하려면 이전 설치를 별도로 수정해야 합니다.

3. **다운로드 캐시** 섹션에서 설치 파일과 매니페스트를 저장하려는 드라이브를 지정합니다. <br><br>예를 들어, **C++을 통한 데스크톱 개발**을 선택할 경우 일시적으로 필요한 크기는 시스템 드라이브에서 1.58GB이며 설치가 완료된 즉시 비워집니다.

 > [!NOTE]
 > 파일은 먼저 시스템의 임시 드라이브에 다운로드된 다음, Visual Studio가 해당 파일을 확인하고 다운로드 캐시 폴더로 옮기고 나면 삭제됩니다. 다운로드 캐시를 다른 드라이브에 유지하도록 선택한 경우에도 Visual Studio는 시스템 드라이브에서 다운로드 캐시 크기에 상응하는 디스크 공간을 필요로 합니다. 
 > [!IMPORTANT]
 > 위치는 처음 설치에서 설정되며 이후에는 설치 관리자 UI에서 변경할 수 없습니다. 대신, [명령줄 매개 변수를 사용하여](use-command-line-parameters-to-install-visual-studio.md) 다운로드 캐시를 이동합니다.

4. **공유 구성 요소, SDK 및 도구** 섹션에서 함께 설치한 Visual Studio에서 공유하는 파일을 저장하려는 드라이브를 지정합니다. Visual Studio 설치 관리자가 설치 위치를 변경하도록 하는 SDK 및 도구도 이 디렉터리에 저장됩니다.

 > [!NOTE]
 > 일부 도구와 SDK에는 설치 가능한 위치에 대해 다른 규칙이 적용됩니다. 이러한 도구 및 SDK도 다른 위치를 선택했다 하더라도 시스템 드라이브에 설치해야 합니다.

## <a name="get-support"></a>지원 받기

때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지를 참조하여 도움을 받으세요. [실시간 채팅](https://www.visualstudio.com/vs/support/#talktous)(영어 전용)을 통해 설치 도움말에 대한 문의할 수 있습니다. 자세한 내용은 [Visual Studio “사용자 의견”](https://www.visualstudio.com/vs/support/#talktous)을 참조하세요.

몇 가지 추가 지원 옵션은 다음과 같습니다.

* Visual Studio 설치 관리자와 Visual Studio IDE에 모두 표시되는 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 Microsoft에 제품 문제를 보고할 수 있습니다.
* [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 Microsoft와 제품 제안을 공유할 수 있습니다.
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고, 답변을 찾을 수 있습니다.
* [Gitter 커뮤니티의 Visual Studio 관련 대화](https://gitter.im/Microsoft/VisualStudio)를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다. (이 옵션을 사용하려면 [GitHub](https://github.com/) 계정이 필요합니다.)

## <a name="see-also"></a>참고 항목

* [Visual Studio 2017 설치](install-visual-studio.md)
* [Visual Studio 2017 업데이트](update-visual-studio.md)
* [Visual Studio 2017 수정](update-visual-studio.md)
* [Visual Studio 2017 제거](uninstall-visual-studio.md)
