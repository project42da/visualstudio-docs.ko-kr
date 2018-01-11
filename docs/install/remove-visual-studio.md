---
title: "Visual Studio 2017 제거 | Microsoft Docs"
description: "Visual Studio를 제거하는 방법을 단계별로 알아봅니다."
ms.custom: 
ms.date: 09/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- uninstall
- uninstall Visual Studio
- remove
- remove Visual Studio
- cleanup
- cleanup Visual Studio
- clean up
- clean up Visual Studio
ms.assetid: 9c81a777-9c95-4934-b517-c60c6dc78799
author: heaths
ms.author: heaths
manager: erickn
ms.workload: multiple
ms.openlocfilehash: a08a24be4f3f9e915a93c9beac7cf5e5c28eb7ca
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="remove-visual-studio"></a>Visual Studio 제거

치명적인 오류가 발생하고 Visual Studio를 복구 또는 제거할 수 없는 경우 `InstallCleanup.exe` 도구를 실행하여 설치 파일 및 제품 정보를 제거할 수 있습니다. 이 도구는 복구 또는 제거가 실패할 경우 마지막 수단으로 실행해야 하며 복구가 필요한 다른 Visual Studio 설치 또는 기타 제품에서 기능을 제거할 수 있습니다.

아래 지침에서는 다음과 같은 동작의 다른 명령줄 스위치로 도구를 실행할 수 있습니다.

| 전환 | 동작 |
| ------ | -------- |
| `-i`   | 이 스위치는 전달된 다른 스위치가 없을 경우 기본값이며 기본 설치 디렉터리 및 제품 정보만 제거합니다. 이 동작은 `InstallCleanup.exe` 도구를 실행한 후 동일한 버전을 다시 설치하려는 경우 사용하는 것이 좋습니다. |
| `-f`   | 이 스위치를 지정하면 기본 설치 디렉터리, 제품 정보는 물론, 다른 Visual Studio 설치 또는 기타 제품과 공유할 수 있는 설치 디렉터리 외부에 설치된 대부분 기타 기능이 제거됩니다. 이 동작은 나중에 다시 설치하지 않고 Visual Studio를 제거하려는 경우에 사용하는 것이 좋습니다. |

1. Visual Studio 설치 관리자를 닫습니다.
2. 관리자 명령 프롬프트를 엽니다. 관리자 명령 프롬프트를 열려면 다음 단계를 따릅니다.
   * **시작** 메뉴에서 **실행**을 클릭합니다([시작] + R).
   * **cmd**를 입력합니다.
   * **명령 프롬프트**를 마우스 오른쪽 단추로 클릭하고 **관리자 권한으로 실행**을 클릭합니다.
3. `InstallCleanup.exe` 유틸리티의 전체 경로를 입력하고 원하는 명령줄 스위치를 전달합니다. 기본적으로 유틸리티 경로는 다음과 같습니다.
   ```
   C:\Program Files (x86)\Microsoft Visual Studio\Installer\resources\app\layout\InstallCleanup.exe
   ```

Visual Studio 설치 관리자 디렉터리에서 항상 `%ProgramFiles(x86)%\Microsoft Visual Studio`에 있는 `InstallCleanup.exe`을 찾지 못한 경우 지침에 따라 [Visual Studio를 설치](install-visual-studio.md)하고 워크로드 선택 화면이 표시되면 창을 닫고 이전 단계를 다시 따릅니다.

## <a name="get-support"></a>지원 받기
때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지를 참조하세요. 문제 해결 단계가 도움이 되지 않는 경우 라이브 채팅을 통해 Microsoft에 설치 지원을 문의할 수 있습니다(영어만 가능). 자세한 내용은 [Visual Studio 지원 페이지](https://www.visualstudio.com/vs/support/#talktous)를 참조하세요.

몇 가지 추가 지원 옵션은 다음과 같습니다.
* Visual Studio 설치 관리자와 Visual Studio IDE에 모두 표시되는 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 Microsoft에 제품 문제를 보고할 수 있습니다.
* [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 Microsoft와 제품 제안을 공유할 수 있습니다.
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고 질문을 하고 답을 찾을 수 있습니다.
* [Gitter 커뮤니티의 Visual Studio 관련 대화](https://gitter.im/Microsoft/VisualStudio)를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다.  (이 옵션을 사용하려면 [GitHub](https://github.com/) 계정이 필요합니다.)

## <a name="see-also"></a>참고 항목
* [Visual Studio 2017 설치](install-visual-studio.md)
* [Visual Studio 2017 업데이트](update-visual-studio.md)
* [Visual Studio 2017 수정](modify-visual-studio.md)
* [Visual Studio 2017 제거](uninstall-visual-studio.md)
