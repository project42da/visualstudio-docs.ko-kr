---
title: 데이터를 다시 데이터베이스에 저장
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- datasets [Visual Basic], validating data
- data validation, datasets
- data [Visual Studio], saving
- row version
- updating datasets, constraints
- datasets [Visual Basic], about datasets
- datasets [Visual Basic], merging
- updates, constraints in datasets
- saving data, about saving data
- datasets [Visual Basic], constraints
- TableAdapters
ms.assetid: afe6cb8a-dc6a-428b-b07b-903ac02c890b
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 6ecbf8e67b2c8db1b33fa1c5228d9d94f98e48c5
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748061"
---
# <a name="save-data-back-to-the-database"></a>데이터를 다시 데이터베이스에 저장
데이터 집합은 데이터의 메모리 내 복사본입니다. 해당 데이터를 수정 하면 인지 다시 데이터베이스에 변경 내용을 저장 하는 것이 좋습니다. 다음 세 가지 방법 중 하나에서 이렇게합니다.

-   TableAdapter의 업데이트 방법 중 하나를 호출 하 여

-   TableAdapter의 DBDirect 메서드 중 하나를 호출 하 여

-   TableAdapterManager에서 UpdateAll 메서드를 호출 하 여 Visual Studio에 대 한 생성 하면 데이터 집합은 데이터 집합의 다른 테이블에 관련 테이블을 포함 하는 경우

데이터에 바인딩하는 경우 데이터 집합 테이블 Windows Form 이나 XAML 페이지에 있는 컨트롤에 데이터 바인딩 아키텍처 수에 대 한 모든 작업을 수행 합니다.

Tableadapter에 익숙한 경우에 다음이 항목 중 하나에 직접 이동할 수 있습니다.

|항목|설명|
|-----------|-----------------|
|[데이터베이스에 새 레코드 삽입](../data-tools/insert-new-records-into-a-database.md)|업데이트 하 고 Tableadapter 또는 명령 개체를 사용 하 여 삽입 수행 하는 방법|
|[TableAdapter를 사용하여 데이터 업데이트](../data-tools/update-data-by-using-a-tableadapter.md)|Tableadapter 사용 하 여 업데이트를 수행 하는 방법|
|[계층적 업데이트](../data-tools/hierarchical-update.md)|두 개 이상의 관련된 테이블에 있는 데이터 집합의 업데이트를 수행 하는 방법|
|[동시성 예외 처리](../data-tools/handle-a-concurrency-exception.md)|두 명의 사용자가 동시에 데이터베이스에 동일한 데이터를 변경 하려고 할 때 예외를 처리 하는 방법|
|[방법: 트랜잭션을 사용 하 여 데이터 저장](../data-tools/save-data-by-using-a-transaction.md)|System.Transactions 네임 스페이스와 TransactionScope 개체를 사용 하 여 트랜잭션에서 데이터를 저장 하는 방법|
|[연습: 트랜잭션에 데이터 저장](../data-tools/save-data-in-a-transaction.md)|트랜잭션 내에서 데이터베이스 데이터를 저장을 보여 주기 위해 Windows Forms 응용 프로그램을 만드는 연습|
|[데이터베이스에 데이터 저장(여러 테이블)](../data-tools/save-data-to-a-database-multiple-tables.md)|레코드를 편집 하 고 다시 데이터베이스에 여러 테이블의 변경 내용을 저장 하는 방법|
|[개체에서 데이터베이스로 데이터 저장](../data-tools/save-data-from-an-object-to-a-database.md)|TableAdapter DbDirect 메서드를 사용 하 여 데이터베이스에 데이터 집합에 없는 개체에서 데이터를 전달 하는 방법|
|[TableAdapter DBDirect 메서드를 사용하여 데이터 저장](../data-tools/save-data-with-the-tableadapter-dbdirect-methods.md)|TableAdapter 쿼리를 보내는 SQL 데이터베이스에 직접 사용 하는 방법|
|[데이터 집합을 XML로 저장](../data-tools/save-a-dataset-as-xml.md)|XML 문서에 데이터 집합을 저장 하는 방법|

