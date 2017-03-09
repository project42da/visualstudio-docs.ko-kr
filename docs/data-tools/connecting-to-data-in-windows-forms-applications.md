---
title: "Windows Forms 응용 프로그램에서 데이터에 연결 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "System.Data.SqlClient.SqlConnection"
  - "System.Data.Odbc.OdbcConnection"
  - "System.Data.OleDb.OleDbConnection"
  - "System.Data.OracleClient.OracleConnection"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "데이터베이스에 연결, ADO.NET 연결"
  - "연결 개체"
  - "연결 개체, 작업용 도구"
  - "연결 개체, 형식"
  - "연결 풀링, ADO.NET 연결"
  - "연결 문자열[Visual Studio], ADO.NET"
  - "연결, 연결 정보"
  - "연결, 디자인 타임"
  - "데이터[Visual Studio], 연결"
  - "데이터 어댑터, 연결"
  - "데이터베이스 연결[Visual Studio], ADO.NET"
  - "데이터베이스[Visual Studio], 연결"
  - "디자인 타임 연결"
  - "동적 속성, ADO.NET 연결"
  - "OleDbConnection 클래스, ADO.NET 연결 개체"
  - "SqlConnection 클래스, ADO.NET 연결 개체"
  - "TableAdapter, 연결"
  - "트랜잭션, ADO.NET"
ms.assetid: 184cbd0d-3b26-418d-a11c-f9f8f004fbff
caps.latest.revision: 31
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# Windows Forms 응용 프로그램에서 데이터에 연결
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 데이터베이스, 웹 서비스, 개체 등 서로 다른 여러 소스의 데이터에 응용 프로그램을 연결하는 도구를 제공합니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 데이터 디자인 도구를 사용하는 경우에는 폼이나 구성 요소에 대해 연결 개체를 명시적으로 만들지 않아도 되는 경우가 많습니다.  연결 개체는 대개 데이터 마법사 중 하나를 완료하거나 데이터 개체를 폼으로 끌어옴으로써 만들어집니다.  데이터베이스, 웹 서비스 또는 개체의 데이터에 응용 프로그램을 연결하려면 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)에서 **새 데이터 소스 추가**를 선택하여 [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)를 실행합니다.  
  
 다음 다이어그램에는 TableAdapter 쿼리를 실행하여 데이터에 연결해 데이터를 가져온 다음 Windows 응용 프로그램의 폼에 표시할 때의 표준 작업 흐름이 나와 있습니다.  
  
 ![클라이언트 응용 프로그램의 데이터 흐름](../data-tools/media/clientdatadiagram.gif "ClientDataDiagram")  
  
 데이터 디자인 도구를 사용하지 않고 연결 개체를 만드는 것이 편리한 경우도 있습니다.  프로그래밍 방식으로 연결을 만드는 방법에 대한 자세한 내용은 [데이터 소스에 연결](../Topic/Connecting%20to%20a%20Data%20Source%20in%20ADO.NET.md)을 참조하세요.  
  
> [!NOTE]
>  웹 응용 프로그램을 데이터에 연결하는 방법에 대한 자세한 내용은 [ASP.NET Data Access Content Map](http://msdn.microsoft.com/ko-kr/f9219396-a0fa-481f-894d-e3d9c67d64f2)를 참조하세요.  
  
## Windows Forms 응용 프로그램을 데이터에 연결하는 연습  
 다음 연습에서는 Windows Forms 응용 프로그램의 데이터에 연결하는 작업과 관련된 절차를 제공합니다.  
  
-   [연습: 데이터베이스의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20a%20Database%20\(Windows%20Forms\).md)  
  
-   [연습: 로컬 데이터베이스 파일의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20a%20Local%20Database%20File%20\(Windows%20Forms\).md)  
  
-   [연습: 웹 서비스의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20a%20Web%20Service%20\(Windows%20Forms\).md)  
  
-   [연습: 개체의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20Objects%20\(Windows%20Forms\).md)  
  
-   [연습: Access 데이터베이스의 데이터에 연결\(Windows Forms\)](../data-tools/connect-to-data-in-an-access-database-windows-forms.md)  
  
## 연결 만들기  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 **연결 추가\/수정** 대화 상자를 사용하여 연결을 구성합니다.  데이터 마법사 중 하나 또는 [서버 탐색기\/데이터베이스 탐색기](../Topic/Server%20Explorer.md)에서 연결을 만들거나 편집할 때 아니면 **속성** 창에서 연결 속성을 편집할 때 **연결 추가** 대화 상자가 표시됩니다.  
  
 다음 작업 중 하나를 수행할 때는 데이터 연결이 자동으로 구성됩니다.  
  
|동작|설명|  
|--------|--------|  
|[데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)를 실행합니다.|**데이터 소스 구성 마법사**에서 데이터베이스 경로를 선택하면 연결이 구성됩니다.  자세한 내용은 [방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)을 참조하세요.|  
|[TableAdapter 구성 마법사](../Topic/TableAdapter%20Configuration%20Wizard.md)를 실행합니다.|**TableAdapter 구성 마법사** 내에서 연결이 만들어집니다.  자세한 내용은 [방법: TableAdapter 만들기](../data-tools/create-and-configure-tableadapters.md)을 참조하세요.|  
|[TableAdapter 쿼리 구성 마법사](../data-tools/editing-tableadapters.md)를 실행합니다.|**TableAdapter 쿼리 구성 마법사** 내에서 연결이 만들어집니다.  자세한 내용은 [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)을 참조하세요.|  
|항목을 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)에서 폼이나 [Component Designer](../Topic/Component%20Designer.md)로 끌어 옵니다.|**데이터 소스** 창에서 **Windows Forms 디자이너** 또는 **구성 요소 디자이너**로 항목을 끌어오면 연결 개체가 만들어집니다.  자세한 내용은 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)을 참조하세요.|  
|[서버 탐색기\/데이터베이스 탐색기](../Topic/Server%20Explorer.md)에 새 데이터 연결을 추가합니다.|**서버 탐색기\/데이터베이스 탐색기**의 데이터 연결이 데이터 마법사 내의 사용 가능한 연결 목록에 표시됩니다.|  
  
