---
title: "원격 디버깅용 Windows 방화벽을 구성 | Microsoft Docs"
ms.custom: 
ms.date: 05/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66e3230a-d195-4473-bbce-8ca198516014
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f7458c2f35bfd29c53b939b6300d2759f0e7897f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="configure-the-windows-firewall-for-remote-debugging"></a>원격 디버깅을 위해 Windows 방화벽 구성
이 항목에서는 다음 운영 체제를 실행하는 컴퓨터에서 원격 디버깅을 사용하도록 방화벽을 구성하는 방법을 설명합니다.  
  
-   Windows 10  
  
-   Windows 8/8.1  
  
-   Windows 7   
  
-   Windows Server 2012 R2  

-   Windows Server 2012
  
-   Windows Server 2008 R2 
  
 디버그 중인 네트워크가 방화벽으로 보호되지 않는 경우에는 이 구성이 필요하지 않습니다. 그렇지 않은 경우 Visual Studio를 호스트하는 컴퓨터와 디버그해야 하는 원격 컴퓨터 둘 다에서 방화벽 구성을 변경해야 합니다.  
  
 **IPSec** 네트워크에서 IPSec을 사용하여 통신을 수행해야 하는 경우 Visual Studio 호스트 컴퓨터와 원격 컴퓨터 둘 다에서 추가 포트를 열어야 합니다.  
  
 **웹 서버** 원격 웹 서버를 디버그하는 경우 원격 컴퓨터에서 추가 포트를 열어야 합니다. (IIS에 대 한 포트 80 열려 있어야 합니다.)  
  
 두 컴퓨터에서 동일한 운영 체제를 실행할 필요는 없습니다. 예를 들어 Visual Studio 컴퓨터는 Windows 10을 실행하고 원격 컴퓨터는 Windows Server 2012 R2를 실행할 수 있습니다.      
  
## <a name="ports-on-the-remote-computer-that-enable-remote-debugging"></a>원격 디버깅을 사용할 수 있도록 하는 원격 컴퓨터의 포트  
  
|||||  
|-|-|-|-|  
|**포트**|**들어오는/나가는 포트**|**프로토콜**|**설명**|   
|4022|들어오는|TCP|VS 2017에 대 한. 포트 번호는 각 Visual Studio 버전마다 2씩 증가합니다. 자세한 내용은 참조 [Visual Studio 원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md)합니다.|  
|4023|들어오는|TCP|VS 2017에 대 한. 포트 번호는 각 Visual Studio 버전마다 2씩 증가합니다. (만 원격으로 사용 되는 디버그 원격 디버거의 64 비트 버전에서 32 비트 프로세스입니다.) 자세한 내용은 참조 [Visual Studio 원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md)합니다.| 
|3702|나가는 포트|UDP|(선택 사항) 원격 디버거 검색에 필요합니다.|    
  
## <a name="how-to-configure-ports-in-windows-firewall"></a>Windows 방화벽에서 포트를 구성하는 방법  

