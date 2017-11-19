---
title: ".Mdf 파일을 업그레이드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server Express
- SQL Server LocalDB
- LocalDB
- SQLEXPRESS
- upgrading SQLExpress to SQLExpress
- upgrading to LocalDB
ms.assetid: 14ca6f76-f80e-4926-8020-3fee2d802b75
caps.latest.revision: "33"
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.technology: vs-data-tools
ms.openlocfilehash: 8ed511eed7b0ace46bbc61c1d486ade608d4b5a5
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="upgrade-mdf-files"></a>.Mdf 파일을 업그레이드
이 항목에서는 새 버전의 Visual Studio를 설치한 후 데이터베이스 파일 (.mdf)을 업그레이드 하기 위한 옵션을 설명 합니다. 다음 작업에 대 한 지침이 포함 됩니다.  
  
-   최신 버전의 SQL Server Express LocalDB를 사용 하려면 데이터베이스 파일을 업그레이드  
  
-   최신 버전의 SQL Server Express를 사용 하려면 데이터베이스 파일을 업그레이드  
  
-   Visual Studio에서 데이터베이스 파일에서 작동 하지만 이전 버전의 SQL Server Express 또는 LocalDB와의 호환성을 유지 합니다.  
  
-   기본 데이터베이스 엔진의 SQL Server Express 확인  
  
이전 버전의 SQL Server Express 또는 LocalDB를 사용 하 여 만든 데이터베이스 파일 (.mdf)을 포함 하는 프로젝트를 열려면 Visual Studio를 사용할 수 있습니다. 그러나 Visual Studio를 사용 하 여 프로젝트 개발을 계속 하려면 해당 버전의 SQL Server Express 또는 LocalDB Visual Studio와 동일한 컴퓨터에 설치 되어 있어야 하거나 데이터베이스 파일을 업그레이드 해야 합니다. 데이터베이스 파일을 업그레이드 하는 경우에 이전 버전의 SQL Server Express 또는 LocalDB를 사용 하 여 액세스할 수 없습니다.  
  
도 메시지가 표시 되는 파일의 버전의 SQL Server Express 또는 현재 설치 된 LocalDB 인스턴스와 호환 되지 않는 경우 이전 버전의 SQL Server Express 또는 LocalDB를 통해 생성 된 데이터베이스 파일을 업그레이드 합니다. 이 문제를 해결 하려면 Visual Studio 하 라는 메시지가 나타납니다 파일을 업그레이드 합니다.  
  
> [!IMPORTANT]
> 업그레이드 하기 전에 데이터베이스 파일을 백업 하는 것이 좋습니다.  
  
> [!WARNING]
> LocalDB 2014 (V12) 32 비트 정수를 (V13) LocalDB 2016 이상에서 생성 된.mdf 파일을 업그레이드 하는 경우 32 비트 버전의 LocalDB에 파일을 다시 열 수 없습니다.
  
데이터베이스를 업그레이드 하기 전에 다음 조건을 고려 합니다.  
  
-   이전 버전과 새 버전의 Visual Studio에서 프로젝트에 작업 하려는 경우 업그레이드 하지 마십시오.  
  
-   SQL Server Express 보다는 LocalDB를 사용 하는 환경에서 응용 프로그램을 사용할 경우 업그레이드 하지 마십시오.  
  
-   LocalDB 동의 하지 않는 때문에 응용 프로그램에서 원격 연결을 사용 하는 경우를 업그레이드 하지 않음.  
  
-   응용 프로그램에서 인터넷 정보 서비스 (IIS)를 사용 하는 경우 업그레이드 하지 마십시오.  
  
-   샌드박스 환경에서 데이터베이스 응용 프로그램을 테스트 하려고 하지만 데이터베이스 관리 하지 않으려는 경우 업그레이드를 고려 합니다.  
  
### <a name="to-upgrade-a-database-file-to-use-the-localdb-version"></a>LocalDB 버전을 사용 하려면 데이터베이스 파일을 업그레이드 하려면
  
1.  **서버 탐색기**, 선택는 **연결할 데이터베이스** 단추입니다.  
  