## <a name="two-stage-updates"></a>2 단계 업데이트
 데이터 소스를 업데이트 하는 두 단계로 이루어집니다. 새 레코드, 변경 된 레코드 또는 삭제 된 레코드와 데이터 집합을 업데이트 하는 첫 번째 단계가입니다. 응용 프로그램 데이터 소스에 다시 해당 변경 내용을 전송 하지, 다음 모르는 경우 업데이트를 사용 하 여 완료 합니다.

 를 다시 데이터베이스에 변경 내용을 보내는 경우는 두 번째 단계는 필요 합니다. 데이터 바인딩된 컨트롤을 사용 하지 않는 경우 수동으로 데이터 집합을 채우는 데 사용 하는 같은 TableAdapter (또는 데이터 어댑터)의 Update 메서드를 호출 해야 합니다. 그러나 하나의 데이터 원본에서 데이터 이동 하거나 여러 데이터 원본을 업데이트 하려면 예를 들어 서로 다른 어댑터를 사용할 수도 있습니다. 데이터 바인딩을 사용 하지 않는 관련된 테이블에 대 한 변경 내용을 저장 하는 경우 수동으로 TableAdapterManager 자동 생성 된 클래스의 변수 인스턴스화하고 다음 UdpateAll 메서드를 호출 해야 합니다.

 ![Visual Basic 데이터 집합 업데이트](../data-tools/media/vbdatasetupdates.gif) 2 단계 프로세스 및 성공적으로 업데이트에서 DataRowVersion 역할 업데이트

 데이터 집합 행의 컬렉션을 포함 된 테이블의 컬렉션을 포함 합니다. 나중에 데이터 원본 업데이트 하려는 경우에 행 추가 또는 제거 하는 경우이 DataTable.DataRowCollection 속성에서 메서드를 사용 해야 합니다. 이러한 메서드는 데이터 소스 업데이트에 대 한 필요한 변경 내용 추적을 수행 합니다. 행 속성에 RemoveAt 컬렉션을 호출 하는 경우 삭제는 데이터베이스에 다시 전달 되지 않습니다.

## <a name="merge-datasets"></a>데이터 집합 병합
 데이터 집합의 내용을 업데이트할 수 있습니다 *병합* 사용 하 여 다른 데이터 집합입니다. 이 과정의 내용을 복사는 *소스* 호출 데이터 집합에 데이터 집합 (라고 하는 *대상* 데이터 집합). 데이터 집합을 병합 하면 원본 데이터 집합의 레코드를 새 대상 데이터 집합에 추가 됩니다. 또한 원본 데이터 집합의 추가 열인 대상 데이터 집합에 추가 됩니다. 데이터 집합 병합는 로컬 데이터 집합이 있고 다른 응용 프로그램에서 두 번째 데이터 집합을 가져올 때 유용 합니다. XML 웹 서비스 같은 구성 요소에서 두 번째 데이터 집합을 가져올 때 또는 여러 데이터 집합의 데이터를 통합 해야 할 경우에 유용 합니다.

 데이터 집합을 병합할 때 부울 인수를 전달할 수 있습니다 (`preserveChanges`)을 설명 하는 <xref:System.Data.DataSet.Merge%2A> 메서드 기존 수정 대상 데이터 집합에 보존 하도록 합니다. 여러 버전의 레코드를 유지 하는 데이터 집합, 때문에는 레코드의 둘 이상의 버전을 병합 되는 유의 해야 합니다. 다음 표에서 두 개의 데이터 집합의 레코드는 병합 하는 방법을 보여 줍니다.

|DataRowVersion|대상 데이터 집합|원본 데이터 집합|
|--------------------|--------------------|--------------------|
|원래 색|James Wilson|James C. Wilson|
|현재|Jim Wilson|James C. Wilson|

 호출 된 <xref:System.Data.DataSet.Merge%2A> 이전 테이블에서 메서드 `preserveChanges=false targetDataset.Merge(sourceDataset)` 결과 다음과:

|DataRowVersion|대상 데이터 집합|원본 데이터 집합|
|--------------------|--------------------|--------------------|
|원래 색|James C. Wilson|James C. Wilson|
|현재|James C. Wilson|James C. Wilson|

 호출 된 <xref:System.Data.DataSet.Merge%2A> 메서드 `preserveChanges = true targetDataset.Merge(sourceDataset, true)` 결과 다음과:

|DataRowVersion|대상 데이터 집합|원본 데이터 집합|
|--------------------|--------------------|--------------------|
|원래 색|James C. Wilson|James C. Wilson|
|현재|Jim Wilson|James C. Wilson|

