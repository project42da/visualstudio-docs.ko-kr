---
title: Mac용 Visual Studio에서 Subversion 리포지토리 설정하기
description: Mac용 Visual Studio에서 Git 및 Subversion 사용
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 0D58FB37-530E-495B-BED6-FD499477A9B6
ms.openlocfilehash: e6b6fd600d3f32c77651b9a4fbb0dff2cd754bcb
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="setting-up-a-subversion-repository"></a>Subversion 리포지토리 설정

Subversion은 중앙 버전 제어 시스템입니다. 즉, 모든 파일과 수정 버전을 포함하는 단일 서버가 있으며 사용자는 여기에서 임의의 파일 버전을 체크 아웃할 수 있습니다. 원격 Subversion 리포지토리에서 파일을 체크 아웃하면 사용자는 해당 시점을 기준으로 리포지토리의 스냅숏을 가져옵니다.

Subversion을 사용하기 전에 올바른 svn 패키지를 포함하도록 Xcode 명령줄 도구를 설치해야 합니다. 다음 명령을 사용하면 SVN이 터미널에 설치되었는지 확인할 수 있습니다.

`svn h`

1. 온라인으로 무료 SVN 리포지토리를 만듭니다. 이 예제에서는 [Assembla](https://app.assembla.com/)를 사용했습니다. 리포지토리가 만들어지면 연결에 사용되는 URL이 제공됩니다. 

    ![SVN URL 획득 및 복사](media/version-control-subversion1-sml.png)

2. Mac용 Visual Studio 프로젝트를 열거나 만듭니다.

3. 프로젝트를 마우스 오른쪽 단추로 클릭하고 **버전 제어 > 버전 제어에서 게시...** 를 선택합니다. 

    ![프로젝트 게시 시작](media/version-control-subversion2.png)

4. **리포지토리에 연결** 탭의 상단 드롭다운에서 **Subversion**을 선택합니다.

5. 1단계에서 제공된 URL을 입력합니다. 이렇게 하면 기본적으로 나머지 필드가 채워집니다. 

    ![리포지토리 선택 및 세부 정보 입력 대화 상자](media/version-control-subversion3.png)

7. **확인**을 클릭한 다음 **게시**를 눌러 확인합니다.

7. 리포지토리를 만든 사이트에 대한 자격 증명을 입력하라는 메시지가 표시될 수 있습니다. 아래 그림과 같이 입력합니다.

    ![](media/version-control-subversion5.png)

8.  이제 사용할 수 있는 모든 버전 제어 명령이 버전 제어 메뉴에 표시됩니다.

