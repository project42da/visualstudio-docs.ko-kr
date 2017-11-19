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
ms.openlocfilehash: 05a288a2d8dff776d8a5d3faea47b06d101f2ea3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
원격 컴퓨터에 관리 권한이 있어야 합니다.  
  
1.  원격 디버거 응용 프로그램을 찾습니다. (이 설치 되어 있는, 위치에 msvsmon.exe를 찾거나 여 시작 메뉴 및 검색에 대 한 열 **원격 디버거**.)
  
     원격 서버에 원격 디버거를 실행 하는 경우 원격 디버거 응용 프로그램을 마우스 오른쪽 단추로 클릭 하 고 선택할 수 **관리자 권한으로 실행**합니다. 원격 서버에서 실행 되지 않는 경우 바로 정상적으로 시작 합니다.
  
3.  처음으로 (또는 구성 하기 전에) 원격 도구를 시작 하 고, **원격 디버깅 구성** 대화 상자가 나타납니다.  
  
     ![RemoteDebuggerConfWizardPage](../media/remotedebuggerconfwizardpage.png "RemoteDebuggerConfWizardPage")  
  
4.  Windows 서비스 API (Windows Server 2008 r 2 에서만 발생 함)는 설치 되지 않은 경우 선택 된 **설치** 단추입니다.  
  
5.  원격 도구를 사용하려는 네트워크 종류를 선택합니다. 하나 이상의 네트워크 형식을 선택해야 합니다. 컴퓨터가 도메인을 통해 연결된 경우 첫 번째 항목을 선택해야 합니다. 컴퓨터가 작업 그룹 또는 홈 그룹을 통해 연결된 경우 두 번째 또는 세 번째 항목을 적절하게 선택해야 합니다.  
  
6.  선택 **원격 디버깅 구성** 방화벽을 구성 하 고 도구를 시작 합니다.  
  
7.  구성이 완료되면 원격 디버거 창이 나타납니다.
  
     ![RemoteDebuggerWindow](../media/remotedebuggerwindow.png "RemoteDebuggerWindow")
  
     이제 원격 디버거를 연결을 기다리고 있습니다. 서버 이름의 기록 하 고 나중에 Visual Studio에서 사용 하는 구성와 일치 해야 하기 때문에 포트 표시 되는 번호입니다.  
  
 디버깅 및 원격 디버거를 중지 해야 할 완료 되 면 클릭 **파일 > 종료** 창에 있습니다. 다시 시작할 수 있습니다는 **시작** 메뉴 또는 명령줄에서:  
  
 **\<Visual Studio 설치 디렉터리 > \Common7\IDE\Remote 디버거\\< x86, x64 또는 Appx\msvsmon.exe**합니다.  