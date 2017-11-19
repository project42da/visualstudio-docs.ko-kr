---
title: "TableAdapter DBDirect 메서드 데이터 저장 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- TableAdapters, walkthroughs
- data [Visual Studio], saving
- saving data, walkthroughs
- data [Visual Studio], TableAdapter
ms.assetid: 74a6773b-37e1-4d96-a39c-63ee0abf49b1
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 3ed52a167b607236b8493e4c8c1736ee597162b9
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="save-data-with-the-tableadapter-dbdirect-methods"></a>TableAdapter DBDirect 메서드 데이터 저장
이 연습에서는 TableAdapter의 DBDirect 메서드를 사용 하 여 데이터베이스에 대해 직접 SQL 문을 실행 하는 자세한 지침을 제공 합니다. TableAdapter의 DBDirect 메서드 제어 데이터베이스 업데이트에 대 한 상세 수준을 제공합니다. 사용 하 여 개별을 호출 하 여 특정 SQL 문과 저장된 프로시저를 실행할 수 있습니다 `Insert`, `Update`, 및 `Delete` 응용 프로그램에서 필요에 따라 메서드 (오버 로드 된 달리 `Update` 업데이트를 수행 하는 메서드 INSERT 및 DELETE 문을 모두 한 번의 호출에에서).  
  
 이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.  
  
-   새 **Windows Forms 응용 프로그램**합니다.  
  
-   만들기 및 구성 된 데이터 집합의 [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)합니다.  
  
-   항목을 끌어오는 경우 폼에 만들어질 컨트롤을 선택 된 **데이터 소스** 창. 자세한 내용은 참조 [데이터 소스 창에서 끌어 올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)합니다.  
  
-   항목을 끌어 데이터 바인딩된 폼 만들기는 **데이터 소스** 창에서 폼으로 합니다.  
  
-   직접 데이터베이스에 액세스 하 고 삽입, 업데이트 및 삭제를 수행 하는 메서드를 추가...  
  
## <a name="prerequisites"></a>필수 구성 요소  
이 연습에서는 Northwind 샘플 데이터베이스 및 SQL Server Express LocalDB를 사용 합니다.  
  
1.  SQL Server Express LocalDB가 없는 경우 설치에서 [SQL Server 버전의 다운로드 페이지](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx), 또는 **Visual Studio 설치 관리자**합니다. Visual Studio 설치 관리자 SQL Server Express LocalDB의 일부로 설치할 수 있습니다는 **데이터 저장 및 처리** 작업 또는 개별 구성 요소입니다.  
  
2.  다음 단계를 수행 하 여 Northwind 샘플 데이터베이스를 설치 합니다.  

    1. Visual Studio에서 열고는 **SQL Server 개체 탐색기** 창. (SQL Server 개체 탐색기의 일부로 설치 되는 **데이터 저장 및 처리** Visual Studio 설치 관리자에서 작업 합니다.) 확장 된 **SQL Server** 노드. LocalDB 인스턴스를 마우스 오른쪽 단추로 클릭 하 고 선택 **새 쿼리 중...** .  

       쿼리 편집기 창이 열립니다.  

    2. 복사는 [Northwind Transact SQL 스크립트](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) 를 클립보드에 복사 합니다. 이 T-SQL 스크립트를 처음부터 Northwind 데이터베이스를 만들고 데이터로 채웁니다.  

    3. 쿼리 편집기에 T-SQL 스크립트를 붙여 넣습니다.를 선택한 후는 **Execute** 단추입니다.  

       짧은 시간 후 쿼리 실행이 완료 되 하 고 Northwind 데이터베이스 생성 됩니다.  
  
## <a name="create-a-windows-forms-application"></a>Windows Forms 응용 프로그램 만들기  
 첫 번째 단계를 만드는 것을 **Windows Forms 응용 프로그램**합니다.  
  
#### <a name="to-create-the-new-windows-project"></a>새 Windows 프로젝트를 만들려면  
  