## 연결 문자열  
 컴파일된 응용 프로그램 또는 응용 프로그램 구성 파일 내에 연결 문자열을 저장할 수 있습니다.  자세한 내용은 [방법: 연결 문자열 저장 및 편집](../Topic/How%20to:%20Save%20and%20Edit%20Connection%20Strings.md)을 참조하세요.  
  
## 연결 정보 및 보안  
 연결을 열 때는 중요한 리소스인 데이터베이스에 액세스하므로 연결 구성 및 사용과 관련된 보안 문제가 흔히 발생합니다.  
  
 시스템의 아키텍처에 따라 응용 프로그램 및 응용 프로그램의 데이터 소스 액세스를 보호하는 방법이 결정됩니다.  예를 들어 웹 기반 응용 프로그램에서는 사용자가 보통 IIS\(인터넷 정보 서비스\)에 익명으로 액세스하므로 보안 자격 증명을 제공하지 않습니다.  이 경우 응용 프로그램이 특정 사용자 정보 대신 자체 로그온 정보를 유지 관리하며 연결을 열고 데이터베이스에 액세스하는 데 해당 정보를 사용합니다.  
  
> [!IMPORTANT]
>  암호와 같은 연결 문자열 세부 정보를 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다.  데이터베이스 액세스를 제어할 경우에는 Windows 통합 보안을 사용하는 방법이 더 안전합니다.  자세한 내용은 [연결 정보 보호](../Topic/Protecting%20Connection%20Information.md)을 참조하세요.  
  
 인트라넷 또는 다층 계층 응용 프로그램에서는 Windows, IIS 및 SQL Server에서 제공하는 통합 보안 옵션을 활용할 수 있습니다.  이 모델에서는 데이터베이스 리소스에 액세스하는 데 로컬 네트워크용 사용자 인증 자격 증명도 사용할 수 있으며 연결 문자열에 명시적인 사용자 이름 또는 암호가 사용되지 않습니다.  일반적으로는 그룹을 통해 데이터베이스 서버 컴퓨터에서 사용 권한이 설정되므로 데이터베이스에 액세스할 수 있는 모든 사용자에 대해 개별 사용 권한을 설정하지 않아도 됩니다.  이 모델에서는 연결에 대해 로그온 정보 자체를 저장할 필요가 없으며 연결 문자열 정보를 보호하기 위해 수행해야 하는 추가 단계도 없습니다.  
  
 보안에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [ADO.NET 응용 프로그램 보안](../Topic/Securing%20ADO.NET%20Applications.md)  
  
-   [Windows Forms의 파일 및 데이터 액세스 추가 보안](../Topic/More%20Secure%20File%20and%20Data%20Access%20in%20Windows%20Forms.md)  
  
## 서버 탐색기\/데이터베이스 탐색기의 디자인 타임 연결  
 **서버 탐색기\/데이터베이스 탐색기**에서는 데이터 소스에 대한 디자인 타임 연결을 만들 수 있습니다.  그러면 사용 가능한 데이터 소스를 찾아보고, 데이터 소스에 포함된 테이블, 열 및 기타 요소에 대한 정보를 표시하고, 데이터베이스 요소를 편집\/작성할 수 있습니다.  
  
 응용 프로그램은 **서버 탐색기\/데이터베이스 탐색기**에서 사용 가능한 연결을 직접 사용하지는 않습니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 이러한 연결을 통해 디자인 타임에 데이터베이스를 사용합니다.  자세한 내용은 [Visual Database Tools](http://msdn.microsoft.com/ko-kr/6b145922-2f00-47db-befc-bf351b4809a1)을 참조하세요.  
  
 예를 들어 디자인 타임에 **서버 탐색기\/데이터베이스 탐색기**를 사용하여 데이터베이스에 대한 연결을 만들 수 있습니다.  나중에 폼을 디자인할 때 데이터베이스를 찾아보고 테이블에서 열을 선택한 다음 [데이터 집합 디자이너](../data-tools/creating-and-editing-typed-datasets.md)로 끌어 올 수 있습니다.  그러면 데이터 집합에 [TableAdapter](../data-tools/tableadapter-overview.md)가 만들어집니다.  또한 새로 만들어진 TableAdapter의 일부분인 새 연결 개체도 만들어집니다.  
  
 디자인 타임 연결에 대한 정보는 특정 프로젝트나 솔루션과는 독립적으로 로컬 컴퓨터에 저장됩니다.  따라서 응용 프로그램에서 작업하는 동안 디자인 타임 연결을 설정하고 나면 연결이 가리키는 서버를 사용할 수 있는 한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 작업할 때마다 **서버 탐색기\/데이터베이스 탐색기**에 해당 연결이 표시됩니다.  자세한 내용은 [How to: Connect to a Database from Server Explorer](http://msdn.microsoft.com/ko-kr/7c1c3067-0d77-471b-872b-639f9f50db74)을 참조하세요.  
  
 [!INCLUDE[SQLObjectExplorer](../data-tools/includes/sqlobjectexplorer_md.md)]  
  
## 참고 항목  
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [연습: 데이터베이스의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20a%20Database%20\(Windows%20Forms\).md)   
 [ASP.NET Data Access Content Map](http://msdn.microsoft.com/ko-kr/f9219396-a0fa-481f-894d-e3d9c67d64f2)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)