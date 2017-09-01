---
title: "Mac용 Visual Studio에서 Git 리포지토리 설정하기"
description: "Mac용 Visual Studio에서 Git 및 Subversion 사용"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: E992FA1D-B2AD-4A28-ADC6-47E4FC471060
ms.translationtype: HT
ms.sourcegitcommit: e2b7ff9126e1cc38ac2e58d6be339b656a024e7f
ms.openlocfilehash: 9f25eda17648ba7eb3c264660ee0eb3b8eee166c
ms.contentlocale: ko-kr
ms.lasthandoff: 08/11/2017

---

# <a name="setting-up-a-git-repository"></a>Git 리포지토리 설정

Git은 모든 팀원이 동일한 문서를 동시에 작업할 수 있는 분산형 버전 제어 시스템입니다. 즉, 모든 파일을 포함하는 단일 서버가 있더라도 이 중앙 소스에서 리포지토리를 체크 아웃할 때마다 리포지토리 전체가 로컬 컴퓨터에 복제됩니다.

Git를 사용한 버전 제어를 제공하는 원격 호스트는 많지만 가장 일반적인 것은 GitHub입니다. 다음 예제에서는 GitHub 호스트를 사용하지만, Mac용 Visual Studio에서 어떤 Git 호스트를 사용해도 버전 제어를 수행할 수 있습니다.

GitHub를 사용하려면 계정을 만들고 구성한 다음 아래의 단계를 수행하세요. 

## <a name="creating-a-remote-repo-on-github"></a>GitHub에서 원격 리포지토리 만들기

다음 예제에서는 GitHub 호스트를 사용하지만, Mac용 Visual Studio에서 어떤 Git 호스트를 사용해도 버전 제어를 수행할 수 있습니다.

Git 리포지토리를 설정하려면 다음 단계를 수행하세요.

1. github.com에서 새 Git 리포지토리를 만듭니다.

    ![새 Git 리포지토리 만들기](media/version-control-git1-sml.png)

2. 리포지토리 이름, 설명, 개인 정보 보호를 설정합니다. 리포지토리를 초기화하지 **마세요.** .gitignore 및 라이선스를 [없음]으로 설정합니다.

    ![Git 리포지토리 세부 사항 설정](media/version-control-git2.png)

3. 다음 장소에서는 방금 만든 리포지토리에 대한 HTTPS 또는 SSH 주소를 표시하고 복사하는 옵션을 제공합니다.

    ![주소 보기 및 복사](media/version-control-git3.png) 이 리포지토리에 Mac용 Visual Studio를 지정하려면 HTTPS 주소가 필요합니다.


## <a name="publishing-an-existing-project"></a>기존 프로젝트 게시

4. Mac용 Visual Studio의 열린 프로젝트로 돌아옵니다. 

5. 메뉴 모음에서 **버전 제어 > 버전 제어에서 게시...**를 선택합니다.

    ![Mac용 Visual Studio에서 체크 아웃 시작](media/version-control-git4-sml.png)

6. 이렇게 하면 **리포지토리 선택** 대화 상자가 표시됩니다. **등록된 리포지토리** 탭을 선택하고 **추가** 단추를 클릭합니다.

    ![](media/version-control-git5.png)

7. 로컬에 표시하고 싶은 리포지토리 이름을 입력하고 3단계에서 복사한 URL을 붙여넣습니다. [리포지토리 구성] 대화 상자가 다음과 같이 표시됩니다. [확인]을 누릅니다. 

    ![Git 세부 사항 입력 대화 상자](media/version-control-git6.png)

    SSH를 사용하여 Git에 연결할 수도 있습니다.

8. Git에 앱을 게시하려면 방금 만든 리포지토리를 선택하고 **모듈 이름**과 **메시지** 텍스트 필드를 작성했는지 확인합니다.

    ![Git에 프로젝트 게시](media/version-control-git7.png)

9. **확인**을 클릭한 다음 경고 대화 상자에서 **게시**를 클릭합니다.

10. Mac용 Visual Studio 기본 설정에서 Git 자격 증명을 입력하지 않았으면 지금 입력합니다. 우선 암호 대신 사용할 액세스 토큰을 만들어야 합니다. 액세스 토큰을 만들려면 Git [액세스 토큰](https://help.github.com/articles/creating-an-access-token-for-command-line-use/) 설명서의 단계를 따르세요.

11. 사용자 이름과 개인용 액세스 토큰을 입력하고 **확인**을 누릅니다.

    ![Git에 대한 사용자 이름 및 암호 입력](media/version-control-git9-sml.png)

12. 몇 초 후 솔루션이 초기 커밋과 함께 게시될 것입니다. [버전 제어] 메뉴 항목을 탐색하여 이를 확인합니다. 이제 [버전 제어] 메뉴 항목이 다음과 같이 다양한 옵션으로 채워져 있을 것입니다. 

    ![버전 제어 메뉴](media/version-control-git10.png)

13. 추가적인 변경 작업을 시작한 경우, **변경 내용 푸시...**를 선택하여 **원격** 리포지토리로 변경 내용을 푸시합니다. 이렇게 하면 github.com에서 해당하는 모든 사용자가 변경 사항을 볼 수 있습니다. 

    ![원격 리포지토리에 변경 사항 푸시](media/version-control-git11.png)

## <a name="publishing-a-new-project"></a>새 프로젝트 게시

새 프로젝트 대화 상자를 사용하면 Git를 사용하여 새 프로젝트를 게시할 수 있습니다. 사용하려면 다음 스크린샷과 같이 **버전 제어에 git을 사용합니다.** 확인란을 선택하세요. 이렇게 하면 리포지토리가 초기화되고 선택적 .gitignore 파일이 추가됩니다.

![원격 리포지토리에 변경 사항 푸시](media/version-control-git12.png)

## <a name="troubleshooting"></a>문제 해결

빈 원격 리포지토리로 프로젝트를 초기화하는 데 문제가 있을 경우 다음 단계를 시도하세요.

- 솔루션 폴더로 이동합니다.
- `Command + Shift + . `를 눌러 숨겨진 파일과 폴더를 표시합니다.
- `.git` 폴더가 있으면 삭제합니다.
- `gitignore` 파일이 있으면 삭제합니다.
- `Command + Shift + . `를 눌러 파일과 폴더를 숨깁니다.
- 솔루션을 Mac용 VS에서 엽니다.
- Solution Pad에서 솔루션 노드를 선택합니다.
- [버전 제어] 메뉴를 찾아 **버전 제어에서 게시**를 선택합니다.
- 위의 연습 단계를 6단계부터 따라 수행합니다.