1. Visual Studio에서에 **파일** 메뉴 선택 **새로**, **프로젝트...** .  
  
2. 확장 **Visual C#** 또는 **Visual Basic** 왼쪽 창에서 선택 **클래식 Windows 데스크톱**합니다.  

3. 가운데 창에서 선택 된 **Windows Forms 앱** 프로젝트 형식을 합니다.  

4. 프로젝트 이름을 **TableAdapterDbDirectMethodsWalkthrough**를 선택한 후 **확인**합니다. 
  
     **TableAdapterDbDirectMethodsWalkthrough** 프로젝트를 만들고 추가 **솔루션 탐색기**합니다.  
  
## <a name="create-a-data-source-from-your-database"></a>데이터베이스에서 데이터 원본 만들기  
 이 단계는 **데이터 소스 구성 마법사** 기반으로 데이터 원본을 만들려면는 `Region` Northwind 샘플 데이터베이스의 테이블입니다. 연결을 만들려면 Northwind 샘플 데이터베이스에 액세스해야 합니다. Northwind 샘플 데이터베이스 설정에 대 한 정보를 참조 하십시오. [하는 방법: 샘플 데이터베이스 설치](../data-tools/installing-database-systems-tools-and-samples.md)합니다.  
  
#### <a name="to-create-the-data-source"></a>데이터 소스를 만들려면  
  
1.  에 **데이터** 메뉴 선택 **데이터 소스 표시**합니다.  
  
2.  에 **데이터 원본** 창에서 **새 데이터 소스 추가** 시작 하는 **데이터 소스 구성 마법사**합니다.  
  
3.  에 **데이터 소스 형식 선택** 화면에서 **데이터베이스**를 선택한 후 **다음**합니다.  
  
4.  에 **데이터 연결 선택** 화면에서 다음 중 하나를 수행 합니다.  
  
    -   Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
         또는  
  
    -   선택 **새 연결** 시작 하는 **연결 추가/수정** 대화 상자.  
  
5.  데이터베이스에서 암호를 요구 하는 경우 중요 한 데이터를 포함 한 다음 선택 옵션을 선택 **다음**합니다.  
  
6.  에 **응용 프로그램 구성 파일에 연결 문자열 저장** 화면에서 **다음**합니다.  
  
7.  에 **데이터베이스 개체 선택** 화면에서 확장 된 **테이블** 노드.  
  
8.  선택 된 `Region` 테이블을 선택한 다음 **마침**합니다.  
  
     **NorthwindDataSet** 프로젝트에 추가 및 `Region` 테이블 표시 되는 **데이터 소스** 창.  
  
## <a name="add-controls-to-the-form-to-display-the-data"></a>데이터를 표시할 폼에 컨트롤 추가  
 항목을 끌어 데이터 바인딩된 컨트롤 만들기는 **데이터 소스** 창에서 폼으로 합니다.  
  
#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>바인딩된 Windows form의 컨트롤에 데이터를 만들려면  
  
-   주 끌어 **지역** 에서 노드는 **데이터 소스** 창에서 폼으로 합니다.  
  
     <xref:System.Windows.Forms.DataGridView> 컨트롤과 레코드 탐색에 사용되는 도구 모음인 <xref:System.Windows.Forms.BindingNavigator>가 폼에 나타납니다. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), `RegionTableAdapter`, <xref:System.Windows.Forms.BindingSource>, 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소 트레이에 나타납니다.  
  
#### <a name="to-add-buttons-that-will-call-the-individual-tableadapter-dbdirect-methods"></a>개별 TableAdapter DbDirect 메서드를 호출하는 단추를 추가하려면  
  
1.  세 개의 끌어 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 끌어다 **Form1** (아래에서 **RegionDataGridView**).  
  
