---
title: "연습: 데이터 집합 디자이너를 사용 하 여 데이터 집합을 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 09/11/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- datasets [Visual Basic], walkthroughs
- XML schemas, creating datasets
- data [Visual Studio], Dataset Designer
- Dataset Designer, walkthroughs
- datasets [Visual Basic], creating
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: f826f7d33a8d35719afacb053995629433b27642
ms.sourcegitcommit: e951faab601f5c05ad6606d8fd0cd2059fc4cc25
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2017
---
# <a name="walkthrough-creating-a-dataset-with-the-dataset-designer"></a>연습: 데이터 집합 디자이너를 사용하여 데이터 집합 만들기

이 연습에서는 만듭니다 사용 하 여 데이터 집합의 **데이터 집합 디자이너**합니다. 새 프로젝트를 만들고 새 추가 과정을 단계별로 걸리는 **데이터 집합** 항목 것입니다. 마법사를 사용 하지 않고 데이터베이스의 테이블에 따라 테이블을 만드는 방법에 설명 합니다.  

이 연습에서 설명하는 작업은 다음과 같습니다.  

-   새 **Windows Forms 응용 프로그램** 프로젝트.  

-   빈 추가 **DataSet** 항목을 프로젝트입니다.  

-   만들고 있는 데이터 집합을 작성 하 여 응용 프로그램에서 데이터 원본 구성의 **데이터 집합 디자이너**합니다.  
 
-   Northwind 데이터베이스에 연결을 만들면 **서버 탐색기**합니다.  

-   데이터베이스의 테이블을 기반으로 데이터 집합에서 TableAdapters를 사용 하 여 테이블 만들기  

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="prerequisites"></a>필수 구성 요소  
이 연습에서는 Northwind 샘플 데이터베이스 및 SQL Server Express LocalDB를 사용 합니다.  
  
1.  SQL Server Express LocalDB가 없는 경우 설치에서 [SQL Server 버전의 다운로드 페이지](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx), 또는 **Visual Studio 설치 관리자**합니다. Visual Studio 설치 관리자 SQL Server Express LocalDB의 일부로 설치할 수 있습니다는 **데이터 저장 및 처리** 작업 또는 개별 구성 요소입니다.  
  
2.  다음 단계를 수행 하 여 Northwind 샘플 데이터베이스를 설치 합니다.  

    1. Visual Studio에서 열고는 **SQL Server 개체 탐색기** 창. (SQL Server 개체 탐색기의 일부로 설치 되는 **데이터 저장 및 처리** Visual Studio 설치 관리자에서 작업 합니다.) 확장 된 **SQL Server** 노드. LocalDB 인스턴스를 마우스 오른쪽 단추로 클릭 하 고 선택 **새 쿼리 중...** .  

       쿼리 편집기 창이 열립니다.  

    2. 복사는 [Northwind Transact SQL 스크립트](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) 를 클립보드에 복사 합니다. 이 T-SQL 스크립트를 처음부터 Northwind 데이터베이스를 만들고 데이터로 채웁니다.  

    3. 쿼리 편집기에 T-SQL 스크립트를 붙여 넣습니다.를 선택한 후는 **Execute** 단추입니다.  

       짧은 시간 후 쿼리 실행이 완료 되 하 고 Northwind 데이터베이스 생성 됩니다.  
  
## <a name="creating-a-new-windows-forms-application-project"></a>새 Windows Forms 응용 프로그램 프로젝트 만들기  
  
#### <a name="to-create-a-new-windows-forms-application-project"></a>새 Windows Forms 응용 프로그램 프로젝트를 만들려면  
  
1. Visual Studio에서에 **파일** 메뉴 선택 **새로**, **프로젝트...** .  
  
2. 확장 **Visual C#** 또는 **Visual Basic** 왼쪽 창에서 선택 **클래식 Windows 데스크톱**합니다.  

3. 가운데 창에서 선택 된 **Windows Forms 앱** 프로젝트 형식을 합니다.  

4. 프로젝트 이름을 **DatasetDesignerWalkthrough**를 선택한 후 **확인**합니다.  
  
     프로젝트를 추가 하는 visual Studio **솔루션 탐색기** 디자이너에서 새 양식을 표시 합니다.  
  
