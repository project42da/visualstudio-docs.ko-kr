---
title: "연습: 작은 샘플 데이터베이스 만들기 | Microsoft Docs"
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
ms.assetid: 36f913c0-f5a7-4831-83a0-baba721ac95c
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: 작은 샘플 데이터베이스 만들기
연습을 통해서 Visual Studio를 사용하여 [연습: ADO.NET을 사용하여 간단한 데이터 응용 프로그램 만들기](../data-tools/create-a-simple-data-application-by-using-adonet.md) 샘플 코드를 포함하는 소형 데이터베이스를 만들 수 있습니다.  
  
 **항목 내용**  
  
-   [데이터베이스 스키마가 포함된 스크립트 만들기](../data-tools/create-a-sql-database-by-using-a-script.md#CreateScript)  
  
-   [데이터베이스 프로젝트 만들기 및 스키마 가져오기](../data-tools/create-a-sql-database-by-using-a-script.md#CreateProject)  
  
-   [데이터베이스 배포](../data-tools/create-a-sql-database-by-using-a-script.md#DeployDatabase)  
  
## 사전 요구 사항  
 이 연습을 완료하려면 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]이 설치되어 있어야 합니다.  또한 데이터베이스를 만들고 배포할 권한이 있는 데이터베이스 서버 또는 LocalDB 데이터베이스에 연결할 수 있어야 합니다.  
  
##  <a name="CreateScript"></a> 데이터베이스 스키마가 포함된 스크립트 만들기  
  
#### 스키마를 가져올 수 있는 원본 스크립트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 메뉴 모음에서 **파일**, **새로 만들기**, **파일**을 선택합니다.  
  
     **새 파일** 대화 상자가 나타납니다.  
  
2.  **범주** 목록에서 **일반**을 선택합니다.  
  
3.  **템플릿** 목록에서 **SQL 파일**을 선택한 다음 **열기** 단추를 선택합니다.  
  
     Transact\-SQL 편집기가 열립니다.  
  
4.  다음 Transact\-SQL 코드를 복사하여 Transact\-SQL 편집기에 붙여넣습니다.  
  
    ```  
    PRINT N'Creating Sales...';  
    GO  
    CREATE SCHEMA [Sales]  
        AUTHORIZATION [dbo];  
    GO  
    PRINT N'Creating Sales.Customer...';  
    GO  
    CREATE TABLE [Sales].[Customer] (  
        [CustomerID]   INT           IDENTITY (1, 1) NOT NULL,  
        [CustomerName] NVARCHAR (40) NOT NULL,  
        [YTDOrders]    INT           NOT NULL,  
        [YTDSales]     INT           NOT NULL  
    );  
    GO  
    PRINT N'Creating Sales.Orders...';  
    GO  
    CREATE TABLE [Sales].[Orders] (  
        [CustomerID] INT      NOT NULL,  
        [OrderID]    INT      IDENTITY (1, 1) NOT NULL,  
        [OrderDate]  DATETIME NOT NULL,  
        [FilledDate] DATETIME NULL,  
        [Status]     CHAR (1) NOT NULL,  
        [Amount]     INT      NOT NULL  
    );  
    GO  
    PRINT N'Creating Sales.Def_Customer_YTDOrders...';  
    GO  
    ALTER TABLE [Sales].[Customer]  
        ADD CONSTRAINT [Def_Customer_YTDOrders] DEFAULT 0 FOR [YTDOrders];  
    GO  
    PRINT N'Creating Sales.Def_Customer_YTDSales...';  
    GO  
    ALTER TABLE [Sales].[Customer]  
        ADD CONSTRAINT [Def_Customer_YTDSales] DEFAULT 0 FOR [YTDSales];  
    GO  
    PRINT N'Creating Sales.Def_Orders_OrderDate...';  
    GO  
    ALTER TABLE [Sales].[Orders]  
        ADD CONSTRAINT [Def_Orders_OrderDate] DEFAULT GetDate() FOR [OrderDate];  
    GO  
    PRINT N'Creating Sales.Def_Orders_Status...';  
    GO  
    ALTER TABLE [Sales].[Orders]  
        ADD CONSTRAINT [Def_Orders_Status] DEFAULT 'O' FOR [Status];  
    GO  
    PRINT N'Creating Sales.PK_Customer_CustID...';  
    GO  
    ALTER TABLE [Sales].[Customer]  
        ADD CONSTRAINT [PK_Customer_CustID] PRIMARY KEY CLUSTERED ([CustomerID] ASC) WITH (ALLOW_PAGE_LOCKS = ON, ALLOW_ROW_LOCKS = ON, PAD_INDEX = OFF, IGNORE_DUP_KEY = OFF, STATISTICS_NORECOMPUTE = OFF);  
    GO  
    PRINT N'Creating Sales.PK_Orders_OrderID...';  
    GO  
    ALTER TABLE [Sales].[Orders]  
        ADD CONSTRAINT [PK_Orders_OrderID] PRIMARY KEY CLUSTERED ([OrderID] ASC) WITH (ALLOW_PAGE_LOCKS = ON, ALLOW_ROW_LOCKS = ON, PAD_INDEX = OFF, IGNORE_DUP_KEY = OFF, STATISTICS_NORECOMPUTE = OFF);  
    GO  
    PRINT N'Creating Sales.FK_Orders_Customer_CustID...';  
    GO  
    ALTER TABLE [Sales].[Orders]  
        ADD CONSTRAINT [FK_Orders_Customer_CustID] FOREIGN KEY ([CustomerID]) REFERENCES [Sales].[Customer] ([CustomerID]) ON DELETE NO ACTION ON UPDATE NO ACTION;  
    GO  
    PRINT N'Creating Sales.CK_Orders_FilledDate...';  
    GO  
    ALTER TABLE [Sales].[Orders]  
        ADD CONSTRAINT [CK_Orders_FilledDate] CHECK ((FilledDate >= OrderDate) AND (FilledDate < '01/01/2020'));  
    GO  
    PRINT N'Creating Sales.CK_Orders_OrderDate...';  
    GO  
    ALTER TABLE [Sales].[Orders]  
        ADD CONSTRAINT [CK_Orders_OrderDate] CHECK ((OrderDate > '01/01/2005') and (OrderDate < '01/01/2020'));  
    GO  
    PRINT N'Creating Sales.uspCancelOrder...';  
    GO  
    CREATE PROCEDURE [Sales].[uspCancelOrder]  
    @OrderID INT  
    AS  
    BEGIN  
    DECLARE @Delta INT, @CustomerID INT  
    BEGIN TRANSACTION  
        SELECT @Delta = [Amount], @CustomerID = [CustomerID]  
         FROM [Sales].[Orders] WHERE [OrderID] = @OrderID;  
  
    UPDATE [Sales].[Orders]  
       SET [Status] = 'X'  
    WHERE [OrderID] = @OrderID;  
  
    UPDATE [Sales].[Customer]  
       SET  
       YTDOrders = YTDOrders - @Delta  
        WHERE [CustomerID] = @CustomerID  
    COMMIT TRANSACTION  
    END  
    GO  
    PRINT N'Creating Sales.uspFillOrder...';  
    GO  
    CREATE PROCEDURE [Sales].[uspFillOrder]  
    @OrderID INT, @FilledDate DATETIME  
    AS  
    BEGIN  
    DECLARE @Delta INT, @CustomerID INT  
    BEGIN TRANSACTION  
        SELECT @Delta = [Amount], @CustomerID = [CustomerID]  
         FROM [Sales].[Orders] WHERE [OrderID] = @OrderID;  
  
    UPDATE [Sales].[Orders]  
       SET [Status] = 'F',  
           [FilledDate] = @FilledDate  
    WHERE [OrderID] = @OrderID;  
  
    UPDATE [Sales].[Customer]  
       SET  
       YTDSales = YTDSales + @Delta  
        WHERE [CustomerID] = @CustomerID  
    COMMIT TRANSACTION  
    END  
    GO  
    PRINT N'Creating Sales.uspNewCustomer...';  
    GO  
    CREATE PROCEDURE [Sales].[uspNewCustomer]  
    @CustomerName NVARCHAR (40),  
    @CustomerID INT OUTPUT  
    AS  
    BEGIN  
    INSERT INTO [Sales].[Customer] (CustomerName) VALUES (@CustomerName);  
    SET @CustomerID = SCOPE_IDENTITY();  
    RETURN @@ERROR  
    END  
    GO  
    PRINT N'Creating Sales.uspPlaceNewOrder...';  
    GO  
    CREATE PROCEDURE [Sales].[uspPlaceNewOrder]  
    @CustomerID INT, @Amount INT, @OrderDate DATETIME, @Status CHAR (1)='O'  
    AS  
    BEGIN  
    DECLARE @RC INT  
    BEGIN TRANSACTION  
    INSERT INTO [Sales].[Orders] (CustomerID, OrderDate, FilledDate, Status, Amount)   
         VALUES (@CustomerID, @OrderDate, NULL, @Status, @Amount)  
    SELECT @RC = SCOPE_IDENTITY();  
    UPDATE [Sales].[Customer]  
       SET  
       YTDOrders = YTDOrders + @Amount  
        WHERE [CustomerID] = @CustomerID  
    COMMIT TRANSACTION  
    RETURN @RC  
    END  
    GO  
    CREATE PROCEDURE [Sales].[uspShowOrderDetails]  
    @CustomerID INT=0  
    AS  
    BEGIN  
    SELECT [C].[CustomerName], CONVERT(date, [O].[OrderDate]), CONVERT(date, [O].[FilledDate]), [O].[Status], [O].[Amount]  
      FROM [Sales].[Customer] AS C  
      INNER JOIN [Sales].[Orders] AS O  
         ON [O].[CustomerID] = [C].[CustomerID]  
      WHERE [C].[CustomerID] = @CustomerID  
    END  
    GO  
    ```  
  
5.  메뉴 모음에서 **파일**, **다른 이름으로 SqlQuery\_1.sql 저장**을 선택합니다.  
  
     **다른 이름으로 파일 저장** 대화 상자가 나타납니다.  
  
6.  **파일 이름** 상자에 `SampleImportScript.sql`을 입력하고 파일을 저장할 위치를 기록한 다음 **저장** 단추를 선택합니다.  
  
7.  메뉴 모음에서 **파일**, **솔루션 닫기**를 선택합니다.  
  
     다음에는 데이터베이스 프로젝트를 만들고 앞에서 만든 스크립트에서 스키마를 가져옵니다.  
  
##  <a name="CreateProject"></a> 데이터베이스 프로젝트 만들기 및 스키마 가져오기  
  
#### 데이터베이스 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  **설치됨**에서 **템플릿** 노드를 확장하고 **다른 언어** 노드를 확장하고, **SQL Server** 범주를 선택한 후 **SQL Server 데이터베이스 프로젝트** 템플릿을 선택합니다.  
  
    > [!NOTE]
    >  **다른 언어** 노드는 설치된 Visual Studio 중 일부에 나타나지 않습니다.  
  
3.  **이름** 상자에 `Small Database`를 입력합니다.  
  
4.  **솔루션용 디렉터리 만들기** 확인란이 아직 선택되어 있지 않은 경우 선택합니다.  
  
5.  **소스 제어에 추가** 확인란이 아직 선택 취소되어 있지 않은 경우 선택 취소하고 **확인** 단추를 선택합니다.  
  
     데이터베이스 프로젝트가 만들어지고 **솔루션 탐색기**에 나타납니다.  
  
     다음에는 스크립트에서 데이터베이스 스키마를 가져옵니다.  
  
#### 스크립트에서 데이터베이스 스키마를 가져오려면  
  
1.  메뉴 모음에서 **프로젝트**, **가져오기**, **스크립트**를 선택합니다.  
  
2.  시작합니다. 페이지에서 텍스트를 검토한 후 **다음** 단추를 선택합니다.  
  
3.  **단일 파일** 옵션 단추를 누른 다음 **찾아보기** 단추를 선택합니다.  
  
     **SQL 스크립트 가져오기** 대화 상자가 나타납니다.  
  
4.  SampleImportScript.sql을 저장한 폴더를 열고 해당 파일을 선택한 다음 **열기** 단추를 선택합니다.  
  
5.  **마침** 단추를 선택하여 **SQL 스크립트 가져오기** 대화 상자를 닫습니다.  
  
     스크립트를 가져온 다음 해당 스크립트가 정의하는 개체가 데이터베이스 프로젝트에 추가됩니다.  
  
6.  요약을 검토한 후 **마침** 단추를 선택하여 **SQL 스크립트 파일 가져오기** 대화 상자를 닫습니다.  
  
7.  **솔루션 탐색기**에서 프로젝트의 Sales, Scripts 및 Security 폴더를 확장한 후 .sql 파일이 포함되어 있는지 확인합니다.  
  
8.  **SQL Server 개체 탐색기**의 **프로젝트** 노드에 데이터베이스가 나타나는지 확인하십시오.  
  
     이 시점에는 데이터베이스에 테이블, 저장 프로시저와 같은 시스템 개체만 포함되어 있습니다.  데이터베이스를 배포한 후에는 스크립트를 정의하는 사용자 테이블과 저장 프로시저가 포함됩니다.  
  
##  <a name="DeployDatabase"></a> 데이터베이스 배포  
 F5 키를 선택하면 기본적으로 LocalDB 데이터베이스에 데이터베이스를 배포 또는 게시합니다.  프로젝트의 속성 페이지를 열고, **디버그** 탭을 선택한 후 연결 문자열을 변경하여 데이터베이스를 다른 위치에 배포할 수 있습니다.