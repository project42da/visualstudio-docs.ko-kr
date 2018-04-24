---
title: 데이터베이스 (여러 테이블)에 데이터를 저장 합니다.
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- updating datasets, walkthroughs
- data [Visual Studio], saving
- saving data, walkthroughs
- data [Visual Studio], updating
ms.assetid: 7ebe03da-ce8c-4cbc-bac0-a2fde4ae4d07
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 5cb987da516c295ea1b3a5b203a1739a70705ae8
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="save-data-to-a-database-multiple-tables"></a>데이터베이스 (여러 테이블)에 데이터를 저장 합니다.
응용 프로그램 개발에서 가장 일반적인 시나리오는 Windows 응용 프로그램의 폼에 데이터를 표시하고 데이터를 편집한 다음 업데이트된 데이터를 데이터베이스로 다시 보내는 것입니다. 이 연습에서는 두 관련 테이블의 데이터를 표시하는 폼을 만들고, 레코드를 편집한 다음 변경 내용을 데이터베이스에 다시 저장하는 방법을 보여줍니다. 이 예에서는 Northwind 샘플 데이터베이스의 `Customers` 및 `Orders` 테이블을 사용합니다.

 TableAdapter의 `Update` 메서드를 호출하여 응용 프로그램의 데이터를 데이터베이스에 다시 저장할 수 있습니다. 테이블을 끌어 오면는 **데이터 소스** 창에서 폼 데이터를 저장 하는 데 필요한 코드는 자동으로 추가 합니다. 폼에 추가 된 테이블을 더이 코드를 수동으로 추가 해야 합니다. 이 연습에서는 둘 이상의 테이블에서 업데이트를 저장하는 코드를 추가하는 방법을 보여줍니다.

> [!NOTE]
>  대화 상자와 메뉴 명령은 활성 설정 또는 사용 중인 버전에 따라 도움말에서 설명 하는 것에서 달라질 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.

 이 연습에서 설명하는 작업은 다음과 같습니다.

-   새 **Windows Forms 응용 프로그램** 프로젝트.

-   만들기 및 응용 프로그램에서 데이터 원본 구성의 [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)합니다.

-   컨트롤에 있는 항목의 설정에서 [데이터 소스 창](add-new-data-sources.md)합니다. 자세한 내용은 참조 [데이터 소스 창에서 끌어 올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)합니다.

-   항목을 끌어 데이터 바인딩된 컨트롤 만들기는 **데이터 소스** 창에서 폼으로 합니다.

-   데이터 집합의 각 테이블의 몇 가지 레코드를 수정 합니다.

-   데이터 집합의 업데이트된 데이터를 데이터베이스로 다시 보내도록 코드를 수정합니다.

## <a name="prerequisites"></a>전제 조건
이 연습에서는 Northwind 샘플 데이터베이스 및 SQL Server Express LocalDB를 사용 합니다.