2.  에 **연결 추가** 대화 상자에서 다음 정보를 지정 합니다.  
  
    -   **데이터 원본**:`Microsoft SQL Server (SqlClient)`  
  
    -   **서버 이름**:  
  
        -   기본 버전을 사용 하려면: `(localdb)\MSSQLLocalDB`합니다.  설치 된 버전의 Visual Studio 및 첫 번째 LocalDB 인스턴스를 만들 때에 따라 ProjectV12 또는 ProjectV13를 지정 합니다. **MSSQLLocalDB** 노드에서 **SQL Server 개체 탐색기** 를 가리키는지 버전을 보여 줍니다.  
  
        -   특정 버전을 사용 하려면: `(localdb)\ProjectsV12` 또는 `(localdb)\ProjectsV13`여기서 V12 LocalDB 2014 고 V13 LocalDB 2016 인지 합니다.  
  
    -   **데이터베이스 파일 첨부**: 주.mdf 파일의 실제 경로입니다.  
  
    -   **논리적 이름**: 파일과 함께 사용 하려는 이름입니다.  
  
3.  **확인** 단추를 선택합니다.  
  
4.  프롬프트 메시지가 나타날 때 선택 된 **예** 단추 파일을 업그레이드 합니다.  
  
    데이터베이스를 업그레이드 하 고 LocalDB 데이터베이스 엔진에 연결 된 이전 버전의 LocalDB와 호환 되는 더 이상.  
  
연결에 대 한 바로 가기 메뉴를 열고 다음을 선택 하 여 LocalDB를 사용 하도록 SQL Server Express 연결을 수정할 수도 있습니다 **연결 수정**합니다. 에 **연결 수정** 대화 상자에서 서버 이름을 변경한 `(LocalDB)\MSSQLLocalDB`합니다. 에 **고급 속성** 대화 상자에서 다음 사항을 확인 **사용자 인스턴스** 로 설정 된 **False**합니다.

### <a name="to-upgrade-a-database-file-to-use-the-sql-server-express-version"></a>SQL Server Express 버전을 사용 하려면 데이터베이스 파일을 업그레이드 하려면  
  
1.  데이터베이스에 연결에 대 한 바로 가기 메뉴에서 선택 **연결 수정**합니다.  
  
2.  에 **연결 수정** 대화 상자는 **고급** 단추입니다.  
  
3.  에 **고급 속성** 대화 상자는 **확인** 서버 이름을 변경 하지 않고 단추입니다.  
  
    데이터베이스 파일을 SQL Server Express의 현재 버전과 일치 하도록 업그레이드 됩니다.  
  
### <a name="to-work-with-the-database-in-visual-studio-but-retain-compatibility-with-sql-server-express"></a>Visual Studio에서 데이터베이스와 함께 작동 하지만 SQL Server Express와 호환성을 유지 하려면  
  
-   Visual Studio에서 업그레이드 하지 않고도 프로젝트를 엽니다.  
  
    -   프로젝트를 실행 하려면 선택은 **F5** 키입니다.  
  
    -   데이터베이스를 편집 하려면에.mdf 파일을 엽니다 **솔루션 탐색기**에서 노드를 확장 하 고 **서버 탐색기** 데이터베이스와 함께 작동 하도록 합니다.  
  
### <a name="to-make-sql-server-express-the-default-database-engine"></a>기본 데이터베이스 엔진의 SQL Server Express 확인 하려면  
  
1.  메뉴 모음에서 선택 **도구**, **옵션**합니다.  
  
2.  에 **옵션** 대화 상자에서 **데이터베이스 도구** 옵션을 선택한 후 **데이터 연결**합니다.  
  
3.  에 **SQL Server 인스턴스 이름** 텍스트 상자를 사용 하려면 LocalDB 또는 SQL Server Express 인스턴스의 이름을 지정 합니다. 인스턴스 이름이 없는 경우 지정 `.\SQLEXPRESS or (LocalDB)\MSSQLLocalDB`합니다.  
  
4.  **확인** 단추를 선택합니다.  
  
    SQL Server Express 응용 프로그램에 대 한 기본 데이터베이스 엔진 됩니다.

## <a name="see-also"></a>참고 항목
[Visual Studio에서 데이터 액세스](accessing-data-in-visual-studio.md)
