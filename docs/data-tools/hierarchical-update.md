---
title: "계층적 업데이트 | Microsoft Docs"
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
- saving data, changed data
- data [Visual Basic], hierarchical update
- saving updated data
- datasets [Visual Basic], hierarchical update
- hierarchical update
- saving data, hierarchical update
- modified data saving
- updated data saving
- related tables, saving
ms.assetid: 68bae3f6-ec9b-45ee-a33a-69395029f54c
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 0091e17cf24a9476dde84cf2d8ad1a34f94e2cdd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="hierarchical-update"></a>계층적 업데이트
*계층적 업데이트* 규칙 참조 무결성을 유지 하면서 데이터베이스에 다시 (두 개 이상의 관련 테이블 집합)의 업데이트 된 데이터를 저장 하는 프로세스를 말합니다. *참조 무결성* 삽입, 업데이트 및 삭제 관련된 레코드의 동작을 제어 하는 데이터베이스에서 제약 조건이 제공 일관성 규칙을 가리킵니다. 예를 들어 이며 해당 고객에 대 한 주문을 만들 수 있도록 허용 하기 전에 customer 레코드를 만들을 적용 하는 참조 무결성  데이터 집합에 있는 관계에 대 한 자세한 내용은 참조 [데이터 집합의 관계](../data-tools/relationships-in-datasets.md)  
  
 계층적 업데이트 기능을 사용 하는 `TableAdapterManager` 를 관리 하는 `TableAdapter`형식화 된 데이터 집합에서 s입니다. `TableAdapterManager` 구성 요소는는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]-않으므로 생성 된 클래스에 속하지는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]합니다. Windows Form 또는 WPF 페이지에 데이터 소스 창에서 테이블을 끌어 Visual Studio 폼 이나 페이지에서 TableAdapterManager 형식의 변수를 추가 하 고 구성 요소 트레이에 디자이너에 표시 합니다. 에 대 한 자세한 내용은 `TableAdapterManager` 의 TableAdapterManager 참조 섹션을 참조 하세요 [Tableadapter](../data-tools/create-and-configure-tableadapters.md)합니다.  
  
 기본적으로 데이터 집합 구조체로 관련된 테이블 "관계에만 해당"을 의미 하는 foreign key 제약 조건을 강제 적용 하지 않습니다. 데이터 집합 디자이너를 사용 하 여 디자인 타임에 해당 설정을 수정할 수 있습니다. (를) 실행 하는 두 테이블 간의 관계 선을 선택 된 **관계** 대화 상자. 여기에서 수행한 변경 내용을 TableAdapterManager 때의 동작 방식을 결정 변경 내용이 관련된 테이블의 데이터베이스를 다시 보내는 것입니다.  
  
## <a name="enable-hierarchical-update-in-a-dataset"></a>데이터 집합에서 계층적 업데이트를 사용 하도록 설정  
 계층적 업데이트는 기본적으로 추가 되거나 프로젝트에서 생성 된 모든 새 데이터 집합에 대해 설정 됩니다. 설정 하 여 계층적 업데이트를 켜거나 끄려면는 **계층적 업데이트** 데이터 집합의 형식화 된 데이터 집합 속성 **True** 또는 **False**:  
  
 ![계층적 업데이트 설정을](../data-tools/media/hierarchical-update-setting.png "계층적 업데이트 설정")  
  
## <a name="create-a-new-relation-between-tables"></a>테이블 간에 새 관계 만들기  
 두 테이블 간에 새 관계를 만들려면 데이터 집합 디자이너에서 각 테이블의 제목 표시줄을 선택, 한 다음 마우스 오른쪽 단추로 클릭 하 고 선택 **관계 추가**합니다.  
  
 ![계층적 업데이트 관계 메뉴 추가](../data-tools/media/hierarchical-update-add-relation-menu.png "계층적 업데이트 관계 메뉴 추가")  
  
