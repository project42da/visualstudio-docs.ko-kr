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
ms.openlocfilehash: c22ba73b464f91bf3036541304cdf94e8660970d
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
---
1. Visual Studio에서 웹 배포 된 응용 프로그램을 배포 하려는 경우 서버에서 최신 버전의 웹 배포를 설치 합니다.

    웹 배포를 설치 하려면 사용 된 [웹 플랫폼 설치 관리자 (WebPI)](https://www.microsoft.com/web/downloads/platform.aspx)합니다. (선택 IIS에서 웹 플랫폼 설치 관리자 링크를 찾으려면 **IIS** 서버 관리자의 왼쪽된 창에서. 서버를 마우스 오른쪽 단추로 클릭 하 고 선택 **인터넷 정보 서비스 (IIS) 관리자**.)

    웹 플랫폼 설치 관리자에서 알게 웹 배포 응용 프로그램 탭에서. 설치 관리자에서 직접 가져올 수도 있습니다는 [Microsoft 다운로드 센터](https://www.microsoft.com/search/result.aspx?q=webdeploy&form=dlc)합니다. 

2. 열어 웹 배포 제대로 실행 중인지 확인 **제어판 > 시스템 및 보안 > 관리 도구 > 서비스** 있는지 확인 하 고 **웹 배포 에이전트 서비스가** 실행 되 고 ( 서비스 이름이 다른 경우 이전 버전)

    에이전트 서비스를 실행 하지 않는 경우이 시작 합니다. 로 이동 하는 표시 되지 않으면 하지 전혀, **제어판 > 프로그램 > 프로그램 제거**, 찾을 **Microsoft 웹 배포 <version>** 합니다. 하기로 **변경** 설치를 선택 해야 하 고 **로컬 하드 드라이브에 설치 됩니다** 웹 배포 구성 요소에 대 한 합니다. 변경 설치 단계를 완료 합니다.