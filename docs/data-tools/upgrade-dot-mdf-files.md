---
title: "방법: LocalDB로 업그레이드하거나 SQL Server Express 계속 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "LocalDB"
  - "SQL Server Express"
  - "SQL Server LocalDB"
  - "SQLEXPRESS"
  - "SQLExpress를 SQLExpress로 업그레이드"
  - "LocalDB로 업그레이드"
ms.assetid: 14ca6f76-f80e-4926-8020-3fee2d802b75
caps.latest.revision: 33
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 방법: LocalDB로 업그레이드하거나 SQL Server Express 계속 사용
이 항목을 설치한 후 데이터베이스 파일 \(.mdf\)을 업그레이드 하는 옵션 설명 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] 및 다음 작업에 대 한 지침이 포함 되어 있습니다.  
  
-   Localdb를 사용 하는 데이터베이스 파일 업그레이드  
  
-   SQL Server 익스프레스의 최신 버전을 사용 하는 데이터베이스 파일 업그레이드  
  
-   작동 데이터베이스 파일에서 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] 호환성을 유지 합니다.[!INCLUDE[ssKatmai_exp](../data-tools/includes/sskatmai_exp_md.md)]  
  
-   SQL Server 익스프레스 기본 데이터베이스 엔진 확인  
  
 사용할 수 있는 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] SQL Server Express의 이전 버전을 사용 하 여 만든 데이터베이스 파일 \(.mdf\) 포함 된 프로젝트를 엽니다.  그러나 개발 프로젝트에서 계속 하려면 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], Visual Studio 같은 시스템에 설치 된 SQL Server Express 버전 여야 또는 SQL Server LocalDB Express를 사용 하는 데이터베이스 파일을 업그레이드 해야 합니다.  데이터베이스 파일을 업그레이드 하는 경우 이전 버전의 SQL Server Express에 액세스할 수 없습니다.  
  
 사용 하 여 만든 데이터베이스 파일을 업그레이드 하 라는 메시지가 표시도 [!INCLUDE[sql_Denali_exp](../data-tools/includes/sql_denali_exp_md.md)] 파일의 버전의 SQL Server를 현재 설치 된 Express 인스턴스와 호환 아닌 경우.  문제를 해결 하려면 Visual Studio 파일의 SQL Server Express 최신 버전으로 업그레이드 하 라는 메시지가 나타납니다.  
  
> [!IMPORTANT]
>  업그레이드 하기 전에 데이터베이스 파일을 백업 하는 것이 좋습니다.  
  
 데이터베이스를 업그레이드 하기 전에 다음과 같은 조건을 고려해 야 합니다.  
  
-   프로젝트에서 작업 하려는 경우 업그레이드 하지 않음 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] 및 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].  
  
-   응용 프로그램 LocalDB SQL Server 익스프레스 보다는 사용 환경에서 사용 하는 경우 업그레이드 하지 마십시오.  
  
-   Localdb를 받지 않는 때문에 응용 프로그램 원격 연결을 사용 하는 경우 업그레이드 하지 마십시오.  
  
-   인터넷 정보 서비스 \(IIS\) 응용 프로그램이 의존 하는 경우 업그레이드 하지 마십시오.  
  
-   샌드박스 환경에서 데이터베이스 응용 프로그램을 테스트할 수 있지만 데이터베이스를 관리 하지 않을 경우 업그레이드 하는 것이 좋습니다.  
  
### Localdb를 사용 하는 데이터베이스 파일을 업그레이드 하려면  
  
1.  **서버 탐색기**, 선택 된  **데이터베이스에 연결** 단추.  
  
2.  에  **연결 추가** 대화 상자에서 다음 정보를 지정 합니다.  
  
    -   **데이터 소스:** Microsoft SQL Server\(SqlClient\)  
  
    -   **서버 이름:** \\v11.0 \(LocalDB\)  
  
    -   **데이터베이스 파일 첨부:** *경로*여기서  *경로* 기본.mdf 파일의 실제 경로입니다.  
  
    -   **논리적 이름:** *이름*여기서  *이름* 파일에 사용할 이름입니다.  
  
3.  **확인** 단추를 선택합니다.  
  
4.  메시지가 나타나면 선택 된  **예** 파일을 업그레이드 하려면 단추.  
  
 없음 더 호환 및 LocalDB 데이터베이스 엔진에 연결 데이터베이스 업그레이드는 [!INCLUDE[ssKatmai_exp](../data-tools/includes/sskatmai_exp_md.md)].  
  
 LocalDB 연결의 바로 가기 메뉴를 열고 다음 선택 하 여 사용 하는 sql Express 연결을 수정할 수도 있습니다  **연결 수정**.  에  **연결 수정** 대화 상자에서 서버 이름 \(LocalDB\) \\v11.0으로 변경 합니다.  에  **고급 속성** 대화 상자에 있는지 확인  **사용자 인스턴스** 를 False로 설정 합니다.  
  
### SQL Server 익스프레스의 최신 버전으로 업그레이드 하려면  
  
1.  데이터베이스 연결에 대 한 바로 가기 메뉴에서 선택  **연결 수정**.  
  
2.  에  **연결 수정** 대화 상자에서 선택 된  **고급** 단추.  
  
3.  에  **고급 속성** 대화 상자에서 선택 된  **확인** 서버 이름을 변경 하지 않고 단추.  
  
 데이터베이스 파일의 현재 버전에 맞게 업그레이드 된 [!INCLUDE[sql_Denali_exp](../data-tools/includes/sql_denali_exp_md.md)].  
  
### 데이터베이스에서 사용할 수 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] 호환성을 유지 합니다.[!INCLUDE[ssKatmai_exp](../data-tools/includes/sskatmai_exp_md.md)]  
  
1.  [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], 프로젝트를 업그레이드 하지 않고 엽니다.  
  
    -   프로젝트를 실행 하려면 F5 키를 선택 합니다.  
  
    -   .Mdf 파일에는 데이터베이스를 편집 하려면 열  **솔루션 탐색기**, 노드를 확장 하 고  **서버 탐색기** 데이터베이스와 작동 하지 방금 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)].  
  
### SQL Server 익스프레스 기본 데이터베이스 엔진을 확인 하려면  
  
1.  메뉴 표시줄에서 선택  **도구**,  **옵션**.  
  
2.  에  **옵션** 대화 상자에서 확장은  **데이터 도구** 옵션을 선택한 다음 선택은  **데이터 연결** 노드.  
  
3.  에  **SQL Server 인스턴스 이름** 을 텍스트 상자에서 SQL Server 사용 하 여 Express의 인스턴스 이름을 지정 합니다.  지정한 인스턴스 이름이 지정 되지 않은 경우  `. \SQLEXPRESS`.  
  
4.  **확인** 단추를 선택합니다.  
  
 기본 데이터베이스 엔진 응용 프로그램에 대 한 SQL Server 익스프레스입니다.  
  
## 참고 항목  
 [로컬 데이터 개요](../data-tools/local-data-overview.md)   
 [연습: 로컬 데이터베이스 파일의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20a%20Local%20Database%20File%20\(Windows%20Forms\).md)