## <a name="understand-foreign-key-constraints-cascading-updates-and-deletes"></a>외래 키 제약 조건, 연속 업데이트 및 삭제를 이해 합니다.  
 어떻게 foreign key 제약 조건 이해 해야 하 고 생성 된 데이터 집합 코드로 생성 되는 데이터베이스에 동작을 연계 합니다.  
  
 기본적으로 데이터 집합에 있는 데이터 테이블 관계를 사용 하 여 생성 됩니다 (<xref:System.Data.DataRelation>)와 일치 하는 데이터베이스에서 관계입니다. 그러나 데이터 집합의 관계는 외래 키 제약 조건으로 생성 되지 않습니다. <xref:System.Data.DataRelation> 으로 구성 된 **관계만** 없이 <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> 또는 <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> 적용 합니다.  
  
 기본적으로 연속 업데이트 및 삭제는 해제 되어 데이터베이스 관계를 모두 업데이트 된 설정 및/또는 상태로 하는 경우에 있습니다. 예를 들어 새 고객 및 새 주문을 만들고 데이터를 저장 하려고 충돌할 수는 데이터베이스에 정의 된 외래 키 제약 합니다. 자세한 내용은 참조 [데이터 집합을 채우는 동안 제약 조건을 해제할](turn-off-constraints-while-filling-a-dataset.md)합니다.  
  
## <a name="set-the-order-to-perform-updates"></a>업데이트를 수행 하는 순서를 설정 합니다.  
 집합의 순서가 삽입, 업데이트 및 삭제 하는 데이터 집합의 모든 테이블의 수정된 된 모든 데이터를 저장 하 필요한 업데이트를 수행 하는 순서를 설정 합니다. 계층적 업데이트를 사용 하는 삽입을 먼저 수행 됩니다 한 다음 업데이트 및 다음 삭제 합니다. `TableAdapterManager` 제공는 `UpdateOrder` 집합 업데이트 수행 하기 위해 먼저 다음 삽입 및 삭제 될 수 있는 속성입니다.  
  
> [!NOTE]
>  업데이트 순서는 포괄적 이해 하는 것이 유용 합니다. 즉, 업데이트가 수행 된 삽입 및 삭제는 데이터 집합의 모든 테이블에 대해 수행 됩니다.  
  
 설정 하는 `UpdateOrder` 에서 항목을 끌어 놓은 후 속성은 [데이터 소스 창](add-new-data-sources.md) 선택 폼으로 `TableAdapterManager` 구성 요소 트레이에 제거한 다음 설정에는 `UpdateOrder` 속성에는 **속성** 창. 
  
## <a name="create-a-backup-copy-of-a-dataset-before-performing-a-hierarchical-update"></a>계층적 업데이트를 수행 하기 전에 데이터 집합의 백업 복사본을 만듭니다.  
 데이터를 저장 하면 (호출 하 여는 `TableAdapterManager.UpdateAll()` 메서드), `TableAdapterManager` 단일 트랜잭션 내에서 각 테이블에 대 한 데이터를 업데이트 하려고 합니다. 모든 테이블에 대 한 업데이트에 실패 하면 전체 트랜잭션이 롤백됩니다. 대부분의 경우 롤백을 원래 상태로 응용 프로그램을 반환합니다.  
  
 그러나 경우에 따라 백업 복사본에서 데이터 집합을 복원 해야 할 수 있습니다. 이러한 예로 자동 증분 값을 사용할 때 발생할 수 있습니다. 예를 들어 저장 작업은 실패 하 고, 데이터 집합에 자동 증분 값 다시 설정 되지 않습니다 자동 증분 값을 만들려는 데이터 집합을 계속 합니다. 이런 응용 프로그램에 적합 하지 않을 수 있는 번호에 간격이 있습니다. 경우에이 동기화 문제가 발생 하는 경우는 `TableAdapterManager` 제공는 `BackupDataSetBeforeUpdate` 트랜잭션이 실패 하면 기존 데이터 집합을 백업 복사본으로 대체 하는 속성입니다.  
  
> [!NOTE]
>  백업 복사본은 하는 동안 메모리에만 `TableAdapterManager.UpdateAll` 메서드를 실행 합니다. 따라서이 백업 데이터 집합에 프로그래밍 방식으로 액세스할 수 없습니다 때문에 않습니다 대체 원래 데이터 집합 또는 범위를 벗어날으로 `TableAdapterManager.UpdateAll` 메서드가 실행 합니다.  
  