> [!CAUTION]
>  에 `preserveChanges = true` 시나리오에서는 경우는 <xref:System.Data.DataSet.RejectChanges%2A> 메서드는 대상 데이터 집합의 레코드에 대 한 다음 원래 데이터를 되돌린는 *소스* 데이터 집합입니다. 즉, 대상 데이터 집합으로 원래 데이터 소스를 업데이트 하려고 하면 원래 행 업데이트를 찾을 수 없습니다. 데이터 원본에서 업데이트 된 레코드와 다른 데이터 집합을 채운 다음 동시성 위반을 방지 하기 위해 병합을 수행 하 여 동시성 위반을 방지할 수 있습니다. (동시성 위반을 다른 사용자는 데이터 집합 작성 된 후 데이터 원본에서 레코드를 수정할 때 발생 합니다.)

## <a name="update-constraints"></a>제약 조건 업데이트
 기존 데이터 행을 변경 하려면 추가 하거나 개별 열에 데이터를 업데이트 합니다. 데이터 집합 제약 조건 (예: 외래 키 또는 null을 허용 하지 제약 조건)이 있으면 있기 업데이트할 때 레코드 오류 상태에 있을 일시적으로 수 있습니다. 즉, 하나 이상의 열을 업데이트를 완료 하지만 다음에 도달 하기 전에 오류 상태에 수 있습니다.

 예기치 않은 제약 조건 위반을 방지 하기 위해 업데이트 제약 조건을 일시적으로 중단할 수 있습니다. 이 두 가지 용도로 사용 됩니다.

-   오류가 발생 한 열을 업데이트 작업을 완료 했습니다 하지만 다른 업데이트를 시작 하지 않은 후 throw 되지 수 없습니다.

-   특정 업데이트 하는 것을 방지 이벤트의 발생 (유효성 검사를 위한 자주 사용 되는 이벤트).

> [!NOTE]
>  Datagrid에 포함 된 데이터 바인딩 아키텍처는 Windows Forms에서 제약 조건 검사와 행 외부 포커스가 이동 하 고 명시적으로 호출할 필요가 없을 때까지 일시 중단 된 <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, 또는 <xref:System.Data.DataRow.CancelEdit%2A> 메서드.

 제약 조건은 자동으로 비활성화 될 때는 <xref:System.Data.DataSet.Merge%2A> 데이터 집합에서 메서드가 호출 됩니다. 병합이 완료 되 면 모든 제약 조건을 사용할 수 없는 데이터 집합에 있는 경우는 <xref:System.Data.ConstraintException> throw 됩니다. 이 경우에는 <xref:System.Data.DataSet.EnforceConstraints%2A> 속성이 `false,` 다시 설정 하기 전에 모든 제약 조건 위반을 해결 해야는 <xref:System.Data.DataSet.EnforceConstraints%2A> 속성을 `true`합니다.

 업데이트를 완료 한 후 다시 활성화할 수 있습니다 제약 조건 검사 이벤트를 발생 시킨 및는 있습니다.

 이벤트 일시 중단 하는 방법에 대 한 자세한 내용은 참조 [데이터 집합을 채우는 동안 제약 조건을 해제할](../data-tools/turn-off-constraints-while-filling-a-dataset.md)합니다.

## <a name="dataset-update-errors"></a>데이터 집합 업데이트 오류
 데이터 집합의 레코드를 업데이트할 때 오류가 발생할 가능성이 있습니다. 예를 들어 열에 잘못 된 형식의 데이터 또는 너무 긴 데이터 또는 다른 무결성 문제가 있는 데이터를 실수로 작성할 수 있습니다. 또는 모든 단계 업데이트 이벤트의 사용자 지정 오류를 발생 시킬 수 있는 응용 프로그램별 유효성 검사를 할 수 있습니다. 자세한 내용은 참조 [데이터 집합의 데이터 유효성 검사](../data-tools/validate-data-in-datasets.md)합니다.

## <a name="maintaining-information-about-changes"></a>변경 내용에 대 한 정보를 유지 관리
 데이터 집합의 변경 내용에 대 한 정보는 두 가지 방법으로 유지 관리: 행 변경 내용이 있는지 여부를 나타내는 플래그를 지정 하 여 (<xref:System.Data.DataRow.RowState%2A>), 레코드의 여러 복사본을 유지 하 여 (<xref:System.Data.DataRowVersion>). 이 정보를 사용 하 여 프로세스는 데이터 집합에서 변경 된 내용을 결정 하 고 데이터 원본에 적절 한 업데이트를 보낼 수 있습니다.

### <a name="rowstate-property"></a>RowState 속성
 <xref:System.Data.DataRow.RowState%2A> 의 속성을 <xref:System.Data.DataRow> 개체는 데이터의 특정 행의 상태에 대 한 정보를 제공 하는 값입니다.

 다음 표에서 설명의 가능한 값은 <xref:System.Data.DataRowState> 열거형:

|DataRowState 값|설명|
|------------------------|-----------------|
|<xref:System.Data.DataRowState.Added>|에 항목으로는 행이 추가 <xref:System.Data.DataRowCollection>합니다. (이 상태에서 행 해당 원래 버전에 존재 하지 않기 때문 때 마지막 <xref:System.Data.DataRow.AcceptChanges%2A> 메서드가).|
|<xref:System.Data.DataRowState.Deleted>|사용 하 여 행이 삭제 된 <xref:System.Data.DataRow.Delete%2A> 의 <xref:System.Data.DataRow> 개체입니다.|
|<xref:System.Data.DataRowState.Detached>|행 생성 되었지만 하나에 속하지 않는 <xref:System.Data.DataRowCollection>합니다. A <xref:System.Data.DataRow> 를 만든 후 전에 것에 추가한 컬렉션을 즉시 및 컬렉션에서 제거 된 후이 상태 개체입니다.|
|<xref:System.Data.DataRowState.Modified>|행의 열 값은 어떤 식으로든에서 변경 되었습니다.|
|<xref:System.Data.DataRowState.Unchanged>|이후 행이 변경 되지 않은 <xref:System.Data.DataRow.AcceptChanges%2A> 가 마지막으로 호출 합니다.|

### <a name="datarowversion-enumeration"></a>DataRowVersion 열거형
데이터 집합 레코드의 여러 버전을 유지합니다. <xref:System.Data.DataRowVersion> 에서 찾은 값을 검색 하는 경우에 필드를 사용할 수 있습니다는 <xref:System.Data.DataRow> 를 사용 하는 <xref:System.Data.DataRow.Item%2A> 속성 또는 <xref:System.Data.DataRow.GetChildRows%2A> 의 메서드는 <xref:System.Data.DataRow> 개체입니다.

다음 표에서 설명의 가능한 값은 <xref:System.Data.DataRowVersion> 열거형:

|DataRowVersion 값|설명|
|--------------------------|-----------------|
|<xref:System.Data.DataRowVersion.Current>|레코드의 현재 버전 레코드에서 마지막으로 이후에 수행 된 모든 수정 내용을 포함 <xref:System.Data.DataRow.AcceptChanges%2A> 호출 되었습니다. 해당 행이 삭제 된 경우에 된 현재 버전이 없습니다.|
|<xref:System.Data.DataRowVersion.Default>|레코드를 데이터 집합 스키마 또는 데이터 원본에 정의 된 대로의 기본값입니다.|
|<xref:System.Data.DataRowVersion.Original>|레코드의 원래 버전을 데이터 집합에 변경 내용이 마지막으로 커밋된 당시의 레코드의 복사본을입니다. 실질적으로 일반적으로 이것이 레코드의 버전 읽음으로 데이터 원본 에서입니다.|
|<xref:System.Data.DataRowVersion.Proposed>|업데이트 중에 있는 동안에 일시적으로 사용할 수 있는 레코드의 제안된 된 버전-즉, 시간이 호출한는 <xref:System.Data.DataRow.BeginEdit%2A> 메서드 및 <xref:System.Data.DataRow.EndEdit%2A> 메서드. 일반적으로 액세스 한 이벤트 처리기에 있는 레코드의 제안된 된 버전와 같은 <xref:System.Data.DataTable.RowChanging>합니다. 호출 하 여 <xref:System.Data.DataRow.CancelEdit%2A> 메서드는 변경 내용을 취소 하 고 제안 된 버전의 데이터 행을 삭제 합니다.|

 원래 및 현재 버전은 데이터 소스에 업데이트 정보를 전송 하는 경우에 유용 합니다. 일반적으로, 데이터 원본에 대 한 업데이트를 보낼 때 데이터베이스에 대 한 새 정보 레코드의 현재 버전입니다. 업데이트할 레코드를 찾고 원래 버전의 정보 사용 됩니다.

 예를 들어 레코드의 기본 키 변경 되는 경우에서 변경 내용을 업데이트 하려면 데이터 원본에서 올바른 레코드를 찾을 수는 방법이 필요 합니다. 원래 버전이 없으면 레코드 생성 뿐만 아니라 추가 원하지 않는 레코드를 부정확 하 고 오래 된 레코드 데이터 소스에 추가 될 가능성이 가장 하 됩니다. 두 가지 버전 동시성 제어에도 사용 됩니다. 레코드가 dataset에 로드 된 이후 변경 되었는지 여부를 확인 하려면 데이터 원본에서 레코드에 대해 원래 버전을 비교할 수 있습니다.

 제안 된 버전을 실제로 데이터 집합에 변경 내용을 커밋하기 전에 유효성 검사를 수행 해야 하는 경우에 유용 합니다.

 레코드를 변경 하는 경우에 않습니다 항상 해당 행의 업데이트 버전. 테이블에 새 행을 삽입할 때 된 현재 버전만 원래 버전이 없습니다. 마찬가지로, 테이블의 호출 하 여 행을 삭제 하면 `Delete` 메서드를 원래 버전만 있지만 현재 버전이 없습니다.

 레코드의 특정 버전 데이터 행을 쿼리하여 있는지 테스트할 수 <xref:System.Data.DataRow.HasVersion%2A> 메서드. 레코드의 두 버전을 전달 하 여 액세스할 수 있습니다는 <xref:System.Data.DataRowVersion> 열의 값을 요청 하는 경우 선택적 인수로 열거형 값입니다.