1.  SQL Server Express LocalDB가 없는 경우 설치에서 [SQL Server Express 다운로드 페이지](https://www.microsoft.com/sql-server/sql-server-editions-express), 또는 **Visual Studio 설치 관리자**합니다. Visual Studio 설치 관리자 SQL Server Express LocalDB의 일부로 설치할 수 있습니다는 **데이터 저장 및 처리** 작업 또는 개별 구성 요소입니다.

2.  다음 단계를 수행 하 여 Northwind 샘플 데이터베이스를 설치 합니다.

    1. Visual Studio에서 열고는 **SQL Server 개체 탐색기** 창. (SQL Server 개체 탐색기의 일부로 설치 되는 **데이터 저장 및 처리** Visual Studio 설치 관리자에서 작업 합니다.) 확장 된 **SQL Server** 노드. LocalDB 인스턴스를 마우스 오른쪽 단추로 클릭 하 고 선택 **새 쿼리 중...** .

       쿼리 편집기 창이 열립니다.

    2. 복사는 [Northwind Transact SQL 스크립트](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) 를 클립보드에 복사 합니다. 이 T-SQL 스크립트를 처음부터 Northwind 데이터베이스를 만들고 데이터로 채웁니다.

    3. 쿼리 편집기에 T-SQL 스크립트를 붙여 넣습니다.를 선택한 후는 **Execute** 단추입니다.

       짧은 시간 후 쿼리 실행이 완료 되 하 고 Northwind 데이터베이스 생성 됩니다.

## <a name="create-the-windows-forms-application"></a>Windows Forms 응용 프로그램 만들기
 첫 번째 단계를 만드는 것을 **Windows Forms 응용 프로그램**합니다. 프로젝트에 이름을 할당은이 단계를 수행 되지만 이름을 지정 하겠습니다 것을 나중에 프로젝트 저장 하겠습니다 때문에 있습니다.

#### <a name="to-create-the-new-windows-forms-application-project"></a>새 Windows forms 응용 프로그램 프로젝트를 만들려면

1. Visual Studio에서에 **파일** 메뉴 선택 **새로**, **프로젝트...** .

2. 확장 **Visual C#** 또는 **Visual Basic** 왼쪽 창에서 선택 **클래식 Windows 데스크톱**합니다.

3. 가운데 창에서 선택 된 **Windows Forms 앱** 프로젝트 형식을 합니다.

4. 프로젝트 이름을 **UpdateMultipleTablesWalkthrough**를 선택한 후 **확인**합니다.

     **UpdateMultipleTablesWalkthrough** 프로젝트를 만들고 추가 **솔루션 탐색기**합니다.

## <a name="create-the-data-source"></a>데이터 원본 만들기
 이 단계 사용 하 여 Northwind 데이터베이스에서 데이터 원본을 만듭니다는 **데이터 소스 구성 마법사**합니다. 연결을 만들려면 Northwind 샘플 데이터베이스에 액세스해야 합니다. Northwind 샘플 데이터베이스 설정에 대 한 정보를 참조 하십시오. [하는 방법: 샘플 데이터베이스 설치](../data-tools/installing-database-systems-tools-and-samples.md)합니다.

#### <a name="to-create-the-data-source"></a>데이터 소스를 만들려면

1.  에 **데이터** 메뉴 선택 **데이터 소스 표시**합니다.

2.  에 **데이터 원본** 창에서**새 데이터 소스 추가** 시작 하는 **데이터 소스 구성 마법사**합니다.

3.  에 **데이터 소스 형식 선택** 화면에서 **데이터베이스**를 선택한 후 **다음**합니다.

4.  에 **데이터 연결 선택** 화면에서 다음 중 하나를 수행 합니다.

    -   Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.

         -또는-

    -   선택 **새 연결** 열려는 **연결 추가/수정** 대화 상자.

5.  데이터베이스에서 암호를 요구 하는 경우 중요 한 데이터를 포함 한 다음 선택 옵션을 선택 **다음**합니다.

6.  에 **응용 프로그램 구성 파일에 연결 문자열 저장**선택, **다음**합니다.

7.  에 **데이터베이스 개체 선택**화면에서 확장 된 **테이블** 노드.

8.  선택 된 **고객** 및 **주문** 테이블을 선택한 다음 선택 **마침**합니다.

     **NorthwindDataSet** 프로젝트에 추가 되는 테이블이에 표시는 **데이터 원본** 창.

## <a name="set-the-controls-to-be-created"></a>만들 컨트롤 설정
 이 연습에서는 데이터에는 `Customers` 테이블은 한 **세부 정보** 개별 컨트롤에 데이터가 표시 되는 레이아웃 합니다. 데이터는 `Orders` 테이블은 한 **그리드** 레이아웃에 표시 되는 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다.

#### <a name="to-set-the-drop-type-for-the-items-in-the-data-sources-window"></a>데이터 소스 창에서 항목에 대한 삭제 유형을 설정하려면

1.  에 **데이터 원본** 창 확장는 **고객** 노드.

2.  에 **고객** 노드를 **세부 정보** 의 제어를 변경 하 고 컨트롤 목록에서는 **고객** 을 개별 컨트롤로 테이블입니다. 자세한 내용은 참조 [데이터 소스 창에서 끌어 올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)합니다.

## <a name="create-the-data-bound-form"></a>데이터 바인딩된 폼 만들기
 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수 있습니다는 **데이터 소스** 창에서 폼으로 합니다.

#### <a name="to-create-data-bound-controls-on-the-form"></a>폼에서 데이터 바인딩된 컨트롤을 만들려면

1.  주 끌어 **고객** 에서 노드는 **데이터 원본** 창으로 **Form1**합니다.

     설명 레이블이 있는 데이터 바인딩된 컨트롤이 레코드 탐색을 위한 도구 모음인 <xref:System.Windows.Forms.BindingNavigator>와 함께 폼에 나타납니다. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), `CustomersTableAdapter`, <xref:System.Windows.Forms.BindingSource>, 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소 트레이에 나타납니다.

