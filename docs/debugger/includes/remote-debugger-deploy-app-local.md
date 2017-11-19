---
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.openlocfilehash: a55b2a12c9a45c5a3952e3e6f4e1627bec8ba520
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
1. 에 **솔루션 탐색기**프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **게시** (Web Forms에 대 한 **웹 응용 프로그램 게시**).

2. 에 **게시** 대화 상자에서 **폴더**, 클릭 **찾아보기**, 새 폴더를 만들고 **C:\Publish**합니다.

    ![RemoteDBG_Publish_Local](../media/remotedbg_publish_local.png "RemoteDBG_Publish_Local")

    Web Forms 앱에 대 한 선택 **사용자 지정** 게시 대화 상자에서 프로필 이름을 입력 하 고 선택 **확인**합니다.

3. **게시**를 클릭합니다.

    Visual Studio는 프로젝트 폴더에 게시합니다. 진행률 출력 창에 표시 됩니다.

4. 에 **게시** 대화 상자에서 클릭는 **설정** 링크를 선택한 다음 선택에서 **설정을** 탭 합니다.

5. 구성을 설정 **디버그**선택, **게시 하기 전에 모든 기존 파일 삭제**, 클릭 하 고 **저장**합니다.

    > [!NOTE]
    > 릴리스 빌드를 사용 하는 경우 게시 하는 경우 web.config 파일에서 디버깅이 비활성화할 수 있습니다.

6. **게시**를 클릭합니다.

    ![RemoteDBG_Publish_Debug_Config](../media/remotedbg_publish_debug_config.png "RemoteDBG_Publish_Debug_Config")
    
    응용 프로그램에서 게시 한 **디버그** 로컬 폴더에 프로젝트의 구성 합니다.

5. ASP.NET 응용 프로그램에 대해 구성 된 로컬 디렉터리에 Visual Studio 컴퓨터에서 ASP.NET 프로젝트 디렉터리를 복사 (이 예제에서는 **C:\Publish**) Windows Server 컴퓨터에 있습니다. 이 자습서에서는 수동으로 복사 하는 PowerShell, Xcopy 또는 Robocopy와 같은 다른 도구를 사용할 수 있지만 가정 합니다.

    > [!CAUTION]
    >  변경 하려면 코드 또는 다시 작성 해야 할 경우에 다시 게시 하 고이 단계를 반복 해야 합니다. 원격 컴퓨터에 복사한 실행 파일은 로컬 소스 및 기호와 정확히 일치해야 합니다.

6. Windows Server에서 있습니다 실행할 수 있는지 확인 앱 올바르게 브라우저에서 앱을 열어 합니다.

    앱은 제대로 실행 되지 않는, 또는 서버와 Visual Studio 컴퓨터에 설치 된 ASP.NET 버전 간의 하는 불일치가 있을 수 있습니다 IIS 또는 웹 사이트 구성에 문제가 있을 수 있습니다. 이전 단계를 다시 확인 합니다.