## <a name="getting-changed-records"></a>변경 된 레코드 가져오기
 데이터 집합의 모든 레코드를 사용 하는 일반적인이 좋습니다. 예를 들어 사용자 작업할 수 있습니다 Windows Forms <xref:System.Windows.Forms.DataGridView> 레코드 수를 표시 하는 컨트롤입니다. 그러나 사용자 수 업데이트 몇 개의 레코드만, 하나를 삭제 및 삽입 한 새 합니다. 메서드를 제공 하는 데이터 집합 및 데이터 테이블 (`GetChanges`) 수정 된 행만 반환 합니다.

 사용 하 여 변경 된 레코드의 하위 집합을 만들 수는 `GetChanges` 데이터 테이블의 메서드 (<xref:System.Data.DataTable.GetChanges%2A>) 또는 데이터 집합의 (<xref:System.Data.DataSet.GetChanges%2A>) 자체입니다. 데이터 테이블에 대 한 메서드를 호출 하는 경우 변경 된 레코드만 포함 된 테이블의 복사본을 반환 합니다. 마찬가지로, 데이터 집합에서 메서드를 호출 하는 경우에 변경 된 레코드와 새 데이터 집합을 얻습니다.

 `GetChanges` 단독으로 변경 된 모든 레코드를 반환합니다. 반면, 원하는 전달 하 여 <xref:System.Data.DataRowState> 매개 변수로 `GetChanges` 메서드를 원하는 변경 된 레코드의 하위 집합을 지정할 수 있습니다: 새로 분리 된 레코드를 삭제 하도록 표시 된 레코드는 레코드를 추가 또는 수정 된 레코드입니다.

 변경 된 레코드의 하위 집합 가져오기 처리를 위해 다른 구성 요소에 레코드를 보내려고 할 때 유용 합니다. 전체 데이터 집합을 전송 하지 않고 구성 요소에서 필요로 하는 레코드만 가져와서 다른 구성 요소와 통신 하는 오버 헤드를 줄일 수 있습니다.

## <a name="committing-changes-in-the-dataset"></a>데이터 집합의 변경 내용 커밋
 변경 되는 데이터 집합에는 <xref:System.Data.DataRow.RowState%2A> 변경 된 행의 속성을 설정 합니다. 레코드의 원래 및 현재 버전 설정, 유지 및 사용할 수 있는 여는 <xref:System.Data.DataRowView.RowVersion%2A> 속성입니다. 이러한 변경 된 행의 속성에 저장 된 메타 데이터는 데이터 원본에 올바른 업데이트를 보내기 위해 필요 합니다.

 데이터 소스의 현재 상태를 반영 하는 변경 내용을, 더 이상이 정보를 유지 하기 위해 필요 합니다. 일반적으로 두 가지가 데이터 집합 및 소스가 있는 경우 동기화:

-   즉시 정보 소스에서 데이터를 읽을 때와 같은 데이터 집합에 로드 합니다.

-   데이터 원본에 데이터 집합에서 변경 내용을 보낸 후 (전이 아니라 데이터베이스에 변경 내용을 전송 하는 데 필요한 변경 내용 정보가 손실 것 때문에).

호출 하 여 데이터 집합에 보류 중인 변경 내용을 커밋할 수 있습니다는 <xref:System.Data.DataSet.AcceptChanges%2A> 메서드. 일반적으로 <xref:System.Data.DataSet.AcceptChanges%2A> 다음 시간에 호출 됩니다.

