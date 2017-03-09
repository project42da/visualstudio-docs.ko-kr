---
title: "로컬 데이터 개요 | Microsoft Docs"
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
  - "Access, Visual Studio의 .mdb 파일"
  - "데이터[Visual Studio], 로컬"
  - "데이터 액세스[Visual Studio], 문제 해결"
  - "로컬 데이터"
  - "LocalDB"
  - "SQL Express"
  - "SQL Server Compact"
  - "SQL Server Express"
  - "SQL Server LocalDB"
  - "SQL Server, 로컬 데이터"
  - "SQLEXPRESS"
ms.assetid: d6afa5ac-2bb8-49f2-a50e-f71f611ed506
caps.latest.revision: 71
caps.handback.revision: 66
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 로컬 데이터 개요
로컬 데이터를 사용하면 응용 프로그램을 별도의 서버에 있는 데이터베이스 대신에 로컬 컴퓨터에 있는 데이터베이스 파일에 연결합니다.  예를 들어, 다음 로컬 데이터베이스 파일에 Visual Studio에서 개발 중인 응용 프로그램을 연결할 수 있습니다.  
  
-   SQL Server Express LocalDB 데이터베이스 파일\(.mdf\)  
  
-   SQL Server Express 데이터베이스 파일\(.mdf\)  
  
-   Microsoft Access 데이터베이스 파일\(.mdb\)  
  
 다음 표에서는 응용 프로그램을 로컬 데이터에 연결하는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
|항목|설명|  
|--------|--------|  
|[연습: Visual Studio에서 로컬 데이터베이스 파일 만들기](../data-tools/create-a-sql-database-by-using-a-designer.md)|데이터 기능을 테스트하고 응용 프로그램을 빌드하는 데 사용할 수 있는 로컬 데이터베이스 파일을 만들기 위한 단계별 지침을 제공합니다.|  
|[연습: 로컬 데이터베이스 파일의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20a%20Local%20Database%20File%20\(Windows%20Forms\).md)|간단한 Windows 응용 프로그램을 만드는 동안 SQL Server Express LocalDB 데이터베이스에 연결하기 위한 단계별 지침을 제공합니다.|  
|[연습: Access 데이터베이스의 데이터에 연결\(Windows Forms\)](../data-tools/connect-to-data-in-an-access-database-windows-forms.md)|Microsoft Access 데이터베이스에 연결하기 위한 단계별 지침을 제공합니다.|  
|[방법: Northwind 데이터베이스에 연결](../data-tools/how-to-connect-to-the-northwind-database.md)|[!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)], SQL Server Compact, SQL Server Express 및 Access에서 Northwind 샘플 데이터베이스에 연결하기 위한 지침을 제공합니다.|  
  
 데이터 소스를 만들고 로컬 데이터 파일에 액세스하도록 구성한 후 다른 소스의 데이터에 대한 작업에서 사용하는 것과 동일한 기술 및 개체를 사용하여 이 데이터에 대한 작업을 수행합니다.  자세한 내용은 [데이터 응용 프로그램 만들기](../data-tools/creating-data-applications.md)를 참조하십시오.  
  
## 응용 프로그램에 데이터베이스 통합  
 로컬 데이터에 연결하면 데이터베이스 파일에 연결할 수 있을 뿐만 아니라 응용 프로그램에도 통합할 수 있습니다.  예를 들어, **프로젝트** 메뉴를 열어 기존 .sdf, .mdf 또는 .mdb 파일을 찾아서 프로젝트에 추가할 수 있습니다.  
  
 로컬 데이터 파일을 추가하면 형식화된 데이터 집합과 응용 프로그램의 데이터베이스 파일을 가리키는 동적 연결 문자열이 만들어집니다.  프로젝트에 데이터베이스 파일을 추가할 때는 **데이터 소스 구성 마법사**를 사용하여 포함할 개체를 지정합니다.  
  