2.  다음 설정 **이름** 및 **텍스트** 각 단추에 대해 속성입니다.  
  
    |이름|텍스트|  
    |----------|----------|  
    |`InsertButton`|**삽입**|  
    |`UpdateButton`|**업데이트**|  
    |`DeleteButton`|**삭제**|  
  
#### <a name="to-add-code-to-insert-new-records-into-the-database"></a>데이터베이스에 새 레코드를 삽입하는 코드를 추가하려면  
  
1.  선택 **InsertButton** 를 click 이벤트에 대 한 이벤트 처리기를 만들고 코드 편집기에서 폼을 엽니다.  
  
2.  `InsertButton_Click` 이벤트 처리기를 다음 코드로 바꿉니다.  
  
     [!code-vb[VbRaddataSaving#1](../data-tools/codesnippet/VisualBasic/save-data-with-the-tableadapter-dbdirect-methods_1.vb)]
     [!code-csharp[VbRaddataSaving#1](../data-tools/codesnippet/CSharp/save-data-with-the-tableadapter-dbdirect-methods_1.cs)]  
  
#### <a name="to-add-code-to-update-records-in-the-database"></a>데이터베이스에서 레코드를 업데이트하는 코드를 추가하려면  
  
1.  두 번 클릭은 **UpdateButton** 를 click 이벤트에 대 한 이벤트 처리기를 만들고 코드 편집기에서 폼을 엽니다.  
  
2.  `UpdateButton_Click` 이벤트 처리기를 다음 코드로 바꿉니다.  
  
     [!code-vb[VbRaddataSaving#2](../data-tools/codesnippet/VisualBasic/save-data-with-the-tableadapter-dbdirect-methods_2.vb)]
     [!code-csharp[VbRaddataSaving#2](../data-tools/codesnippet/CSharp/save-data-with-the-tableadapter-dbdirect-methods_2.cs)]  
  
#### <a name="to-add-code-to-delete-records-from-the-database"></a>데이터베이스에서 레코드를 삭제 하는 코드를 추가 하려면  
  
1.  선택 **DeleteButton** 를 click 이벤트에 대 한 이벤트 처리기를 만들고 코드 편집기에서 폼을 엽니다.  
  
2.  `DeleteButton_Click` 이벤트 처리기를 다음 코드로 바꿉니다.  
  
     [!code-vb[VbRaddataSaving#3](../data-tools/codesnippet/VisualBasic/save-data-with-the-tableadapter-dbdirect-methods_3.vb)]
     [!code-csharp[VbRaddataSaving#3](../data-tools/codesnippet/CSharp/save-data-with-the-tableadapter-dbdirect-methods_3.cs)]  
  
## <a name="run-the-application"></a>응용 프로그램 실행  
  
#### <a name="to-run-the-application"></a>응용 프로그램을 실행하려면  
  
-   선택 **F5** 응용 프로그램을 실행 합니다.  
  
-   선택 된 **삽입** 단추를 선택한 새 레코드가 표에 표시 되는지 확인 합니다.  
  
-   선택 된 **업데이트** 단추를 하 고 표에 레코드가 업데이트 되었는지 확인 합니다.  
  
-   선택 된 **삭제** 단추를 클릭 한 레코드의 표에서 삭제 되는지 확인 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 응용 프로그램 요구 사항에 따라 데이터 바인딩된 폼을 만든 후 수행 해야 할 수 있습니다 하는 몇 단계를 더 합니다. 이 연습에서 보완할 수 있는 사항은 다음과 같습니다.  
  
-   폼에 검색 기능을 추가합니다.  
  
-   추가 테이블을 선택 하 여 데이터 집합에 추가 **마법사로 데이터 집합 구성** 내에서 **데이터 소스** 창. 관련 노드를 폼으로 끌어 관련 데이터를 표시하는 컨트롤을 추가할 수 있습니다. 자세한 내용은 참조 [데이터 집합의 관계](relationships-in-datasets.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터를 다시 데이터베이스에 저장](../data-tools/save-data-back-to-the-database.md)