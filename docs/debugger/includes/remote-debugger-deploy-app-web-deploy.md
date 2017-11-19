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
ms.openlocfilehash: 27cff46f5a68ef28f247aa159a2b8be5db56b0fe
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
웹 플랫폼 설치 관리자를 사용 하 여 웹 배포를 설치한 경우 Visual Studio에서 직접 앱을 배포할 수 있습니다.

1. 관리자 권한으로 Visual Studio를 시작 하 고 프로젝트를 다시 여세요.

    웹 배포를 사용 하 여 앱을 배포 하려면 관리자 권한이 필요 합니다.

2. **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.

3. 에 대 한 **게시 대상 선택**선택, **IIS, FTP, 등** 클릭 **게시**합니다.

    ![RemoteDBG_Publish_IISl](../media/remotedbg_iis_profile.png "RemoteDBG_Publish_IIS")

4. IIS 설치에 대 한 수정 사항을 구성 매개 변수를 입력 합니다.

    ![RemoteDBG_Publish_WebDeployl](../media/remotedbg_iis_webdeploy_config.png "RemoteDBG_Publish_WebDeploy")

    다음 단계는 호스트 이름에서 유효성을 검사 하려고 하면 해결 되지 않으면는 **서버** 텍스트 상자에서 IP 주소를 지정 하십시오. 포함 `http://` 의 접두사로 **서버** 필드입니다.  에 포트 80을 사용 하면는 **서버** 텍스트 상자의 하 고 포트 80이 고 방화벽에서 열려 있는지 확인 합니다.

6. 클릭 **다음**, 선택는 **디버그** 구성을 선택 하 고 **대상에서 추가 파일 제거** 아래는 **파일 게시** 옵션.

    > [!NOTE]
    > 릴리스 구성을 선택 하면 게시 하는 경우 web.config 파일에서 디버깅이 비활성화할 수 있습니다.

5. 클릭 **Prev**를 선택한 후 **유효성 검사**합니다. 연결 설정의 유효성을 검사 하는 경우에 게시 하도록 시도할 수 있습니다.

6. 클릭 **게시** 에서는 앱을 게시 합니다.

    출력 탭에는 게시 성공 하 고 브라우저에는 다음 응용 프로그램 열고 경우 표시 됩니다.

    웹 배포에 대해 언급 오류가 발생할 경우 웹 배포 설치 단계를 다시 확인 하 고 올바른 포트가 열려 있는지 확인 (서버에서 열어야 하는 8172 포트 필요도 웹 배포).

    응용 프로그램 배포를 성공적으로 표시 되지만 제대로 실행 되지 않는 IIS 구성, ASP.NET 설치 프로그램 또는 웹 사이트 구성에 문제가 있을 수 있습니다. Windows 서버에서 웹 사이트에서 IIS 더 구체적인 오류 메시지에 대 한 연 후 이전 단계를 다시 확인 합니다.