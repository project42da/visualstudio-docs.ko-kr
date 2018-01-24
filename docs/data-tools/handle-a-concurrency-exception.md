---
title: "동시성 예외 처리 | Microsoft Docs"
ms.custom: 
ms.date: 09/11/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- concurrency control, exceptions
- datasets [Visual Basic], errors
- exception handling, concurrency issues
- data concurrency, walkthroughs
- updating datasets, errors
- concurrency control, walkthroughs
ms.assetid: 73ee9759-0a90-48a9-bf7b-9d6fc17bff93
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 71572ac38c7aed3154360d3bad9e4b84fe0107e3
ms.sourcegitcommit: 49aa031cbebdd9c7ec070c713afb1a97d1ecb701
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="handle-a-concurrency-exception"></a>동시성 예외 처리
동시성 예외 (<xref:System.Data.DBConcurrencyException>)는 두 명의 사용자가 동시에 데이터베이스에 동일한 데이터를 변경 하려고 할 때 발생 합니다. Catch 하는 방법을 보여 주는 Windows 응용 프로그램을 만들면이 연습에서는 한 <xref:System.Data.DBConcurrencyException>를 오류를 발생 하는 행 키를 찾아 처리 하는 방법에 대 한 전략에 알아봅니다.  
  
 이 연습에서는 다음 프로세스를 안내합니다.  
  
1.  새 **Windows Forms 응용 프로그램** 프로젝트를 만듭니다.  
  
2.  Northwind에 따라 새 데이터 집합을 만들 `Customers` 테이블입니다.  
  
3.  있는 폼을 만듭니다는 <xref:System.Windows.Forms.DataGridView> 데이터를 표시 합니다.  
  
4.  데이터 집합의 데이터로 채우는 `Customers` Northwind 데이터베이스의 테이블입니다.  
  
5.  사용 하 여는 **테이블 데이터 표시** 기능 **서버 탐색기** 액세스로는 `Customers` 테이블의 데이터 및 레코드를 변경 합니다.  
  
6.  다른 값으로 동일한 레코드를 변경 하 고, 데이터 집합 업데이트 발생 하는 동시성 오류가 발생 하는 데이터베이스에 변경 내용을 쓸 시도 합니다.  
  
7.  오류를 catch 한 다음 계속 하 고 데이터베이스를 업데이트 또는 업데이트 작업을 취소 여부를 결정 하는 레코드의 서로 다른 버전을 표시 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
이 연습에서는 Northwind 샘플 데이터베이스 및 SQL Server Express LocalDB를 사용 합니다.  
  
