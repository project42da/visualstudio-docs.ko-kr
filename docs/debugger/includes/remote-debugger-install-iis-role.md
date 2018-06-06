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
ms.openlocfilehash: 103000c2ded944236762ffd55603877ece7b7968
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34768224"
---
이러한 단계에만 IIS의 기본 구성을 보여 줍니다. 자세한 내용은 하거나 Windows 데스크톱 컴퓨터에 설치 하려면 참조 [를 IIS에 게시](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration) 또는 [IIS 8.0를 사용 하 여 ASP.NET 3.5 및 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)합니다.

Windows Server 운영 체제에 대 한 사용는 **역할 및 기능 추가** 통해 마법사는 **관리** 링크 또는 **대시보드** 링크를 **서버관리자**. **서버 역할** 단계에서 **웹 서버(IIS)** 확인란을 선택합니다.

![서버 역할 선택 단계에서 선택된 웹 서버 IIS 역할](../media/remotedbg-server-roles-ws2012.png)

**역할 서비스** 단계에서 원하는 IIS 역할 서비스를 선택하거나 제공된 기본 역할 서비스를 받아들입니다. 배포를 사용 하 여 사용 하도록 설정 하려는 경우 설정 및 웹 배포 게시 되어 있는지 확인 합니다 **IIS 관리 스크립트 및 도구** 을 선택 합니다.

웹 서버 역할 및 서비스를 설치 하는 확인 단계를 진행 합니다. 웹 서버(IIS) 역할을 설치한 후에 서버/IIS를 다시 시작할 필요가 없습니다.