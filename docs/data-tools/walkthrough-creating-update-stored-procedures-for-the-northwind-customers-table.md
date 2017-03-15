---
title: "연습: Northwind Customers 테이블의 업데이트 저장 프로시저 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "Northwind 샘플 데이터베이스"
  - "O/R 디자이너, 저장 프로시저"
  - "저장 프로시저[Visual Studio]"
ms.assetid: 6fd9e7e0-6862-44d3-9710-acc5a72d4ffd
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 연습: Northwind Customers 테이블의 업데이트 저장 프로시저 만들기
[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 설명서에 포함된 일부 도움말 항목의 경우 Customers 테이블의 데이터 업데이트\(삽입\/업데이트\/삭제\)를 수행하려면 Northwind 샘플 데이터베이스의 추가 저장 프로시저가 필요합니다.  
  
 이 연습에서는 [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)]용 Northwind 샘플 데이터베이스에서 이러한 추가 저장 프로시저를 만드는 지침을 제공합니다.  
  
 이 항목 뒷부분의 다음 단계 섹션에서는 이러한 추가 저장 프로시저를 사용하는 방법을 보여주는 항목에 대한 링크를 제공합니다.  
  
 이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.  
  
-   Northwind 샘플 데이터베이스에 대한 데이터 연결 만들기  
  
-   저장 프로시저 만들기  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스의 SQL Server 버전 액세스 권한.  자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)을 참조하십시오.  
  
## Northwind 데이터베이스에 연결  
 이 연습에서는 Northwind 데이터베이스의 SQL Server 버전에 연결해야 합니다.  다음 절차에서는 데이터 연결을 만드는 지침을 제공합니다.  
  
> [!NOTE]
>  Northwind 데이터베이스에 대한 데이터 연결이 이미 있는 경우 다음 섹션인 저장 프로시저 만들기로 이동하면 됩니다.  
  
#### Northwind SQL Server 데이터베이스에 대한 데이터 연결을 만들려면  
  