## <a name="modify-the-generated-save-code-to-perform-the-hierarchical-update"></a>계층적 업데이트를 수행 하는 코드를 저장 한 생성 된 수정  
 `TableAdapterManager.UpdateAll` 메서드를 호출한 다음 관련 테이블이 포함된 데이터 집합의 이름을 전달하여 데이터 집합의 관련 데이터 테이블에서 데이터베이스로 변경 내용을 저장합니다. 예를 들어 NorthwindDataset에 포함된 모든 테이블의 업데이트를 백 엔드 데이터베이스로 보내려면 `TableAdapterManager.UpdateAll(NorthwindDataset)` 메서드를 실행합니다.  
  
 항목을 놓으면는 **데이터 원본** 창, 코드를 자동으로 추가 됩니다는 `Form_Load` 이벤트를 각 테이블을 채웁니다 (의 `TableAdapter.Fill` 메서드). 코드에도 추가 됩니다는 **저장** 단추 클릭 이벤트의는 <xref:System.Windows.Forms.BindingNavigator> 다시 데이터베이스에 데이터 집합에서 데이터를 저장 하려면 (의 `TableAdapterManager.UpdateAll` 메서드).  
  
 생성된 저장 코드에는 `CustomersBindingSource.EndEdit` 메서드를 호출하는 코드 줄도 포함됩니다. 호출 보다 구체적으로 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 첫 번째 메서드 <xref:System.Windows.Forms.BindingSource>폼에 추가 된 합니다. 즉,이 코드는만에서 끌어 첫 번째 테이블에 대해 생성 된 **데이터 소스** 창에서 폼으로 합니다. <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 호출에서는 현재 편집 중인 데이터 바인딩된 컨트롤의 프로세스에 포함된 모든 변경 내용을 커밋합니다. 따라서 데이터 바인딩된 컨트롤에 계속 포커스가 클릭는 **저장** 단추, 보류 중인 모든 편집 컨트롤 하면 실제 저장 전에 커밋된 한다는 점에서 (의 `TableAdapterManager.UpdateAll` 메서드).  
  
> [!NOTE]
>  추가 데이터 집합 디자이너는 `BindingSource.EndEdit` 는 폼에 놓은 첫 번째 테이블에 대 한 코드입니다. 그러므로 폼의 각 관련 테이블에 대해 `BindingSource.EndEdit` 메서드를 호출하는 코드 줄을 추가해야 합니다. 이 연습에서는 `OrdersBindingSource.EndEdit` 메서드 호출을 추가해야 합니다.  
  
#### <a name="to-update-the-code-to-commit-changes-to-the-related-tables-before-saving"></a>저장 전에 관련 테이블로 변경 내용을 커밋하도록 코드를 업데이트하려면  
  
1.  두 번 클릭은 **저장** 단추는 <xref:System.Windows.Forms.BindingNavigator> 열려는 **Form1** 코드 편집기에서.  
  