Visual Studio 또는 원격 디버거를 설치할 때 소프트웨어는 올바른 포트를 열어야 하려고 합니다. 그러나 (예: 타사 방화벽을 사용 하 여) 일부 시나리오에서는 수동으로 포트를 열어야 할 수 있습니다. 포트가 열려 있는지 확인 해야 하는 경우 참조 [문제 해결](#troubleshooting)합니다. 포트 열기에 대 한 몇 가지 지침을 이전 버전의 Windows에서 달라질 수 있습니다.

포트를 열려면:
  
1. 열기는 **시작** 메뉴, 검색할 **고급 보안이 포함 된 Windows 방화벽**합니다.

2. 그런 다음 선택 **인바운드 규칙 > 새 규칙 > 포트**, 클릭 하 고 **다음**합니다. (보내는 규칙에 대 한 선택 **아웃 바운드 규칙** 대신 합니다.)

3. 선택 **TCP** 또는 **UDP**포트 번호에 따라 합니다.

4. 아래 **특정 로컬 포트**, 포트 번호를 입력, 클릭 **다음**합니다.

5. 클릭 **연결 허용** 클릭 하 고 **다음**합니다.

6. 포트에 대 한 고 클릭 하나 이상의 네트워크 종류도 선택 **다음**합니다.

    선택한 유형은 원격 컴퓨터가 연결된 네트워크를 포함해야 합니다.
7. 이름을 추가 합니다 (예를 들어 **msvsmon**, **IIS**, 또는 **웹 배포**) 규칙과 클릭에 대 한 **마침**합니다.

    인바운드 규칙 또는 아웃 바운드 규칙 목록에 새 규칙이 표시 됩니다.

## <a name="troubleshooting"></a>문제 해결

응용 프로그램에 연결 하 고 원격 디버거를 사용 하는 데 문제가 있는 경우 올바른 포트가 열려 있는지 확인 해야 합니다.

### <a name="verify-that-ports-are-open-in-the-windows-firewall-on-the-visual-studio-computer"></a>Visual Studio 컴퓨터에서 Windows 방화벽에서 열려 있는 포트가 있는지 확인  
 Windows 방화벽을 구성하기 위한 지침은 운영 체제마다 약간 다릅니다. Windows 8/8.1, Windows 10 및 Windows Server 2012, 단어에서 **앱** 사용 됩니다; Windows 7 또는 Windows Server 2008, 단어 **프로그램** 사용 됩니다.  다음 단계는 사용 하 여 단어 **앱**합니다.  
  
1.  Windows 방화벽 페이지를 엽니다. **시작** 메뉴 검색 상자에 **Windows 방화벽**을 입력합니다.  
  
2.  **Windows 방화벽을 통해 앱 또는 기능 허용**을 클릭합니다.  
  
3.  **허용된 앱 및 기능** 목록에서 **Visual Studio 원격 디버거 검색**을 찾습니다. 표시되는 경우 선택되었으며 하나 이상의 네트워크 종류도 선택되었는지 확인합니다.  
  
4.  **Visual Studio 원격 디버거 검색** 이 표시되지 않는 경우 **다른 앱 허용**을 클릭합니다. 하면 여전히 표시 되지 않는 경우에 **앱 추가** 창 클릭 **찾아보기** 이동한 다음  **\<Visual Studio 설치 디렉터리 > \Common7\IDE\Remote디버거**. 응용 프로그램에 대한 적절한 폴더(x86, x64, Appx)를 찾은 다음 **msvsmon.exe**를 선택합니다. **추가**를 클릭합니다.  
  
5.  에 **허용 되는 앱 및 기능** 목록에서 **Visual Studio 원격 디버거**합니다. 원격 디버깅 모니터에서 통신하려는 네트워크 종류(**도메인, 홈/회사(개인), 공용**)를 하나 이상 선택합니다. 종류는 Visual Studio 컴퓨터가 연결된 네트워크를 포함해야 합니다. 

### <a name="verify-that-ports-are-open-in-the-windows-firewall-on-the-remote-computer"></a>원격 컴퓨터에서 Windows 방화벽에서 열려 있는 포트가 있는지 확인  
 원격 디버깅 구성 요소는 원격 컴퓨터에 설치하거나 공유 디렉터리에서 실행할 수 있습니다. 두 경우 모두 원격 컴퓨터의 방화벽을 구성해야 합니다. 원격 디버깅 구성 요소는 다음 위치에 있습니다.  
  
 **\<Visual Studio 설치 디렉터리 > \Common7\IDE\Remote 디버거**  
  
 Windows 방화벽을 구성하기 위한 지침은 운영 체제마다 약간 다릅니다. Windows 8/8.1, Windows 10 및 Windows Server 2012, 단어에서 **앱** 사용 됩니다; Windows 7 또는 Windows Server 2008, 단어 **프로그램** 사용 됩니다.  다음 단계는 사용 하 여 단어 **앱**합니다.  
  
1.  Windows 방화벽 페이지를 엽니다. **시작** 메뉴 검색 상자에 **Windows 방화벽**을 입력합니다.  
  
2.  **Windows 방화벽을 통해 앱 또는 기능 허용**을 클릭합니다.  
  
3.  에 **허용 되는 앱 및 기능** 목록에서 찾도록 **Visual Studio 원격 디버거**합니다. 표시되는 경우 선택되었으며 하나 이상의 네트워크 종류도 선택되었는지 확인합니다.  
  
4.  경우 **Visual Studio 원격 디버거** 가 나타나지 않으면 클릭 **다른 앱 허용**합니다. 하면 여전히 표시 되지 않는 경우에 **추가 응용 프로그램 창**, 클릭 **찾아보기** 이동한 다음  **\<Visual Studio 설치 디렉터리 > \Common7\IDE\Remote디버거**. 응용 프로그램에 대한 적절한 폴더(x86, x64, Appx)를 찾은 다음 **msvsmon.exe**를 선택합니다. **추가**를 클릭합니다.  
  
5.  에 **앱이 허용 된** 목록에서 **Visual Studio 원격 디버거**합니다. 원격 디버깅 모니터에서 통신하려는 네트워크 종류(**도메인, 홈/회사(개인), 공용**)를 하나 이상 선택합니다. 종류는 Visual Studio 컴퓨터가 연결된 네트워크를 포함해야 합니다. 

### <a name="managed-or-native-compatibility-mode-open-additional-ports-on-the-remote-computer"></a>(관리 또는 네이티브 호환성 모드) 원격 컴퓨터에서 추가 포트를 열려면

디버거에 대 한 호환 모드를 사용 하는 경우 (**도구 > 옵션 > 디버깅**), 추가 포트를 열 수를 해야 합니다. 호환성 모드에서는 레거시 버전의 디버거 및 서로 다른 포트는 필요 합니다.

> [!NOTE]
> 레거시 디버거 버전이 Visual Studio 2010의 디버거 합니다.
  
|||||  
|-|-|-|-|  
|**포트**|**들어오는/나가는 포트**|**프로토콜**|**설명**|  
|135, 139, 445|나가는 포트|TCP|필수.|  
|137, 138|나가는 포트|UDP|필수.|  
|500, 4500|나가는 포트|UDP|도메인 정책에 따라 IPSec을 통해 네트워크 통신을 수행해야 하는 경우에 필요합니다.|  
|80|나가는 포트|TCP|웹 서버 디버깅에 필요합니다.|
  
## <a name="see-also"></a>참고 항목  
 [원격 디버깅](../debugger/remote-debugging.md)