-   한 후 데이터 집합을 로드 합니다. TableAdapter를 호출 하 여 데이터 집합을 로드 하는 경우 `Fill` 메서드를 다음 어댑터 자동으로 변경 내용을 커밋하고 있습니다. 그러나 다른 데이터 집합을 병합 하 여 데이터 집합을 로드 하는 경우 다음 해야 수동으로 변경 내용을 커밋해야 합니다.

    > [!NOTE]
    >  호출 하는 경우 변경 내용을 자동으로 커밋되지는 어댑터를 방지할 수 있습니다는 `Fill` 설정 하 여 메서드는 `AcceptChangesDuringFill` 어댑터의 속성 `false`합니다. 로 설정 되어 있으면 `false`, 하면 <xref:System.Data.DataRow.RowState%2A> 채우기 중에 삽입 된 각 행의로 설정 된 <xref:System.Data.DataRowState.Added>합니다.

-   후 데이터 집합 변경 내용을 XML 웹 서비스 같은 다른 프로세스를 보냅니다.

    > [!CAUTION]
    >  이러한 방식으로 변경을 커밋한 변경 정보가 지워집니다. 데이터 집합에 어떤 변경 사항이 알아야 응용 프로그램에 필요한 작업을 수행할 커밋 변경 내용이 아니라 될 때까지 한 후 완료지 않습니다.

이 메서드는 다음을 수행합니다.

-   기록 된 <xref:System.Data.DataRowVersion.Current> 에 레코드의 버전 해당 <xref:System.Data.DataRowVersion.Original> 버전 원래 버전을 덮어씁니다.

-   모든 행을 제거 여기서는 <xref:System.Data.DataRow.RowState%2A> 속성이 <xref:System.Data.DataRowState.Deleted>합니다.

-   설정의 <xref:System.Data.DataRow.RowState%2A> 를 레코드의 속성 <xref:System.Data.DataRowState.Unchanged>합니다.

<xref:System.Data.DataSet.AcceptChanges%2A> 메서드는 세 가지 수준에서 사용할 수 있습니다. 호출할 수 있습니다는 <xref:System.Data.DataRow> 을 커밋 개체는 해당 행에 대 한 변경입니다. 에 대해 호출할 수도 <xref:System.Data.DataTable> 테이블의 모든 행을 커밋하는 개체입니다. 마지막으로,에서 호출할 수는 <xref:System.Data.DataSet> 데이터 집합의 모든 테이블의 모든 레코드의 모든 보류 중인 변경 내용을 커밋하는 개체입니다.

다음 표에서 변경 내용이 커밋된에서 메서드는 개체에 따라 설명 합니다.

|메서드|결과|
|------------|------------|
|<xref:System.Data.DataRow.AcceptChanges%2A?displayProperty=fullName>|특정 행에 대해서만 변경 내용이 커밋됩니다.|
|<xref:System.Data.DataTable.AcceptChanges%2A?displayProperty=fullName>|특정 테이블의 모든 행에 변경 내용이 커밋됩니다.|
|<xref:System.Data.DataSet.AcceptChanges%2A?displayProperty=fullName>|데이터 집합의 모든 테이블의 모든 행에 변경 내용이 커밋됩니다.|

> [!NOTE]
>  TableAdapter를 호출 하 여 데이터 집합을 로드 하는 경우 `Fill` 메서드를 필요가 없습니다 명시적으로 변경 내용을 적용 합니다. 기본적으로는 `Fill` 메서드 호출에서 `AcceptChanges` 데이터 테이블 채우기 완료 된 후 메서드.

 관련된 메서드가 <xref:System.Data.DataSet.RejectChanges%2A>, 복사 하 여 변경 내용의 효과 실행는 <xref:System.Data.DataRowVersion.Original> 버전에 다시는 <xref:System.Data.DataRowVersion.Current> 레코드의 버전입니다. 또한 설정는 <xref:System.Data.DataRow.RowState%2A> 각 레코드 다시로의 <xref:System.Data.DataRowState.Unchanged>합니다.

## <a name="data-validation"></a>데이터 유효성 검사
 응용 프로그램의 데이터에 전달 되는 프로세스의 요구 사항을 충족 하는지 확인 하기 위해 유효성 검사를 추가 해야 하는 경우가 많습니다. 폼에서 사용자가 입력도 구성 요소 내에서 계산 되는 정보가 데이터 원본에 대 한 제약 조건 내에 있는지를 확인 하거나 다른 응용 프로그램에서 응용 프로그램에 전송 된 데이터 유효성을 검사할 정확한 지 확인 합니다. 그러면 만들어질 수 있습니다. 및 응용 프로그램 요구 사항입니다.

 여러 가지 방법으로 데이터를 확인할 수 있습니다.

