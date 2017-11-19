---
title: "데이터 집합 쿼리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: 7b1a91cf-8b5a-4fc0-ac36-0dc2d336fa1b
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 10e37db09efab78b3048ddeab4096325ba00802f
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="query-datasets"></a>쿼리 데이터 집합
데이터 집합의 특정 레코드를 검색 하려면 FindBy 메서드를 사용 하 여 DataTable에서, 테이블의 행 컬렉션을 반복 하거나 사용 하 여 해당 하는 foreach 문을 작성 [LINQ to DataSet](/dotnet/framework/data/adonet/linq-to-dataset)합니다.  
  
## <a name="dataset-case-sensitivity"></a>데이터 집합의 대/소문자 구분  
데이터 집합 내에서 테이블과 열 이름의 대/소문자 기본적으로-즉, "Customers" 라는 데이터 집합의 테이블 수를 구분 "customers"로 SQL Server를 포함 하 여 여러 데이터베이스에서 명명 규칙 일치 합니다. SQL Server 기본 동작은 대/소문자를 통해서만 데이터 요소의 이름을 구별할 수 없으며입니다.  
  
> [!NOTE]
>  데이터 집합과 달리 스키마에 정의 된 데이터 요소의 이름은 대/소문자 구분 되므로 XML 문서는 대/소문자를 구분 합니다. 예를 들어 스키마 프로토콜을 통해 "Customers"와 "customers" 이라는 다른 테이블 라는 테이블을 정의 하려면 이 값은 대/소문자만 다른 요소를 포함 하는 스키마를 사용 하 여를 dataset 클래스를 생성 하는 경우 이름 충돌이 발생할 수 있습니다.  
  
그러나, 대/소문자 구분 데이터 집합 내에서 데이터를 해석 하는 방법을 하는 요소 수 있습니다. 예를 들어 데이터 집합 테이블의 데이터를 필터링 하는 경우 검색 조건을 비교는 대/소문자 구분 여부에 따라 다른 결과 반환할 수 있습니다. 필터링, 검색, 및 데이터 집합의 설정 하 여 정렬의 대/소문자를 제어할 수 있습니다 <xref:System.Data.DataSet.CaseSensitive%2A> 속성입니다. 데이터 집합에 있는 모든 테이블에서 기본적으로이 속성의 값을 상속 합니다. (각 개별 테이블에 대해이 속성 테이블의 설정 하 여 재정의할 수 있습니다 <xref:System.Data.DataTable.CaseSensitive%2A> 속성입니다.)  
  
## <a name="locate-a-specific-row-in-a-data-table"></a>데이터 테이블의 특정 행 찾기  
  
#### <a name="to-find-a-row-in-a-typed-dataset-with-a-primary-key-value"></a>기본 키 값이 있는 형식화 된 데이터 집합에서 한 행을 찾기 위해  
  
