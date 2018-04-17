---
title: 원격 디버거 포트 할당 | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 05/18/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 238bb4ec-bb00-4c2b-986e-18ac278f3959
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3872f11dff614e8fae4deeace7cdf301cd9b5e1c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="remote-debugger-port-assignments"></a>원격 디버거 포트 할당
Visual Studio 원격 디버거는 응용 프로그램 또는 백그라운드 서비스로 실행할 수 있습니다. 응용 프로그램으로 실행되는 경우 다음과 같이 기본적으로 할당되는 포트를 사용합니다.  

-   Visual Studio 2017: 4022

-   Visual Studio 2015: 4020  
  
-   Visual Studio 2013: 4018  
  
-   Visual Studio 2012: 4016  
  
 즉, 원격 디버거에 할당되는 포트 번호가 각 릴리스마다 2씩 증가합니다. 원하는 대로 다른 포트 번호를 설정할 수 있습니다. 이후 섹션에서 포트 번호를 설정하는 방법을 설명합니다.  
  
## <a name="the-remote-debugger-port-on-32-bit-operating-systems"></a>32비트 운영 체제의 원격 디버거 포트  
 (Visual Studio 2017)에 TCP 4022은 기본 포트 이며 모든 시나리오에 필요 합니다. 명령줄 또는 원격 디버거 창에서 구성할 수 있습니다.  
  
 원격 디버거 창에서 클릭 **도구 > 옵션**, TCP/IP 포트 번호를 설정 합니다.  
  
 명령줄에서 시작으로 원격 디버거는 **/포트** 전환: **msvsmon /port \<포트 번호 >**합니다.  
  
 원격 디버깅 도움말에서 모든 원격 디버거 명령줄 스위치를 찾을 수 있습니다 (키를 눌러 **F1** 키를 누르거나 **도움말 > 사용량** 원격 디버거 창에서).  
  
## <a name="the-remote-debugger-port-on-64-bit-operating-systems"></a>64비트 운영 체제의 원격 디버거 포트  
 64 비트 버전의 원격 디버거를 시작할 때 기본적으로 4022 포트를 사용 합니다.  32 비트 프로세스를 디버깅 하는 경우 64 비트 버전의 원격 디버거 포트 4023에서 32 비트 버전의 원격 디버거를 시작 합니다. 32 비트 원격 디버거를 실행 하는 경우에 4022를 사용 하 여 및 4023 사용 되지 않습니다.  
  
 이 포트는 명령줄에서 구성할 수 있는: **Msvsmon /wow64port \<포트 번호 >**합니다.  
  
## <a name="the-discovery-port"></a>검색 포트  
 UDP 3702는 네트워크에서 실행 중인 원격 디버거 인스턴스를 찾는 데 사용됩니다(예: **프로세스에 연결** 대화 상자의 **찾기** 대화 상자). 원격 디버거를 실행하는 컴퓨터를 검색하는 용도로만 사용되므로 대상 컴퓨터의 컴퓨터 이름 또는 IP 주소를 확인하는 다른 방법이 있을 경우 선택 사항입니다. 이는 검색에 사용되는 표준 포트이므로 포트 번호를 구성할 수 없습니다.  
  
 검색을 사용하지 않으려는 경우 검색을 사용하지 않도록 설정하여 명령줄에서 msvsmon을 시작할 수 있습니다(  **Msvsmon /nodiscovery**).  
  
## <a name="remote-debugger-ports-on-azure"></a>Azure의 원격 디버거 포트  
 Azure의 원격 디버거에서 사용되는 포트는 다음과 같습니다. 클라우드 서비스의 포트는 개별 VM의 포트에 매핑됩니다. 모든 포트는 TCP입니다.  
  
||||  
|-|-|-|  
|**연결**|**클라우드 서비스의 포트**|**VM의 포트**|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Connector|30400|30398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Forwarder|31400|31398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.FileUpload|32400|32398|  
  
## <a name="see-also"></a>참고 항목  
 [원격 디버깅](../debugger/remote-debugging.md)