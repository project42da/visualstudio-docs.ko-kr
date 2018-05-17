---
title: TF 버전 제어
description: Team Foundation 버전 제어를 사용하여 Team Foundation Server 또는 Visual Studio Team Services에 연결.
author: asb3993
ms.author: amburns
ms.date: 05/03/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
ms.openlocfilehash: f892209faeb06ca703d28016457e9ba4ab86ccda
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="connecting-to-team-foundation-version-control"></a>eam Foundation 버전 제어에 연결 

VSTS(Visual Studio Team Services) 및 TFS(Team Foundation Server)는 분산형 버전 제어인 Git와 중앙 집중식 버전 제어인 TFVC(Team Foundation Version Control)라는 두 가지 버전 제어 모드를 제공합니다. 이 아티클에서는 Mac용 Visual Studio에서 Team Foundation 버전 제어를 사용하는 방법에 대한 개요와 그 시작점을 제공합니다.

> [!NOTE]
> **참고**: Team Foundation 버전 제어 지원은 현재 미리 보기 상태이며, 일부 기능은 아직 완전히 작동하지 않습니다. 아직 변경의 여지가 많이 있습니다.

## <a name="requirements"></a>요구 사항

* Mac용 Visual Studio 버전 7.5 이상.
* Visual Studio Team Servers 또는 Team Foundation Server 2013 이상
* Team Foundation 버전 제어를 사용하도록 구성된 Visual Studio Team Services 또는 Team Foundation Server의 프로젝트.

## <a name="installation"></a>설치

Mac용 Visual Studio에서 **Visual Studio > 확장...** 메뉴를 선택합니다. "TF 버전 제어"를 검색하고 **Team Foundation 버전 제어** 확장을 설치합니다. 메시지가 표시되면 IDE를 다시 시작합니다.

## <a name="using-the-add-in"></a>추가 기능 사용

확장이 설치되면 **버전 제어 > TFS/VSTS > Team Foundation 버전 제어에 연결...** 메뉴를 선택합니다. 

![TFVC 서버 추가](media/tfvc-add-remove-server.png)


Visual Studio Team Services 또는 Team Foundation Server를 선택하여 시작:

![TFVC 서버와 연결](media/tfvc-choose-server-type.png)

자격 증명 입력: 

![TFVC 서버에 로그인](media/tfvc-login.png)

그런 다음, 액세스할 프로젝트 선택: 

![프로젝트 선택](media/tfvc-choose-projects.png)

계속하려면 대화 상자를 닫은 후 **버전 제어 > TFS/VSTS > 소스 제어 탐색기** 메뉴를 사용하여 소스를 찾아봅니다.

> [!WARNING]
> **알려진 문제**: 이 미리 보기 릴리스에서는 처음으로 소스 제어 탐색기를 열 때 새 작업 영역을 만들어야 합니다.

![소스 탐색기](media/tfvc-source-explorer.png)

소스 코드 탐색기에서 서버의 소스 코드를 찾아보고 다음 작업을 수행할 수 있습니다.

- 작업 영역 관리(만들기, 편집 또는 삭제).
- 프로젝트 구조 사이로 이동.
- 프로젝트 매핑.
- 프로젝트 가져오기.
- 파일 잠금 및 잠금 해제.
- 파일 이름 바꾸기.
- 파일 삭제.
- 새 파일 추가.
- 체크 아웃.
- 체크 인.
- 변경 기록 보기.
- 변경 내용 비교.

## <a name="creating-a-new-workspace"></a>새 작업 영역 만들기

소스 제어 탐색기에서 **작업 영역 관리** 단추를 클릭합니다. 

![작업 영역 관리](media/tfvc-manage-workspaces.png)

**추가**를 클릭하여 새 작업 영역을 만듭니다.

![작업 영역 만들기](media/tfvc-create-workspace.png)

작업 영역의 이름을 지정한 후 **작업 폴더 추가**를 클릭하여 컴퓨터의 로컬 폴더에 프로젝트를 매핑합니다.

완료되면 **확인**을 클릭한 후 작업 영역 관리 대화 상자를 닫습니다. 이제 소스 코드 탐색기를 통해 파일을 가져와 시작할 수 있습니다.