---
title: "새 연결 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8a93c287-2834-4a83-a590-bdc3fe8d293f
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: accf99d7a1d230bac64ebd8ebf9c9f1071ad1876
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="add-new-connections"></a>새 연결 추가
데이터베이스 또는 서비스에 대 한 연결을 테스트 하 고 데이터베이스의 내용과 스키마를 사용 하 여 탐색할 수 **서버 탐색기**, **클라우드 탐색기**, 또는 **SQL Server 개체 탐색기**. 이러한 창은의 기능을 어느 정도 까지는 겹칩니다. 기본 차이점은:  
  
 - 서버 탐색기  
 기본적으로 Visual Studio에 설치 합니다. 연결을 테스트 하 고 SQL Server 데이터베이스, ADO.NET 공급자가 설치 되어 있는 다른 데이터베이스 및 일부 Azure 서비스가 볼 데 사용할 수 있습니다. 또한 시스템 성능 카운터, 이벤트 로그 등 메시지 큐 하위 수준 개체를 보여 줍니다. 데이터 원본에는 ADO.NET 공급자가 없습니다, 여기에서 표시 되지 않습니다 되지만 사용할 수 있습니다 여전히 Visual Studio에서 프로그래밍 방식으로 연결 하 여 합니다.  
  
 - 클라우드 탐색기  
 선택 하 여 수동으로 Visual Studio extension이 창을 설치 **도구** > **확장명 및 업데이트** > **온라인**  >  **Visual Studio 갤러리**합니다. 탐색 하 고 Azure 서비스에 연결에 대 한 특수 기능을 제공 합니다.  
  
 - SQL Server 개체 탐색기  
 SQL Server Data Tools와 함께 설치 하 고 아래에 표시 된 **보기** 메뉴. 발생 표시 되지 않으면로 이동 **프로그램 및 기능** 제어판에서 Visual Studio를 찾아 선택 합니다 **변경** 를 다시 SQL Server Data Tools에 대 한 확인란을 선택한 후 설치 프로그램을 실행 합니다. 사용 하 여 **SQL Server 개체 탐색기** 보기 SQL 데이터베이스 (경우에 ADO.NET 공급자)에 새 데이터베이스를 만들, 스키마 수정, 저장된 프로시저를 만들, 연결 문자열을 검색할 하며, 해당 데이터를 보고 합니다. 없는 ADO.NET 공급자가 설치 된 SQL 데이터베이스는 여기에서 표시 되지 않습니다 되지만 여전히에 연결할 수 있습니다에 프로그래밍 방식으로.  
  
## <a name="add-a-connection-in-server-explorer"></a>서버 탐색기에서 연결을 추가 합니다.  
 데이터베이스에 연결을 만들려면 클릭는 **연결 추가** 아이콘 **서버 탐색기**, 마우스 오른쪽 단추로 클릭 하거나 **서버 탐색기** 에 **데이터 연결** 노드 선택한 **연결 추가**합니다. 여기에서 다른 서버, SharePoint 서비스 또는 Azure 서비스에 데이터베이스에 연결할 수 있습니다.  
  
 ![서버 탐색기 새 연결 아이콘](../data-tools/media/raddata-server-explorer-new-connection-icon.png "raddata 서버 탐색기에 대 한 새 연결 상태 아이콘")  
  
 그러면는 **연결 추가** 대화 상자. 여기에서 SQL Server LocalDB 인스턴스의 이름을 입력 했습니다 했습니다.  
  
 ![새 연결 추가](../data-tools/media/raddata-add-new-connection-dialog.png "raddata 추가 새 연결 대화 상자")  
  
## <a name="change-the-provider"></a>공급자 변경  
 데이터 소스를 것을 원하지 않을 경우 클릭는 **변경** 단추를 새 데이터 소스 및/또는 새 ADO.NET 데이터 공급자를 선택 합니다. 새 공급자를 구성한 방법에 따라 자격 증명을 요청할 수 있습니다.  
  
 ![데이터 공급자 AD0.NET 변경](../data-tools/media/raddata-change-ad0.net-data-provider.png "raddata AD0.NET 데이터 공급자 변경")  
  
## <a name="test-the-connection"></a>연결 테스트  
 데이터 소스를 선택한 후 클릭 **연결 테스트**합니다. 성공 하지 못한 할 경우 문제를 해결 하는 공급 업체의 설명서에 따라 합니다.  
  
 ![연결 테스트](../data-tools/media/raddata-test-connection.png "raddata 연결 테스트")  
  
 만들 준비가 된 테스트에 성공 하면는 *데이터 소스*, 의미 있는 Visual Studio 용어는 *데이터 모델* 기본 데이터베이스 또는 서비스를 기반으로 하는 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [.NET용 Visual Studio 데이터 도구](../data-tools/visual-studio-data-tools-for-dotnet.md)