1.  SQL Server Express LocalDB가 없는 경우 설치에서 [SQL Server Express 다운로드 페이지](https://www.microsoft.com/sql-server/sql-server-editions-express), 또는 **Visual Studio 설치 관리자**합니다. Visual Studio 설치 관리자 SQL Server Express LocalDB의 일부로 설치할 수 있습니다는 **데이터 저장 및 처리** 작업 또는 개별 구성 요소입니다.  
  
2.  다음 단계를 수행 하 여 Northwind 샘플 데이터베이스를 설치 합니다.  

    1. Visual Studio에서 열고는 **SQL Server 개체 탐색기** 창. (SQL Server 개체 탐색기의 일부로 설치 되는 **데이터 저장 및 처리** Visual Studio 설치 관리자에서 작업 합니다.) 확장 된 **SQL Server** 노드. LocalDB 인스턴스를 마우스 오른쪽 단추로 클릭 하 고 선택 **새 쿼리 중...** .  

       쿼리 편집기 창이 열립니다.  

    2. 복사는 [Northwind Transact SQL 스크립트](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) 를 클립보드에 복사 합니다. 이 T-SQL 스크립트를 처음부터 Northwind 데이터베이스를 만들고 데이터로 채웁니다.  

    3. 쿼리 편집기에 T-SQL 스크립트를 붙여 넣습니다.를 선택한 후는 **Execute** 단추입니다.  

       짧은 시간 후 쿼리 실행이 완료 되 하 고 Northwind 데이터베이스 생성 됩니다.  
  
> [!NOTE]
>  대화 상자와 메뉴 명령은 활성 설정 또는 사용 중인 버전에 따라 도움말에서 설명 하는 것에서 달라질 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="create-a-new-project"></a>새 프로젝트 만들기  
 새 Windows Forms 응용 프로그램을 만들어 여 연습을 시작 합니다.  
  
#### <a name="to-create-a-new-windows-forms-application-project"></a>새 Windows Forms 응용 프로그램 프로젝트를 만들려면  
  
1. Visual Studio에서에 **파일** 메뉴 선택 **새로**, **프로젝트...** .  
  
2. 확장 **Visual C#** 또는 **Visual Basic** 왼쪽 창에서 선택 **클래식 Windows 데스크톱**합니다.  

3. 가운데 창에서 선택 된 **Windows Forms 앱** 프로젝트 형식을 합니다.  

4. 프로젝트 이름을 **ConcurrencyWalkthrough**를 선택한 후 **확인**합니다. 
  
     **ConcurrencyWalkthrough** 프로젝트를 만들고 추가 **솔루션 탐색기**, 디자이너에서 새 양식을 엽니다.  
  
## <a name="create-the-northwind-dataset"></a>Northwind 데이터 집합 만들기  
 라는 데이터 집합을 만들면이 섹션에서는 `NorthwindDataSet`합니다.  
  
#### <a name="to-create-the-northwinddataset"></a>NorthwindDataSet를 만들려면  
  
1.  에 **데이터** 메뉴 선택 **새 데이터 소스 추가**합니다.  
  
     [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png) 열립니다.  
  
2.  에 **데이터 소스 형식 선택** 화면에서 **데이터베이스**합니다.  
  
3.  사용 가능한 연결 목록에서 Northwind 샘플 데이터베이스에 대 한 연결을 선택 합니다. 연결의 연결 목록에서 사용할 수 없는 경우 선택 **새 연결**  
  
    > [!NOTE]
    >  로컬 데이터베이스 파일에 연결 하는 경우 선택 **아니요** 파일을 프로젝트에 추가 하려는 묻는 메시지가 나타나면 합니다.  
  
4.  에 **응용 프로그램 구성 파일에 연결 문자열 저장** 화면에서 **다음**합니다.  
  
5.  확장 된 **테이블** 노드 선택한는 `Customers` 테이블입니다. 데이터 집합에 대 한 기본 이름이 있어야 `NorthwindDataSet`합니다.  
  
6.  선택 **마침** 를 프로젝트에 데이터 집합을 추가 합니다.  
  
## <a name="create-a-data-bound-datagridview-control"></a>데이터 바인딩된 DataGridView 컨트롤 만들기  
 이 섹션에서는 만들는 <xref:System.Windows.Forms.DataGridView> 끌어는 **고객** 에서 항목의 **데이터 소스** 창 Windows Form으로 합니다.  
  
#### <a name="to-create-a-datagridview-control-that-is-bound-to-the-customers-table"></a>Customers 테이블에 바인딩되는 DataGridView 컨트롤을 만들려면  
  
1.  에 **데이터** 메뉴 선택 **데이터 소스 표시** 열려는 **데이터 소스 창**합니다.  
  
2.  에 **데이터 원본** 창 확장는 **NorthwindDataSet** 노드를 선택한 후는 **고객** 테이블입니다.  
  
3.  테이블 노드의 아래쪽 화살표를 선택한 다음 선택 **DataGridView** 드롭 다운 목록에 있습니다.  
  
4.  폼의 빈 영역에 테이블을 끕니다.  
  
     A <xref:System.Windows.Forms.DataGridView> 라는 컨트롤 `CustomersDataGridView` 및 <xref:System.Windows.Forms.BindingNavigator> 라는 `CustomersBindingNavigator` 에 바인딩된 폼에 추가 <xref:System.Windows.Forms.BindingSource>합니다. 이 선반에 바인딩되어는 `Customers` 테이블에 `NorthwindDataSet`합니다.  
  
## <a name="test-the-form"></a>양식을 테스트합니다  
 이제 폼이이 지점까지 예상 대로 동작 하는지 확인을 테스트할 수 있습니다.  
  
#### <a name="to-test-the-form"></a>양식을 테스트 하려면  
  
1.  선택 **F5** 응용 프로그램을 실행 하려면  
  
     폼이 표시는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 데이터로 채워지는 `Customers` 테이블입니다.  
  
2.  에 **디버그** 메뉴 선택 **디버깅 중지**합니다.  
  
## <a name="handle-concurrency-errors"></a>동시성 오류 처리  
 오류를 처리 하는 방법은 응용 프로그램을 제어 하는 특정 비즈니스 규칙에 따라 달라 집니다. 이 연습에 대 한 동시성 오류를 처리 하는 방법에 대 한 예를 들어 다음 전략을 사용 했습니다.  
  
 레코드의 세 가지 버전으로 사용자를 표시 하는 응용 프로그램:  
  
-   데이터베이스의 현재 레코드  
  
-   원래 데이터 집합에 로드 된 레코드  
  
-   데이터 집합의 제안 된 변경 내용  
  
그러면 사용자는 제안 된 버전으로 데이터베이스를 덮어쓸 또는 업데이트 작업을 취소 및 데이터베이스에서 새 값으로 데이터 집합 새로 고침 수입니다.  
  
#### <a name="to-enable-the-handling-of-concurrency-errors"></a>동시성 오류 처리를 사용 하도록 설정 하려면  
  
1.  사용자 지정 오류 처리기를 만듭니다.  
  
2.  사용자에 게 선택 항목을 표시 합니다.  
  
3.  사용자의 응답을 처리 합니다.  
  
4.  업데이트를 다시 하거나 데이터 집합의 데이터를 다시 설정 합니다.  
  
### <a name="add-code-to-handle-the-concurrency-exception"></a>동시성 예외를 처리 하는 코드를 추가 합니다.  
 업데이트를 수행 하려고 하면 예외가 발생 하는 경우 일반적으로 발생된 한 예외에서 제공 되는 정보로 작업을 수행 하려고 합니다.  
  
 이 섹션에서는 데이터베이스를 업데이트 하는 코드를 추가 합니다. 또한 처리 모든 <xref:System.Data.DBConcurrencyException> 이 발생, 다른 예외 뿐만 아니라 합니다.  
  
> [!NOTE]
>  `CreateMessage` 및 `ProcessDialogResults` 이 연습의 뒷부분에서 메서드를 추가 합니다.  
  
##### <a name="to-add-error-handling-for-the-concurrency-error"></a>동시성 오류에 대해 오류 처리를 추가 하려면  
  
1.  아래에 다음 코드를 추가 `Form1_Load` 메서드:  
  
     [!code-csharp[VbRaddataConcurrency#1](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_1.cs)]
     [!code-vb[VbRaddataConcurrency#1](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_1.vb)]  
  
2.  대체는 `CustomersBindingNavigatorSaveItem_Click` 호출할 메서드를는 `UpdateDatabase` 메서드는 다음과 같습니다.  
  
     [!code-csharp[VbRaddataConcurrency#2](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_2.cs)]
     [!code-vb[VbRaddataConcurrency#2](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_2.vb)]  
  
### <a name="display-choices-to-the-user"></a>사용자에 게 선택 사항 표시  
 방금 코드 작성 호출에서 `CreateMessage` 프로시저를 사용자에 게 오류 정보를 표시 합니다. 이 연습에서는 사용자에 게 서로 다른 버전의 레코드를 표시 하는 메시지 상자를 사용 합니다. 그러면 사용자가 레코드 변경 내용으로 덮어쓰거나 편집을 취소할 것인지를 선택할 수 있습니다. 응답에 전달 되 면 사용자가 메시지 상자에 있는 (단추 클릭) 하는 옵션을 선택 된 `ProcessDialogResult` 메서드.  
  
##### <a name="to-create-the-message-to-display-to-the-user"></a>사용자에 게 표시할 메시지를 만들려면  
  
-   다음 코드를 추가 하 여 메시지를 만들는 **코드 편집기**합니다. 아래에 다음이 코드를 입력의 `UpdateDatabase` 메서드.  
  
     [!code-csharp[VbRaddataConcurrency#4](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_3.cs)]
     [!code-vb[VbRaddataConcurrency#4](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_3.vb)]  
  
### <a name="process-the-users-response"></a>사용자의 응답을 처리 합니다.  
 메시지 상자에 대 한 사용자의 응답을 처리 하는 코드가 있어야 합니다. 옵션은 중 하나를 덮어쓰고 데이터베이스의 현재 레코드 제안 된 변경으로 인해 또는 로컬 변경 내용을 데이터베이스에 현재 있는 레코드와 데이터 테이블을 새로 고칩니다. 예, 선택한 경우에 <xref:System.Data.DataTable.Merge%2A> 메서드는 *preserveChanges* 인수로 설정 `true`합니다. 이렇게 하면 레코드의 원래 버전 데이터베이스의 레코드와 일치 하므로 성공 하려면 업데이트 시도 됩니다.  
  
##### <a name="to-process-the-user-input-from-the-message-box"></a>메시지 상자에서 입력 한 사용자를 처리 하려면  
  
-   이전 섹션에 추가 된 코드 아래에 다음 코드를 추가 합니다.  
  
     [!code-csharp[VbRaddataConcurrency#3](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_4.cs)]
     [!code-vb[VbRaddataConcurrency#3](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_4.vb)]  
  
## <a name="test-the-form"></a>양식을 테스트합니다  
 이제 예상 대로 동작 되도록 폼을 테스트할 수 있습니다. 동시성 위반을 시뮬레이션 하기 NorthwindDataSet를 채운 후 데이터베이스의 데이터를 변경 해야 합니다.  
  
#### <a name="to-test-the-form"></a>양식을 테스트 하려면  
  
1.  선택 **F5** 응용 프로그램을 실행 합니다.  
  
2.  폼이 나타나면 계속 해 서 실행 하 고 Visual Studio IDE를 전환 합니다.  
  
3.  에 **보기** 메뉴 선택 **서버 탐색기**합니다.  
  
4.  **서버 탐색기**, 응용 프로그램을 사용 하는 한 다음 확장 연결 확장은 **테이블** 노드.  
  
5.  마우스 오른쪽 단추로 클릭는 **고객** 테이블을 선택한 다음 **테이블 데이터 표시**합니다.  
  
6.  첫 번째 레코드에 (`ALFKI`) 변경 `ContactName` 를 `Maria Anders2`합니다.  
  
    > [!NOTE]
    >  변경 내용을 커밋하지 다른 행으로 이동 합니다.  
  
7.  로 전환는 `ConcurrencyWalkthrough`의 폼을 실행 합니다.  
  
8.  양식에서 첫 번째 레코드에 (`ALFKI`), 변경`ContactName` 를 `Maria Anders1`합니다.  
  
9. 선택 된 **저장** 단추입니다.  
  
     동시성 오류가 발생 하 고 메시지 상자가 나타납니다.  
  
10. 선택 하면 **아니요** 업데이트를 취소 하 고 현재 데이터베이스에 있는 값으로 데이터 집합을 업데이트 합니다. 선택 하면 **예** 제안 된 값이 데이터베이스에 기록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터를 다시 데이터베이스에 저장](../data-tools/save-data-back-to-the-database.md)