2.  관련 끌어 **Orders** 에서 노드는 **데이터 원본** 창으로 **Form1**합니다.

    > [!NOTE]
    >  관련 **Orders** 노드 아래에 있는 **팩스** 열의 자식 노드가 고는 **고객** 노드.

     <xref:System.Windows.Forms.DataGridView> 컨트롤과 레코드 탐색에 사용되는 도구 모음인 <xref:System.Windows.Forms.BindingNavigator>가 폼에 나타납니다. `OrdersTableAdapter` 및 <xref:System.Windows.Forms.BindingSource> 구성 요소 트레이에 나타납니다.

## <a name="add-code-to-update-the-database"></a>데이터베이스를 업데이트 하는 코드 추가
 호출 하 여 데이터베이스를 업데이트할 수는 `Update` 의 메서드는 **고객** 및 **Orders** Tableadapter. 기본적으로 대 한 이벤트 처리기는 **저장** 의 단추는<xref:System.Windows.Forms.BindingNavigator> 데이터베이스에 업데이트를 보내는 폼의 코드에 추가 됩니다. 이 절차를 올바른 순서로 업데이트를 보내는 코드를 수정 합니다. 이렇게 하면 참조 무결성 오류 발생 가능성을 없어집니다. 또한 이 코드는 try-catch 블록에서 업데이트 호출을 래핑하여 오류 처리를 구현합니다. 응용 프로그램의 요구 사항에 맞게 코드를 수정할 수 있습니다.

> [!NOTE]
>  명확성을 위해이 연습에는 트랜잭션을 사용 하지 않습니다. 그러나 이상의 관련 테이블 두 개를 업데이트 하는 경우 트랜잭션 내에서 모든 업데이트 논리를 포함 합니다. 트랜잭션은 변경 내용을 커밋하기 전에 데이터베이스에 대 한 모든 관련된 변경 사항이 정상적으로 수행 되었는지를 확인 하는 프로세스입니다. 자세한 내용은 참조 [트랜잭션 및 동시성](/dotnet/framework/data/adonet/transactions-and-concurrency)합니다.

#### <a name="to-add-update-logic-to-the-application"></a>응용 프로그램에 업데이트 논리를 추가하려면

1.  선택 된 **저장** 단추는 <xref:System.Windows.Forms.BindingNavigator>합니다. 코드 편집기를 엽니다.이 `bindingNavigatorSaveItem_Click` 이벤트 처리기입니다.

2.  관련 TableAdapter의 `Update` 메서드를 호출하도록 이벤트 처리기의 코드를 바꿉니다. 다음 코드는 먼저 각 <xref:System.Data.DataRowState>(<xref:System.Data.DataRowState.Deleted>, <xref:System.Data.DataRowState.Added> 및 <xref:System.Data.DataRowState.Modified>)에 대해 업데이트된 정보를 저장할 3개 임시 데이터 테이블을 만듭니다. 그런 다음 업데이트를 올바른 순서로 실행 됩니다. 이 코드는 다음과 같습니다.

     [!code-vb[VbRaddataSaving#10](../data-tools/codesnippet/VisualBasic/save-data-to-a-database-multiple-tables_1.vb)]
     [!code-csharp[VbRaddataSaving#10](../data-tools/codesnippet/CSharp/save-data-to-a-database-multiple-tables_1.cs)]

## <a name="test-the-application"></a>응용 프로그램 테스트

#### <a name="to-test-the-application"></a>응용 프로그램을 테스트하려면

1.  선택 **F5**합니다.

2.  각 테이블에 포함된 레코드 하나 이상의 데이터를 변경해 봅니다.

3.  선택 된 **저장** 단추입니다.

4.  데이터베이스의 값을 점검하여 변경 내용이 저장되었는지 확인합니다.


## <a name="see-also"></a>참고자료

- [데이터를 다시 데이터베이스에 저장](../data-tools/save-data-back-to-the-database.md)