2.  `OrdersBindingSource.EndEdit` 메서드를 호출하는 줄 뒤에 `CustomersBindingSource.EndEdit` 메서드를 호출하는 코드 줄을 추가합니다. 코드는 **저장** 단추 클릭 이벤트는 다음과 같습니다.  
  
     [!code-vb[VSProDataOrcasHierarchicalUpdate#1](../data-tools/codesnippet/VisualBasic/hierarchical-update_1.vb)]
     [!code-csharp[VSProDataOrcasHierarchicalUpdate#1](../data-tools/codesnippet/CSharp/hierarchical-update_1.cs)]  
  
이처럼 데이터를 데이터베이스에 저장하기 전에 관련 자식 테이블에 대해 변경 내용을 커밋해야 할 뿐 아니라 새 자식 레코드를 데이터 집합에 추가하기 전에 새로 만든 부모 레코드도 커밋해야 할 수 있습니다. 다시 말해서 외래 키 제약 조건으로 인해 새 자식 레코드(Orders)를 데이터 집합에 추가할 수 있도록 설정되기 전에 새 부모 레코드(Customer)를 데이터 집합에 추가해야 할 수 있습니다. 자식 `BindingSource.AddingNew` 이벤트를 사용하면 이 작업을 수행할 수 있습니다.  
  
> [!NOTE]
>  새 부모 레코드를 커밋하 해야 할지 여부를 데이터 소스에 바인딩하는 데 사용 되는 컨트롤의 유형에 따라 달라 집니다. 이 연습에서는 개별 컨트롤 사용 하 여 부모 테이블을 바인딩합니다. 이렇게 하려면 새 부모 레코드를 커밋하는 추가 코드가 필요 합니다. 다음과 같은 복잡 한 바인딩 컨트롤에 부모 레코드가 표시 대신 된 경우는 <xref:System.Windows.Forms.DataGridView>추가로 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 부모 레코드 필요 하지 않을 것에 대 한 호출입니다. 컨트롤의 기본 데이터 바인딩 기능이 새 레코드 커밋을 처리하기 때문입니다.  
  
#### <a name="to-add-code-to-commit-parent-records-in-the-dataset-before-adding-new-child-records"></a>새 자식 레코드를 추가하기 전에 데이터 집합에서 부모 레코드를 커밋하는 코드를 추가하려면  
  
1.  `OrdersBindingSource.AddingNew` 이벤트에 대한 이벤트 처리기를 만듭니다.  
  
    -   열기 **Form1** 디자인 뷰에서 선택 **OrdersBindingSource** 구성 요소 트레이에 선택 **이벤트** 에 **속성** 창 및 다음 두 번 클릭은 **AddingNew** 이벤트입니다.  
  
2.  코드 줄을 호출 하는 이벤트 처리기에 추가 `CustomersBindingSource.EndEdit` 메서드. `OrdersBindingSource_AddingNew` 이벤트 처리기의 코드는 다음과 같습니다.  
  
     [!code-vb[VSProDataOrcasHierarchicalUpdate#2](../data-tools/codesnippet/VisualBasic/hierarchical-update_2.vb)]
     [!code-csharp[VSProDataOrcasHierarchicalUpdate#2](../data-tools/codesnippet/CSharp/hierarchical-update_2.cs)]  
  
## <a name="tableadaptermanager-reference"></a>TableAdapterManager 참조  
 기본적으로는 `TableAdapterManager` 클래스 관련된 테이블을 포함 하는 데이터 집합을 만들 때 생성 됩니다. 클래스를 생성 되지 않도록 하려면의 값을 변경는 `Hierarchical Update` false로 데이터 집합의 속성입니다. Windows Form 또는 WPF 페이지의 디자인 화면으로 관계가 있는 테이블을 끌어 놓으면 Visual Studio 클래스의 멤버 변수를 선언 합니다. 데이터 바인딩을 사용 하지 않는 경우 수동으로 변수를 선언 해야 합니다.  
  
 `TableAdapterManager` 클래스가 않습니다의 일부가 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]합니다. 따라서 설명서에서을 조회할 수 없습니다. 데이터 집합 만들기 프로세스의 일환으로 디자인 타임에 생성 됩니다.  
  
 다음은 자주 사용 되는 메서드 및 속성의는 `TableAdapterManager` 클래스:  
  
|멤버|설명|  
|------------|-----------------|  
|`UpdateAll` 메서드|모든 데이터 테이블의 모든 데이터를 저장합니다.|  
|`BackUpDataSetBeforeUpdate` 속성|실행 하기 전에 데이터 집합의 백업 복사본을 만들 것인지 결정는 `TableAdapterManager.UpdateAll` 메서드. 부울 값입니다.|  
|*tableName* `TableAdapter` 속성|나타냅니다는 `TableAdapter`합니다. 생성 된 `TableAdapterManager` 각각에 대 한 속성이 포함 되어 `TableAdapter` 관리 합니다. 예를 들어, Customers 및 Orders 테이블이 포함 된 데이터 집합으로 생성 됩니다는 `TableAdapterManager` 포함 된 `CustomersTableAdapter` 및 `OrdersTableAdapter` 속성입니다.|  
|`UpdateOrder` 속성|개별 insert, update 및 delete 명령을의 순서를 제어 합니다. 이 설정의 값 중 하나에 `TableAdapterManager.UpdateOrderOption` 열거형입니다.<br /><br /> 기본적으로는 `UpdateOrder` 로 설정 된 **InsertUpdateDelete**합니다. 이 즉, 삽입, 다음 업데이트 및 삭제 한 다음 데이터 집합의 모든 테이블에 대해 수행 됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [데이터를 다시 데이터베이스에 저장](../data-tools/save-data-back-to-the-database.md)