## <a name="adding-a-new-dataset-to-the-application"></a>응용 프로그램에 새 데이터 집합 추가  
  
#### <a name="to-add-a-new-dataset-item-to-the-project"></a>프로젝트에 새 데이터 집합 항목을 추가 하려면  
  
1.  에 **프로젝트** 메뉴 선택 **새 항목 추가...** .  
  
     **새 항목 추가** 대화 상자가 나타납니다.  
  
2.  왼쪽 창에서 선택 **데이터**을 선택한 후 **DataSet** 가운데 창에서.  
  
3.  데이터 집합 이름을 **NorthwindDataset**를 선택한 후 **추가**합니다.  
  
     라는 파일을 추가 하는 visual Studio **NorthwindDataset.xsd** 프로젝트에서 엽니다는 **데이터 집합 디자이너**합니다.  
  
## <a name="creating-a-data-connection-in-server-explorer"></a>서버 탐색기에서 데이터 연결 만들기  
  
#### <a name="to-create-a-connection-to-the-northwind-database"></a>Northwind 데이터베이스에 연결을 만들려면  
  
1.  에 **보기** 메뉴를 클릭 하 여 **서버 탐색기**합니다.  
  
2.  **서버 탐색기**, 클릭는 **연결할 데이터베이스** 단추입니다.  
  
3.  Northwind 샘플 데이터베이스에 연결을 만듭니다.  
  
## <a name="creating-the-tables-in-the-dataset"></a>데이터 집합에 테이블 만들기  
이 섹션에서는 데이터 집합에 테이블을 추가 하는 방법을 설명 합니다.  
  
#### <a name="to-create-the-customers-table"></a>Customers 테이블을 만들려면  
  
1.  데이터 연결에서 만든 확장 **서버 탐색기**를 차례로 확장 하 고는 **테이블** 노드.  
  
2.  끌어서는 **고객** 에서 테이블 **서버 탐색기** 에 **데이터 집합 디자이너**합니다.  
  
     A **고객** 데이터 테이블 및 **CustomersTableAdapter** 데이터 집합에 추가 됩니다.  
  
#### <a name="to-create-the-orders-table"></a>Orders 테이블을 만들려면  
  
-   끌어서는 **Orders** 에서 테이블 **서버 탐색기** 에 **데이터 집합 디자이너**합니다.  
  
     **Orders** 데이터 테이블 **OrdersTableAdapter**, 및 간에 데이터 관계는 **고객** 및 **Orders** 테이블에 추가 되는 데이터 집합입니다.  
  
#### <a name="to-create-the-orderdetails-table"></a>OrderDetails 테이블을 만들려면  
  
-   끌어서는 **Order Details** 에서 테이블 **서버 탐색기** 에 **데이터 집합 디자이너**합니다.  
  
     **Order Details** 데이터 테이블 **OrderDetailsTableAdapter**, 및 간에 데이터 관계는 **Orders** 및 **OrderDetails** 테이블 데이터 집합에 추가 됩니다.  
  
## <a name="next-steps"></a>다음 단계  
  
### <a name="to-add-functionality-to-your-application"></a>응용 프로그램에 기능을 추가하려면  
  
-   데이터 집합을 저장 합니다.  
  
-   항목을 선택는 **데이터 소스** 창에서 폼으로 끕니다. 자세한 내용은 참조 [Visual Studio에서 데이터를 바인딩할 Windows Forms 컨트롤](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)합니다.  
  
-   Tableadapter에 더 많은 쿼리를 추가 합니다. 
  
-   유효성 검사 논리를 추가 <xref:System.Data.DataTable.ColumnChanging> 또는 <xref:System.Data.DataTable.RowChanging> 데이터 집합에 있는 데이터 테이블의 이벤트입니다. 자세한 내용은 참조 [데이터 집합의 데이터 유효성 검사](../data-tools/validate-data-in-datasets.md)합니다.  
  
## <a name="see-also"></a>참고 항목
[Visual Studio에서 데이터 집합 만들기 및 구성](../data-tools/create-and-configure-datasets-in-visual-studio.md)  
[Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
[Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
[데이터 유효성 검사](../data-tools/validate-data-in-datasets.md)   
[데이터 저장](../data-tools/saving-data.md)