-   데이터 유효성 검사 응용 프로그램에 코드를 추가 하 여의 비즈니스 계층입니다. 데이터 집합을 한 곳이 수행할 수 있습니다. 백 엔드 유효성 검사의 장점 중 일부 제공-행 및 열 값이 변경 될 때 변경 사항을 확인 하는 등입니다. 자세한 내용은 참조 [데이터 집합의 데이터 유효성 검사](../data-tools/validate-data-in-datasets.md)합니다.

-   표시 계층 양식에 유효성 검사를 추가 합니다. 자세한 내용은 참조 [Windows Forms에서 사용자 입력 유효성 검사](/dotnet/framework/winforms/user-input-validation-in-windows-forms)합니다.

-   데이터 원본에 데이터를 전송 하 여 데이터 백 엔드에서-예를 들어 데이터베이스-하므로 적용 하거나 데이터를 취소 하 고 있습니다. 데이터베이스에 복잡 한 데이터 유효성 검사 및 오류 정보를 제공 하는 기능에 작업 하는 경우 어디에서 가져왔는지에 관계 없이 데이터를 확인할 수 없으므로 실용적인 방법이 될 수 있습니다. 그러나이 방법은 응용 프로그램 관련 요구 사항을 사용할 수 없는 수 있습니다. 그리고 데이터 유효성 검사 데이터 소스 수 발생할 다양 한 왕복에 응용 프로그램이 쉽게 백 엔드에 의해 발생 하는 유효성 검사 오류 해결 방법에 따라 데이터 원본에 있습니다.

    > [!IMPORTANT]
    >  데이터 명령을 사용 하는 경우는 <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> 속성으로 설정 된 <xref:System.Data.CommandType.Text>, 신중 하 게 데이터베이스에 전달 하기 전에 클라이언트에서 전송 되는 정보를 확인 합니다. 악의적인 사용자가를 보내려고 시도할 수 있습니다 (주입) 데이터베이스를 훼손 하거나 무단으로 액세스 하기 위해 SQL 문을 수정 또는 추가 합니다. 데이터베이스에 사용자 입력을 전송 하기 전에 항상 정보가 올바른지 확인 합니다. 항상 매개 변수가 있는 쿼리 또는 가능한 경우 저장된 프로시저를 사용 하는 것이 좋습니다.

## <a name="transmitting-updates-to-the-data-source"></a>데이터 원본에 대 한 전송 업데이트
데이터 집합을 변경한 후에 데이터 원본에 변경 내용을 전송할 수 있습니다. 가장 일반적으로이 호출 하 여 수행 된 `Update` 메서드 TableAdapter (또는 데이터 어댑터). 데이터 테이블의 각 레코드를 통해 메서드 루프는 업데이트 형식을 필요한 결정 (업데이트, 삽입 또는 삭제), 한 다음 적절 한 명령을 실행 합니다.

 업데이트를 적용 하는 방법을의 예시의 경우 응용 프로그램에서 단일 데이터 테이블을 포함 하는 데이터 집합을 사용 한다고 가정 합니다. 응용 프로그램 데이터베이스에서 두 개의 행을 인출합니다. 검색이 수행 된 후 메모리에 데이터 테이블은 다음과 같습니다.

```sql
(RowState)     CustomerID   Name             Status
(Unchanged)    c200         Robert Lyon      Good
(Unchanged)    c400         Nancy Buchanan    Pending
```

 "기본"를 Nancy 선하라 상태를 변경 하는 응용 프로그램 값이이 변경으로 인해는 <xref:System.Data.DataRow.RowState%2A> 에서 해당 행에 대 한 속성 변경 <xref:System.Data.DataRowState.Unchanged> 를 <xref:System.Data.DataRowState.Modified>합니다. 값은 <xref:System.Data.DataRow.RowState%2A> 첫 번째 행에 대 한 속성은 <xref:System.Data.DataRowState.Unchanged>합니다. 데이터 테이블은 이제 다음과 같이 보입니다.