1.  **보기** 메뉴에서 **서버 탐색기**\/**데이터베이스 탐색기**를 클릭합니다.  
  
2.  **데이터 연결**을 마우스 오른쪽 단추로 클릭하고 **연결 추가**를 클릭합니다.  
  
3.  **데이터 소스 선택** 대화 상자에서 **Microsoft SQL Server**를 클릭한 다음 **확인**을 클릭합니다.  
  
     **연결 추가** 대화 상자가 열리는 경우 **데이터 소스**가 **Microsoft SQL Server\(SqlClient\)**가 아니면 **변경**을 클릭하여 **데이터 소스 선택\/변경** 대화 상자를 열고 **Microsoft SQL Server**를 클릭한 후에 **확인**을 클릭합니다.  
  
4.  드롭다운 목록에서 **서버 이름**을 클릭하거나 Northwind 데이터베이스가 있는 서버의 이름을 입력합니다.  
  
5.  데이터베이스 또는 응용 프로그램의 요구 사항에 따라 **Windows 인증 사용**을 클릭하거나 특정 사용자 이름 및 암호를 사용하여 SQL Server를 실행하는 컴퓨터에 로그온합니다\(**SQL Server 인증**\).  
  
6.  **데이터베이스 이름 선택 또는 입력** 목록에서 Northwind 데이터베이스를 클릭합니다.  
  
7.  **확인**을 클릭합니다.  
  
     데이터 연결이 **서버 탐색기**\/**데이터베이스 탐색기**에 추가됩니다.  
  
## 저장 프로시저 만들기  
 Northwind 데이터베이스에 대해 제공된 SQL 스크립트를 실행하여 저장 프로시저를 만듭니다. 이때 **서버 탐색기**\/**데이터베이스 탐색기**에서 제공되는 [Visual Database Tools](http://msdn.microsoft.com/ko-kr/6b145922-2f00-47db-befc-bf351b4809a1)를 사용합니다.  
  
#### SQL 스크립트를 사용하여 저장 프로시저를 만들려면  
  
1.  **서버 탐색기**\/**데이터베이스 탐색기**에서 Northwind 데이터베이스를 확장합니다.  
  
2.  **저장 프로시저** 노드를 마우스 오른쪽 단추로 클릭하고 **새 저장 프로시저 추가**를 클릭합니다.  
  
3.  다음 코드를 코드 편집기에 붙여 넣습니다. 이때 `CREATE PROCEDURE` 템플릿을 다음과 같이 바꿉니다.  
  
    ```  
    IF EXISTS (SELECT * FROM sysobjects WHERE name = 'SelectCustomers' AND user_name(uid) = 'dbo')  
        DROP PROCEDURE dbo.[SelectCustomers]  
    GO  
  
    CREATE PROCEDURE dbo.[SelectCustomers]  
    AS  
        SET NOCOUNT ON;  
    SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax FROM dbo.Customers  
    GO  
  
    IF EXISTS (SELECT * FROM sysobjects WHERE name = 'InsertCustomers' AND user_name(uid) = 'dbo')  
        DROP PROCEDURE dbo.InsertCustomers  
    GO  
  
    CREATE PROCEDURE dbo.InsertCustomers  
    (  
        @CustomerID nchar(5),  
        @CompanyName nvarchar(40),  
        @ContactName nvarchar(30),  
        @ContactTitle nvarchar(30),  
        @Address nvarchar(60),  
        @City nvarchar(15),  
        @Region nvarchar(15),  
        @PostalCode nvarchar(10),  
        @Country nvarchar(15),  
        @Phone nvarchar(24),  
        @Fax nvarchar(24)  
    )  
    AS  
        SET NOCOUNT OFF;  
    INSERT INTO [dbo].[Customers] ([CustomerID], [CompanyName], [ContactName], [ContactTitle], [Address], [City], [Region], [PostalCode], [Country], [Phone], [Fax]) VALUES (@CustomerID, @CompanyName, @ContactName, @ContactTitle, @Address, @City, @Region, @PostalCode, @Country, @Phone, @Fax);  
  
    SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax FROM Customers WHERE (CustomerID = @CustomerID)  
    GO  
  
    IF EXISTS (SELECT * FROM sysobjects WHERE name = 'UpdateCustomers' AND user_name(uid) = 'dbo')  
        DROP PROCEDURE dbo.UpdateCustomers  
    GO  
  
    CREATE PROCEDURE dbo.UpdateCustomers  
    (  
        @CustomerID nchar(5),  
        @CompanyName nvarchar(40),  
        @ContactName nvarchar(30),  
        @ContactTitle nvarchar(30),  
        @Address nvarchar(60),  
        @City nvarchar(15),  
        @Region nvarchar(15),  
        @PostalCode nvarchar(10),  
        @Country nvarchar(15),  
        @Phone nvarchar(24),  
        @Fax nvarchar(24),  
        @Original_CustomerID nchar(5)  
    )  
    AS  
        SET NOCOUNT OFF;  
    UPDATE [dbo].[Customers] SET [CustomerID] = @CustomerID, [CompanyName] = @CompanyName, [ContactName] = @ContactName, [ContactTitle] = @ContactTitle, [Address] = @Address, [City] = @City, [Region] = @Region, [PostalCode] = @PostalCode, [Country] = @Country, [Phone] = @Phone, [Fax] = @Fax WHERE (([CustomerID] = @Original_CustomerID));  
  
    SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax FROM Customers WHERE (CustomerID = @CustomerID)  
    GO  
  
    IF EXISTS (SELECT * FROM sysobjects WHERE name = 'DeleteCustomers' AND user_name(uid) = 'dbo')  
        DROP PROCEDURE dbo.DeleteCustomers  
    GO  
  
    CREATE PROCEDURE dbo.DeleteCustomers  
    (  
        @Original_CustomerID nchar(5)  
    )  
    AS  
        SET NOCOUNT OFF;  
    DELETE FROM [dbo].[Customers] WHERE (([CustomerID] = @Original_CustomerID))  
    GO  
    ```  
  
4.  코드 편집기에서 모든 텍스트를 선택하고 선택한 텍스트를 마우스 오른쪽 단추로 클릭한 후에 **선택 항목 실행**을 클릭합니다.  
  
     Northwind 데이터베이스에 대해 SelectCustomers, InsertCustomers, UpdateCustomers 및 DeleteCustomers 저장 프로시저가 만들어집니다.  
  
## 다음 단계  
 저장 프로시저를 만든 후에는 해당 저장 프로시저를 사용하는 방법을 보여주는 다음 연습을 진행해 보세요.  
  
 [방법: 저장 프로시저를 할당하여 업데이트, 삽입 및 삭제 수행\(O\/R 디자이너\)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)  
  
 [연습: LINQ to SQL 클래스 만들기\(O\/R 디자이너\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)  
  
 [연습: 엔터티 클래스의 삽입, 업데이트 및 삭제 동작 사용자 지정](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)  
  
## 참고 항목  
 [O\/R 디자이너\(개체 관계형 디자이너\)](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)