-   행을 찾으려면 호출 강력한 형식의 `FindBy` 테이블의 기본 키를 사용 하는 방법입니다.  
  
     다음 예제에서는 `CustomerID` 있으면의 기본 키 열은 `Customers` 테이블입니다. 즉, 생성 된 `FindBy` 방법은 `FindByCustomerID`합니다. 이 예제에서는 특정 할당 하는 방법을 보여 줍니다 <xref:System.Data.DataRow> 생성 된를 사용 하 여 변수에 `FindBy` 메서드.  
  
     [!code-csharp[VbRaddataEditing#18](../data-tools/codesnippet/CSharp/query-datasets_1.cs)]
     [!code-vb[VbRaddataEditing#18](../data-tools/codesnippet/VisualBasic/query-datasets_1.vb)]  
  
#### <a name="to-find-a-row-in-an-untyped-dataset-with-a-primary-key-value"></a>기본 키 값이 있는 형식화 되지 않은 데이터 집합에는 행을 찾기 위해  
  
-   호출 된 <xref:System.Data.DataRowCollection.Find%2A> 의 메서드는 <xref:System.Data.DataRowCollection> 컬렉션, 기본 키를 매개 변수로 전달 합니다.  
  
     다음 예에서는 라는 새 행을 선언 하는 방법을 보여 줍니다 `foundRow` 의 반환 값을 할당 하 고는 <xref:System.Data.DataRowCollection.Find%2A> 메서드. 기본 키가 없으면 열 인덱스 1의 내용은 메시지 상자에 표시 됩니다.  
  
     [!code-csharp[VbRaddataEditing#19](../data-tools/codesnippet/CSharp/query-datasets_2.cs)]
     [!code-vb[VbRaddataEditing#19](../data-tools/codesnippet/VisualBasic/query-datasets_2.vb)]  
  
## <a name="find-rows-by-column-values"></a>열 값으로 행을 찾습니다.  
  
#### <a name="to-find-rows-based-on-the-values-in-any-column"></a>모든 열에 값을 기반으로 하는 행을 찾으려면  
  
-   데이터 테이블을 사용 하 여 만들어진는 <xref:System.Data.DataTable.Select%2A> 의 배열을 반환 하 <xref:System.Data.DataRow>에 전달 된 식에 따라 s는 <xref:System.Data.DataTable.Select%2A> 메서드. 유효한 식의 작성 하는 방법에 대 한 자세한 내용은 페이지의 "식 구문" 섹션에 대 한 참조는 <xref:System.Data.DataColumn.Expression%2A> 속성입니다.  
  
     사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Data.DataTable.Select%2A> 의 메서드는 <xref:System.Data.DataTable> 특정 행을 찾거나 합니다.  
  
     [!code-csharp[VbRaddataEditing#20](../data-tools/codesnippet/CSharp/query-datasets_3.cs)]
     [!code-vb[VbRaddataEditing#20](../data-tools/codesnippet/VisualBasic/query-datasets_3.vb)]  
  
## <a name="access-related-records"></a>관련 레코드 액세스  
데이터 집합에 테이블이 관련 되는 경우는 <xref:System.Data.DataRelation> 개체가 다른 테이블에서 사용할 수 있는 관련된 레코드를 만들 수 있습니다. 예를 들어 데이터 집합 포함 하는 `Customers` 및 `Orders` 테이블에 만들어 사용할 수 있습니다.  
  
사용할 수 있습니다는 <xref:System.Data.DataRelation> 호출 하 여 관련된 레코드를 찾을 개체는 <xref:System.Data.DataRow.GetChildRows%2A> 의 메서드는 <xref:System.Data.DataRow> 부모 테이블에서 합니다. 이 메서드는 관련된 자식 레코드의 배열을 반환합니다. 하거나 호출할 수 있습니다는 <xref:System.Data.DataRow.GetParentRow%2A> 의 메서드는 <xref:System.Data.DataRow> 자식 테이블에 있습니다. 이 메서드는 단일 반환 <xref:System.Data.DataRow> 부모 테이블에서 합니다.  
  
이 페이지에서는 형식화 된 데이터 집합을 사용 하는 예제를 제공 합니다. 형식화 되지 않은 데이터 집합에서 관계를 탐색 하는 방법에 대 한 정보를 참조 하십시오. [Datarelation 탐색](/dotnet/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations)합니다.  
  
> [!NOTE]
>  Windows Forms 응용 프로그램에서 작업 하는 데이터 바인딩 기능을 사용 하 여 데이터를 표시 하는 경우 디자이너에서 생성 된 양식 응용 프로그램에 대 한 충분 한 기능을 제공할 수 있습니다. 자세한 내용은 참조 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)합니다. 특히 참조 [데이터 집합의 관계](relationships-in-datasets.md)합니다.  
  
다음 코드 예제에서는 형식화 된 데이터 집합의 관계 위/아래로 이동 하는 방법을 보여 줍니다. 입력 한 코드 예제에서는 사용 하 여 <xref:System.Data.DataRow>s (`NorthwindDataSet.OrdersRow`) 및 생성 된 FindBy*PrimaryKey* (`FindByCustomerID`) 메서드를 원하는 행을 찾아 관련된 레코드를 반환 합니다. 예제를 컴파일하고 있는 경우에 올바르게 실행:  
  
-   라는 데이터 집합의 인스턴스 `NorthwindDataSet` 와 `Customers` 테이블입니다.  
  
-   `Orders` 테이블입니다.  
  
-   명명 된 관계 `FK_Orders_Customers`두 테이블을 연결 합니다.  
  
또한 반환 될 모든 레코드에 대 한 데이터로 채울 수 두 테이블 모두 필요 합니다.  
  
#### <a name="to-return-the-child-records-of-a-selected-parent-record"></a>자식 선택한 부모 레코드의 레코드를 반환 하려면  
  
-   호출 된 <xref:System.Data.DataRow.GetChildRows%2A> 메서드는 특정 `Customers` 데이터에서 행의 배열을 반환 하 고 행을 `Orders` 테이블:  
  
     [!code-csharp[VbRaddataDatasets#6](../data-tools/codesnippet/CSharp/query-datasets_4.cs)]
     [!code-vb[VbRaddataDatasets#6](../data-tools/codesnippet/VisualBasic/query-datasets_4.vb)]  
  
#### <a name="to-return-the-parent-record-of-a-selected-child-record"></a>선택한 자식 레코드의 부모 레코드를 반환 하려면  
  
-   호출의 <xref:System.Data.DataRow.GetParentRow%2A> 메서드는 특정 `Orders` 데이터 행과 단일 행에서 반환 된 `Customers` 테이블:  
  
     [!code-csharp[VbRaddataDatasets#7](../data-tools/codesnippet/CSharp/query-datasets_5.cs)]
     [!code-vb[VbRaddataDatasets#7](../data-tools/codesnippet/VisualBasic/query-datasets_5.vb)]

## <a name="see-also"></a>참고 항목
[Visual Studio의 데이터 집합 도구](../data-tools/dataset-tools-in-visual-studio.md)  