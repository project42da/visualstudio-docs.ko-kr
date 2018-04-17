---
title: Visual Studio의 개체에 바인딩할 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], object binding
- data [Visual Studio], binding to objects
- object binding
- binding, to objects
ms.assetid: ed743ce6-73af-45e5-a8ff-045eddaccc86
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 71922f3fb6dffb63c1a6c5ed1b12e5cbce402323
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="bind-objects-in-visual-studio"></a>Visual Studio에서 개체 바인딩
Visual Studio 응용 프로그램에서 데이터 원본으로 사용자 지정 개체를 사용 하기 위한 디자인 타임 도구를 제공 합니다. UI 컨트롤에 바인딩할 수 있는 개체에는 데이터베이스에서 데이터를 저장 하려는 경우 클래스 또는 클래스를 생성 하려면 Entity Framework를 사용 하는 것이 좋습니다. 모든 변경 내용 추적 코드, 즉, DbSet 개체에 대해 AcceptChanges를 호출 하는 경우 로컬 개체에 변경 내용을 데이터베이스에 저장 자동으로 자동 생성 하는 entity Framework 합니다. 자세한 내용은 참조 [Entity Framework 설명서](https://ef.readthedocs.org/en/latest/)합니다.  
  
> [!TIP]
>  응용 프로그램이 이미 데이터 집합에 기반한 경우에이 문서에서 개체 바인딩 하는 방법으로 간주 합니다. 데이터 집합을 사용 하 던와 처리할 데이터는 테이블 형식 및 하지 너무 복잡 하거나 너무 큰 경우 이러한 접근 방식은 사용할 수도 있습니다. 훨씬 더 간단 예를 들어 DataReader를 사용 하 고 수동으로 데이터 바인딩에서 없이 UI를 업데이트 하 여 개체에 직접 데이터를 로드 하는 관련 된 참조 [ADO.NET을 사용 하 여 간단한 데이터 응용 프로그램을 만들](../data-tools/create-a-simple-data-application-by-using-adonet.md)합니다.  
  
## <a name="object-requirements"></a>개체의 요구 사항  
 Visual Studio의 디자인 도구는 데이터에 사용할 수 있는 사용자 지정 개체에 대 한 유일한 요구 사항은 개체 공용 속성을 하나 이상 필요 함을입니다.  
  
 일반적으로 사용자 지정 개체는 특정 인터페이스, 생성자, 또는 응용 프로그램에 대 한 데이터 소스로 작동 하는 특성에는 필요 하지 않습니다. 그러나에서 개체를 끌 경우는 **데이터 원본** 데이터 바인딩된 컨트롤을 만드는 디자인 화면에는 창 고 개체가 구현 하는 경우는 <xref:System.ComponentModel.ITypedList> 또는 <xref:System.ComponentModel.IListSource> 인터페이스를 개체에는 기본값이 있어야 합니다. 생성자입니다. 그렇지 않으면 Visual Studio에서 데이터 원본 개체를 인스턴스화할 수 없습니다 및 디자인 화면으로 항목을 끌 때에 오류를 표시 합니다.  
  
## <a name="examples-of-using-custom-objects-as-data-sources"></a>사용자 지정 개체를 사용 하 여 데이터 원본으로의 예  
 개체를 데이터 원본으로 작업 하는 경우 응용 프로그램 논리를 구현 하는 다양 한 방식으로 있을 때는 SQL에 대 한 데이터베이스에 있는 몇 가지 표준 작업 Visual Studio에서 생성 된 TableAdapter 개체를 사용 하 여 간소화할 수 있습니다. 이 페이지에서는 이러한 표준 프로세스를 구현 하는 방법을 설명 TableAdapters.It를 사용 하 여 없습니다 가이드로 사용자 지정 개체를 만들기 위한 합니다. 예를 들어, 개체 또는 응용 프로그램의 논리의 특정 구현에 관계 없이 다음과 같은 일반적인 작업은 일반적으로 수행 합니다.  
  
-   (일반적으로 데이터베이스)에서 개체에 데이터를 로드 합니다.  
  
-   형식화 된 개체 컬렉션을 만드는 중입니다.  
  
-   개체를 추가 하 고 컬렉션에서 개체를 제거 합니다.  
  
-   폼에서 사용자에 게 개체 데이터를 표시 합니다.  
  
-   개체의 데이터 변경/편집 합니다.  
  
-   데이터베이스에 다시 개체에서 데이터를 저장 합니다.   
  
### <a name="load-data-into-objects"></a>데이터 개체를 로드  
 이 예에서는 Tableadapter를 사용 하 여 개체에 데이터를 로드 합니다. Tableadapter는 기본적으로 두 가지 종류의 데이터 테이블 채우기 및 데이터베이스에서 데이터를 인출 하는 메서드를 생성 됩니다.  
  
-   `TableAdapter.Fill` 메서드는 반환 된 데이터로 기존 데이터 테이블을 채웁니다.  
  
-   `TableAdapter.GetData` 메서드 데이터로 채워진 새 데이터 테이블을 반환 합니다.  
  
 데이터를 사용 하 여 사용자 지정 개체를 로드 하는 가장 쉬운 방법은 호출 하는 것은 `TableAdapter.GetData` 메서드를 반환 된 데이터 테이블의 행의 컬렉션을 반복 하 고 각 행의 값과 각 개체를 채웁니다. 만들 수는 `GetData` TableAdapter에 추가 된 쿼리에 대 한 채워진된 데이터 테이블을 반환 하는 메서드.  
  
> [!NOTE]
>  Visual Studio에는 TableAdapter 쿼리 이름을 `Fill` 및 `GetData` 기본적으로 하지만 이러한 이름은 모든 유효한 메서드 이름으로 변경할 수 있습니다.  
  
 다음 예제에서는 데이터 테이블의 행을 반복 하 고 개체를 데이터로 채우는 방법을 보여 줍니다.  
  
 [!code-csharp[VbRaddataConnecting#4](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_1.cs)]
 [!code-vb[VbRaddataConnecting#4](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_1.vb)]  
  
### <a name="create-a-typed-collection-of-objects"></a>형식화 된 개체의 컬렉션 만들기  
 사용자 개체에 대 한 컬렉션 클래스를 만들 수도 있고 자동으로 제공 되는 형식화 된 컬렉션을 사용할 수는 [BindingSource 구성 요소](/dotnet/framework/winforms/controls/bindingsource-component)합니다.  
  
 상속 하는 것이 개체에 대 한 사용자 지정 컬렉션 클래스를 만들 때 <xref:System.ComponentModel.BindingList%601>합니다. 이 제네릭 클래스는 Windows forms에서 데이터 바인딩 인프라에 알림을 보내는 이벤트를 발생 하는 기능 뿐 아니라 컬렉션을 관리 하는 기능을 제공 합니다.  
  
 자동으로 생성 된 컬렉션의 <xref:System.Windows.Forms.BindingSource> 사용 하 여 한 <xref:System.ComponentModel.BindingList%601> 해당 형식화 된 컬렉션에 대 한 합니다. 응용 프로그램 추가 기능을 요구 하지 않는 경우 다음 내에서 컬렉션을 유지 관리할 수 있습니다는 <xref:System.Windows.Forms.BindingSource>합니다. 자세한 내용은 참조는 <xref:System.Windows.Forms.BindingSource.List%2A> 의 속성은 <xref:System.Windows.Forms.BindingSource> 클래스입니다.  
  
> [!NOTE]
>  컬렉션에서의 기본 구현을 제공 하지 않는 하는 기능이 필요한 경우는 <xref:System.ComponentModel.BindingList%601>, 필요에 따라 클래스에 추가할 수 있도록 사용자 지정 컬렉션을 만들어야 합니다.  
  
 다음 코드에서는의 강력한 형식의 컬렉션에 대 한 클래스를 만드는 방법을 보여 줍니다. `Order` 개체:  
  
 [!code-csharp[VbRaddataConnecting#8](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_2.cs)]
 [!code-vb[VbRaddataConnecting#8](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_2.vb)]  
  
### <a name="add-objects-to-a-collection"></a>컬렉션에 개체를 추가 합니다.  
 호출 하 여 개체를 컬렉션에 추가 된 `Add` 또는 사용자 지정 컬렉션 클래스의 메서드는 <xref:System.Windows.Forms.BindingSource>합니다.  
  
 
> [!NOTE]
>  `Add` 메서드는 자동으로 사용자 지정 컬렉션을 위해 제공에서 상속 하는 경우 <xref:System.ComponentModel.BindingList%601>합니다.  
  
 다음 코드에서 형식화 된 컬렉션에 개체를 추가 하는 방법을 보여 줍니다는 <xref:System.Windows.Forms.BindingSource>:  
  
 [!code-csharp[VbRaddataConnecting#5](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_3.cs)]
 [!code-vb[VbRaddataConnecting#5](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_3.vb)]  
  
 다음 코드에서는 개체에서 상속 하는 형식화 된 컬렉션에 추가 하는 방법을 보여 줍니다. <xref:System.ComponentModel.BindingList%601>:  
  
> [!NOTE]
>  이 예제는 `Orders` 컬렉션의 속성은는 `Customer` 개체입니다.  
  
 [!code-csharp[VbRaddataConnecting#6](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_4.cs)]
 [!code-vb[VbRaddataConnecting#6](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_4.vb)]  
  
### <a name="remove-objects-from-a-collection"></a>컬렉션에서 개체를 제거 합니다.  
 호출 하 여 컬렉션에서 개체를 제거는 `Remove` 또는 `RemoveAt` 메서드 또는 사용자 지정 컬렉션 클래스의 <xref:System.Windows.Forms.BindingSource>합니다.  
  
> [!NOTE]
>  `Remove` 및 `RemoveAt` 에서 상속 하는 경우 사용자 지정 컬렉션에 대해 자동으로 메서드는 제공 <xref:System.ComponentModel.BindingList%601>합니다.  
  
 다음 코드에 찾고 있는 형식화 된 컬렉션에서 개체를 제거 하는 방법을 보여 줍니다는 <xref:System.Windows.Forms.BindingSource> 와 <xref:System.Windows.Forms.BindingSource.RemoveAt%2A> 메서드:  
  
 [!code-csharp[VbRaddataConnecting#7](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_5.cs)]
 [!code-vb[VbRaddataConnecting#7](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_5.vb)]  
  
### <a name="display-object-data-to-users"></a>사용자에 게 개체 데이터를 표시 합니다.  
 사용자에 게 개체에 데이터를 표시 하려면 개체 데이터 소스 사용 하 여 프로그램을 만듭니다는 **데이터 소스 구성** 마법사, 다음에서 전체 개체 또는 개별 속성에서 폼으로 끌어 옵니다는 **데이터 원본**창.  
  
### <a name="modify-the-data-in-objects"></a>개체의 데이터 수정  
 Windows Forms 컨트롤에 데이터 바인딩된 사용자 지정 개체의 데이터를 편집 하려면 데이터 바인딩된 컨트롤에 (또는 해당 개체의 속성에 직접)를 편집 하면 됩니다. 데이터 바인딩 아키텍처는 개체의에서 데이터를 업데이트합니다.  
  
 응용 프로그램에 필요한 변경 내용 추적 하 고 원래 값으로 제안 된 변경 내용 뒷면 회전, 개체 모델에서이 기능을 구현 해야 합니다. 어떻게 데이터 테이블을 유지 한 제안 된 변경 내용을 추적의 예 참조 <xref:System.Data.DataRowState>, <xref:System.Data.DataSet.HasChanges%2A>, 및 <xref:System.Data.DataTable.GetChanges%2A>합니다.  
  
### <a name="save-data-in-objects-back-to-the-database"></a>데이터베이스에 다시 개체에 데이터를 저장 합니다.  
 TableAdapter의 DBDirect 메서드를 개체에서 값을 전달 하 여 데이터베이스에 다시 데이터를 저장 합니다.  
  
 Visual Studio는 데이터베이스에 대해 직접 실행할 수 있는 DBDirect 메서드를 만듭니다. 이러한 메서드는 DataSet 또는 DataTable 개체를 필요 하지 않습니다.  
  
|TableAdapter DBDirect 메서드|설명|  
|----------------------------------|-----------------|  
|`TableAdapter.Insert`|개별 열 값 메서드 매개 변수로 전달할 수 있도록 하는 데이터베이스에 새 레코드를 추가 합니다.|  
|`TableAdapter.Update`|기존 데이터베이스의 레코드를 업데이트 합니다. 큐브의 Update 메서드에 메서드 매개 변수로 원래와 새 열 값입니다. 원래 값 원본 레코드를 찾는 데 사용 되 고 해당 레코드를 업데이트 하려면 새 값이 사용 됩니다.<br /><br /> `TableAdapter.Update` 메서드는 또한을 수행 하 여이 데이터 집합의 변경 내용을 데이터베이스로 다시 조정는 <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, <xref:System.Data.DataRow>, 배열 또는 <xref:System.Data.DataRow>메서드 매개 변수로 합니다.|  
|`TableAdapter.Delete`|메서드 매개 변수로 전달 된 원래 열 값에 따라 데이터베이스에서 기존 레코드를 삭제 합니다.|  
  
 개체의 컬렉션에서 데이터를 저장 하려면 (예: 다음에 대 한 루프를 사용 하 여) 개체의 컬렉션을 반복 합니다. TableAdapter의 DBDirect 메서드를 사용 하 여 데이터베이스에 각 개체에 대 한 값을 보냅니다.  
  
 사용 하는 방법을 보여 주는 다음 예제는 `TableAdapter.Insert` DBDirect 메서드는 데이터베이스에 직접 새 고객을 추가 하려면:  
  
 [!code-csharp[VbRaddataSaving#23](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_6.cs)]
 [!code-vb[VbRaddataSaving#23](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_6.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)