```sql
(RowState)     CustomerID   Name             Status
(Unchanged)    c200         Robert Lyon      Good
(Modified)     c400         Nancy Buchanan    Preferred
```

 이제 응용 프로그램에서 `Update` 메서드를 호출하여 데이터 집합을 데이터베이스로 전송합니다. 메서드는 각 행을 다시 검사합니다. 첫 번째 행에 대 한 메서드가 해당 행이 원래 데이터베이스에서 인출 된 이후 변경 되지 않으므로 SQL 문이 없는 데이터베이스에 전송 합니다.

 그러나 두 번째 행에 대 한는 `Update` 메서드에서 자동으로 올바른 데이터 명령을 호출 하 고 데이터베이스에 전송 합니다. 특정 SQL 문의 구문을 내부 데이터 저장소에서 지 원하는 SQL 언어에 따라 달라 집니다. 그러나 다음과 같은 일반적인 특성은 전송 된 SQL 문을 가지 주목할 만한 합니다.

-   전송 된 SQL 문이 UPDATE 문의 경우 때문에 UPDATE 문을 사용 하는 어댑터가 알의 값은 <xref:System.Data.DataRow.RowState%2A> 속성은 <xref:System.Data.DataRowState.Modified>합니다.

-   UPDATE 문의 대상이 행 임을 나타내는 WHERE 절을 포함 하는 전송 된 SQL 문이 여기서 `CustomerID = 'c400'`합니다. 때문에이 SELECT 문의이 일부를 다른 모든 대상 행을 구별는 `CustomerID` 대상 테이블의 기본 키가 있습니다. 레코드의 원래 버전에서 파생 된 WHERE 절에 대 한 정보 (`DataRowVersion.Original`), 행을 식별 하는 데 필요한 값이 변경 하는 경우.

-   전송 된 SQL 문에 수정 된 열의 새 값을 설정 하는 SET 절을 포함 합니다.

    > [!NOTE]
    > 경우 TableAdapter의 `UpdateCommand` 속성이 저장된 프로시저의 이름으로 설정 되어, 어댑터는 SQL 문을 생성 하지 않습니다. 대신 전달 된 적절 한 매개 변수가 있는 저장된 프로시저를 호출 합니다.

## <a name="passing-parameters"></a>매개 변수 전달
 일반적으로 매개 변수를 사용 하 여 데이터베이스에서 업데이트 하려고 하는 레코드에 대 한 값을 전달 합니다.  때 TableAdapter의 `Update` 메서드는 UPDATE 문 실행, 매개 변수 값을 입력 해야 합니다. 이 값을 가져오는데는 `Parameters` 적절 한 데이터 명령에 대 한 컬렉션-이 경우는 `UpdateCommand` TableAdapter의 개체입니다.

 데이터 어댑터를 생성 하는 Visual Studio 도구를 사용한 적이 있다면는 `UpdateCommand` 문의 각 매개 변수 자리 표시자에 해당 하는 매개 변수 컬렉션을 포함 하는 개체입니다.

 <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A?displayProperty=fullName> 각 매개 변수의 속성 데이터 테이블의 열을 가리킵니다. 예를 들어는 `SourceColumn` 속성에 대 한는 `au_id` 및 `Original_au_id` 매개 변수 작성자 id를 포함 하는 데이터 테이블의 열으로 설정 됩니다. 때 어댑터의 `Update` 메서드 실행 레코드를 업데이트 하는 문을 값을 입력에서 만든이 id 열을 읽습니다.

 UPDATE 문에서 (레코드에 기록 됩니다 하)는 모두 새 값을 이전 값 (되도록 데이터베이스에서 레코드를 찾을 수)도 지정 해야 합니다. 따라서 각 값에 대해 두 개의 매개 변수는: WHERE 절에 대 한와 SET 절에 대 한 합니다. 두 매개 변수 데이터를 업데이트 하는 레코드에서 읽지만 매개 변수의에 따라 열 값의 여러 버전을 받게 <xref:System.Data.SqlClient.SqlParameter.SourceVersion> 속성입니다. SET 절에 대 한 매개 변수는 현재 버전에 가져오고 WHERE 절에 대 한 매개 변수는 원래 버전을 가져옵니다.

> [!NOTE]
> 값을 설정할 수는 `Parameters` 컬렉션 데이터 어댑터에 대 한 이벤트 처리기에서 일반적으로 수행 하려면 코드에서 직접 <xref:System.Data.DataTable.RowChanging> 이벤트입니다.

## <a name="see-also"></a>참고자료

- [Visual Studio의 데이터 집합 도구](../data-tools/dataset-tools-in-visual-studio.md)
- [만들기 및 Tableadapter를 구성 합니다.](create-and-configure-tableadapters.md)
- [TableAdapter를 사용하여 데이터 업데이트](../data-tools/update-data-by-using-a-tableadapter.md)
- [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)
- [데이터 유효성 검사](validate-data-in-datasets.md)
- [데이터 저장](../data-tools/saving-data.md)