> [!NOTE]
>  .sdf, .mdf 또는 .mdb 파일을 파일 탐색기에서 **솔루션 탐색기**로 끌어서 연결을 자동으로 구성하고 **데이터 소스 구성 마법사**를 시작할 수 있습니다.  그런 다음 응용 프로그램에 사용할 개체를 지정할 수 있습니다.  
  
 **데이터 소스 구성 마법사**를 사용하여 로컬 데이터 파일에 대한 데이터 소스를 만드는 경우 해당 파일을 프로젝트에 포함할지 묻는 메시지가 나타납니다.  포함하지 않으면 실제 데이터 파일이 아니라 하드 코딩된 경로가 가리키는 연결 문자열만 응용 프로그램에 포함됩니다.  자세한 내용은 [방법: 프로젝트의 로컬 데이터 파일 관리](../data-tools/how-to-manage-local-data-files-in-your-project.md)을 참조하십시오.  
  
 마법사를 완료하면 데이터베이스 파일과 데이터 집합이 **솔루션 탐색기**\/**데이터베이스 탐색기**에 나타나고 지정한 데이터베이스 개체가 **데이터 소스** 창에 나타납니다.  **데이터 소스** 창에서 폼으로 항목을 끌어 놓아 내부 데이터에 바인딩된 컨트롤을 만들 수 있습니다.  **데이터 소스** 창을 열려면 **데이터** 메뉴를 연 후 **데이터 소스 표시**를 선택합니다.  자세한 내용은 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)를 참조하십시오.  
  
## 데이터베이스 파일 사용  
 Visual Studio에서 기존 데이터베이스 파일\(.mdf\)을 사용하기 전에 파일을 [!INCLUDE[sql_Denali_short](../data-tools/includes/sql_denali_short_md.md)] 데이터베이스 파일로 변환해야 합니다.  기존 데이터베이스 파일에 연결하면 업그레이드할지 여부를 묻는 메시지 상자가 나타납니다.  
  
> [!IMPORTANT]
>  데이터베이스 파일\(.mdf\)을 업그레이드하면 SQL Server의 이전 버전에서 해당 파일을 열 수 없습니다.  
  
 **SQL Server 인스턴스 이름**이 SQLEXPRESS로 설정되고 SQL Server 2008 Express가 설치된 경우 데이터베이스 파일\(.mdf\)을 변환하지 않아도 됩니다.  Visual Studio 2010이 설치되어 있으면 SQL Server 2008 Express도 설치되어 있습니다.  이 데이터베이스 파일의 인스턴스 이름을 변경하려면 Visual Studio에서 **연결 추가** 대화 상자를 열고 `.\SQLEXPRESS`를 서버 이름으로 지정한 다음 데이터베이스 또는 데이터베이스 파일 이름을 지정합니다.  
  
## SQL Server Express LocalDB 및 SQL Server Express  
 Visual Studio의 모든 프로젝트에 서비스 기반 데이터베이스 파일\(.mdf\)을 추가할 수 있습니다.  Visual Studio에서 디자이너를 사용하여 테이블 및 기타 데이터베이스 개체를 디자인하고 쿼리를 실행할 수 있습니다.  
  
 Visual Studio에서 서비스 기반 데이터베이스를 만들면 이전 버전의 Visual Studio가 SQL Server Express 엔진을 사용한 것과는 달리 SQL Server Express LocalDB 엔진을 사용하여 데이터베이스 파일\(.mdf\)에 액세스합니다.  
  
 SQL Server Express LocalDB는 SQL Server 데이터베이스와 대부분 동일한 방식으로 프로그래밍할 수 있는 SQL Server의 간단한 버전입니다.  SQL Server Express LocalDB는 사용자 모드로 실행되고 더 적은 필수 구성 요소를 사용하고 구성이 없어 더 신속하게 설치할 수 있습니다.  
  
> [!NOTE]
>  SQL Server Express LocalDB에 대한 자세한 내용은 Microsoft 웹 사이트의 [LocalDB 소개, 향상된 SQL Express](http://go.microsoft.com/fwlink/?LinkId=234375) 및 [LocalDB: 내 데이터베이스는 어디 있습니까?](http://go.microsoft.com/fwlink/?LinkId=234376)를 참조하십시오.  
  
 Visual Studio에서는 SQL Server Express LocalDB 대신 SQL Server Express를 기본값으로 사용할 수 있습니다.  메뉴 모음에서 **도구**, **옵션**을 선택합니다.  **데이터베이스 도구** 노드에서 **데이터 연결**을 선택합니다.  **SQL Server 인스턴스 이름** 텍스트 상자에 `SQLEXPRESS`를 입력합니다.  또는 SQL Server 인스턴스 이름\(예: `SQL2008`\)의 다른 값을 입력할 수 있습니다.  
  
 다음 표에서는 SQL Server Express LocalDB와 SQL Server Express 엔진 사이의 차이점에 대해 설명합니다.  
  
||SQL Server Express LocalDB|SQL Server Express|  
|-|--------------------------------|------------------------|  
|서비스 기반 데이터베이스를 만들 때의 데이터베이스 형식|[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] 및 [!INCLUDE[vs_dev12](../data-tools/includes/vs_dev12_md.md)]의 SQL Server Express LocalDB|Visual Studio 2010 이전 버전의 SQL Server Express|  
|도구\/옵션의 SQL Server 인스턴스 이름|\(LocalDB\)\\v11.0|SQLEXPRESS|  
|연결 문자열의 데이터 소스 값|\(LocalDB\)\\v11.0|.\\SQLEXPRESS|  
|연결 문자열의 AttachDbFilename 값|file path|file path|  
|사용자 인스턴스 필요\(연결 문자열의 "User Instance\=True"\)|아니요|예|  
|데이터베이스 파일의 확장명|.mdf|.mdf|  
  
## SQL Server Express LocalDB의 장점  
  
-   SQL Server Express LocalDB는 SQL Server Express LocalDB를 활성화하는 기능인 서비스 기반 SQL Server 버전과 호환됩니다.  SQL Server에서는 데이터베이스 또는 Transact\-SQL 코드를 업그레이드 단계 없이 SQL Server Express LocalDB에서 SQL Server 또는 SQL Azure로 이동시킬 수 있습니다.  따라서 SQL Server Express LocalDB를 사용하여 모든 SQL Server 버전을 대상으로 하는 응용 프로그램을 개발할 수 있습니다.  
  
-   SQL Server Express LocalDB는 SQL Server의 상위 버전에서 지원하는 것과 같은 쿼리 최적화 프로그램 및 쿼리 프로세서를 지원합니다.  
  
## 각 프로젝트에 두 개의 데이터베이스 복사본 포함  
 프로젝트를 빌드하면 데이터베이스 파일이 루트 프로젝트 폴더에서 출력\(**bin**\) 폴더로 복사됩니다.  이 동작은 파일의 **출력 디렉터리에 복사** 속성에 종속되며 해당 속성의 기본값은 사용 중인 데이터베이스 파일의 형식에 종속됩니다.  
  
 **솔루션 탐색기**에서 **bin** 폴더를 보려면 도구 모음에서 **모든 파일 표시** 단추를 선택합니다.  
  
> [!NOTE]
>  **출력 디렉터리에 복사** 속성은 웹 또는 C\+\+ 프로젝트에 적용되지 않습니다.  
  
 루트 프로젝트 폴더의 데이터베이스 파일은 **서버 탐색기**\/**데이터베이스 탐색기** 또는 다른 [Visual Database Tools](http://msdn.microsoft.com/ko-kr/6b145922-2f00-47db-befc-bf351b4809a1)를 사용하여 데이터베이스 스키마 또는 데이터를 편집할 때만 변경됩니다.  
  
 응용 프로그램을 개발하는 동안 데이터를 변경하면 **bin** 폴더의 데이터베이스가 변경되는 것입니다.  예를 들어, F5 키를 선택하여 응용 프로그램을 디버그하는 경우 해당 폴더의 데이터베이스에 연결됩니다.  
  
|**출력 디렉터리에 복사** 속성의 값|동작|  
|---------------------------|--------|  
|**새 버전이면 복사**\(.sdf 파일의 기본값\)|데이터베이스 파일은 프로젝트를 처음 빌드할 때 프로젝트 디렉터리에서 **bin** 디렉터리로 복사됩니다.  그런 후 프로젝트를 다시 빌드할 때마다 파일의 **수정한 날짜** 속성이 비교됩니다.  프로젝트 폴더의 파일이 새 버전인 경우 해당 파일이 **bin** 폴더에 복사되어 이전 파일을 대체합니다.  새 버전이 아니면 파일이 복사되지 않습니다. **Caution:**  .mdb 또는 .mdf 파일의 경우 이 값을 사용하지 않는 것이 좋습니다.  데이터가 변경되지 않아도 데이터베이스 파일은 변경될 수 있습니다.  단순히 연결을 열기만 해도\(예: **서버 탐색기**에서 **테이블** 노드 확장\) 파일이 새 버전으로 표시될 수 있습니다.|  
|**항상 복사**\(.mdf 및 .mdb 파일의 기본값\)|데이터베이스 파일은 응용 프로그램을 빌드할 때마다 프로젝트 디렉터리에서 **bin** 디렉터리로 복사됩니다.  다음에 응용 프로그램을 실행할 때 출력 폴더의 데이터 파일에 대해 변경된 모든 내용을 덮어씁니다.|  
|**복사 안 함**|시스템에서 **bin** 디렉터리의 파일을 덮어쓰지 않습니다.  응용 프로그램에서 출력 디렉터리에 있는 데이터베이스 파일을 가리키는 동적 연결 문자열을 만듭니다.  따라서 출력 디렉터리의 데이터가 프로젝트 디렉터리의 데이터와 일치하도록 하려면 파일을 출력 디렉터리로 직접 복사해야 합니다.|  
  
## 일반적인 로컬 데이터 문제  
 다음 표에서는 로컬 데이터 파일에 대한 작업을 수행하는 동안 발생하는 일반적인 문제에 대해 설명합니다.  
  
|문제|설명|  
|--------|--------|  
|응용 프로그램을 테스트하고 데이터를 수정해도 다음에 응용 프로그램을 실행하면 변경 내용이 사라집니다.|**출력 디렉터리에 복사** 속성의 값은 **새 버전이면 복사** 또는 **항상 복사**입니다.  프로젝트를 빌드할 때마다 출력 폴더에 있는 데이터베이스\(응용 프로그램을 테스트할 때 수정되는 데이터베이스\)를 덮어씁니다.  자세한 내용은 [방법: 프로젝트의 로컬 데이터 파일 관리](../data-tools/how-to-manage-local-data-files-in-your-project.md)을 참조하십시오.|  
|데이터 파일이 잠겨 있다는 내용의 메시지가 표시됩니다.|Access\(.mdb 파일\): 파일이 Access와 같은 다른 프로그램에서 열려 있지 않은지 확인합니다.<br /><br /> SQL Server Express\(.mdf 파일\): Visual Studio IDE 외부에서 데이터 파일을 복사, 이동 또는 이름을 바꾸는 경우 SQL Express에서 해당 데이터 파일을 잠급니다.|  
|두 명 이상의 사용자가 동시에 같은 데이터베이스에 액세스하려고 하면 액세스가 거부됩니다.|Visual Studio에서는 각 사용자에 대해 별도의 SQL Server 인스턴스를 만드는 SQL Server Express의 기능인 *사용자 인스턴스*가 사용됩니다.  한 사용자가 파일에 액세스하면 그 다음 사용자는 해당 파일에 연결할 수 없습니다.  이 문제는 예를 들어 사용자가 ASP.NET Development Server와 IIS\(인터넷 정보 서비스\)에서 웹 응용 프로그램을 동시에 실행하려고 할 때 발생할 수 있습니다. IIS는 일반적으로 다른 계정으로 실행해야 합니다.|  
  
## 참고 항목  
 [연습: 로컬 데이터베이스 파일의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20a%20Local%20Database%20File%20\(Windows%20Forms\).md)   
 [연습: Access 데이터베이스의 데이터에 연결\(Windows Forms\)](../data-tools/connect-to-data-in-an-access-database-windows-forms.md)