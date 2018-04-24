---
title: N 계층 데이터 집합에 유효성 검사 추가
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- n-tier applications, validating
- validation [Visual Basic], n-tier data applications
- validating n-tier data applications
ms.assetid: 34ce4db6-09bb-4b46-b435-b2514aac52d3
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: ed9bcb4521b5e9bdad839563aae1c566d20a5681
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="add-validation-to-an-n-tier-dataset"></a>N 계층 데이터 집합에 유효성 검사 추가
N 계층 솔루션으로 분리 되어 있는 데이터 집합에 유효성 검사 추가 기본적으로 단일 파일 (단일 프로젝트에서 데이터 집합) 데이터 집합에 유효성 검사와 동일 합니다. 데이터에 유효성 검사를 수행 하기 위한 권장된 위치는 동안는 <xref:System.Data.DataTable.ColumnChanging> 및/또는 <xref:System.Data.DataTable.RowChanging> 데이터 테이블의 이벤트입니다.

 데이터 집합을 데이터 집합에 있는 데이터 테이블의 열 및 행 변경 이벤트에 사용자 코드를 추가할 수는 partial 클래스를 생성 하는 기능을 제공 합니다. N 계층 솔루션에 대 한 데이터 집합에 코드를 추가 하는 방법에 대 한 자세한 내용은 참조 [n 계층 응용 프로그램에서 데이터 집합에 코드 추가](../data-tools/add-code-to-datasets-in-n-tier-applications.md), 및 [n 계층 응용 프로그램에서 Tableadapter에 코드를 추가할](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md)합니다. Partial 클래스에 대 한 자세한 내용은 참조 [하는 방법: 클래스 (클래스 디자이너)를 부분 클래스로 분할](../ide/how-to-split-a-class-into-partial-classes-class-designer.md) 또는 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)합니다.

> [!NOTE]
>  데이터 집합에서 TableAdapters 분리할 때는 (설정 하 여는 **데이터 집합 프로젝트** 속성), 프로젝트의 기존 부분 데이터 집합 클래스가 자동으로 이동할 수 없습니다. 기존 부분 데이터 집합 클래스는 데이터 집합 프로젝트에 수동으로 이동 해야 합니다.

> [!NOTE]
>  데이터 집합 디자이너 자동으로 만들지 않으므로 이벤트 처리기에 대 한 C#에서 <xref:System.Data.DataTable.ColumnChanging> 및 <xref:System.Data.DataTable.RowChanging> 이벤트입니다. 수동으로 이벤트 처리기를 만들고 이벤트를 이벤트 처리기를 연결 해야 합니다. 다음 절차는 Visual Basic 및 C#에서 필요한 이벤트 처리기를 만드는 방법을 설명 합니다.

## <a name="validate-changes-to-individual-columns"></a>개별 열에 변경 내용 유효성 검사
 처리 하 여 개별 열에 값을 유효성 검사는 <xref:System.Data.DataTable.ColumnChanging> 이벤트입니다. <xref:System.Data.DataTable.ColumnChanging> 이벤트는 열에 값을 수정 하면 발생 합니다. 에 대 한 이벤트 처리기를 만들고는 <xref:System.Data.DataTable.ColumnChanging> 원하는 열을 두 번 클릭 하 여 이벤트는 **데이터 집합 디자이너**합니다.

 열을 두 번 클릭 처음으로 디자이너에 대 한 이벤트 처리기가 생성 된 <xref:System.Data.DataTable.ColumnChanging> 이벤트입니다. `If...Then` 문이 만들어집니다 특정 열에 대 한 테스트 하는 합니다. 예를 들어 다음 코드는 Northwind Orders 테이블에서 RequiredDate 열을 두 번 클릭할 때 생성 됩니다.

```vb
Private Sub OrdersDataTable_ColumnChanging(ByVal sender As System.Object, ByVal e As System.Data.DataColumnChangeEventArgs) Handles Me.ColumnChanging
    If (e.Column.ColumnName = Me.RequiredDateColumn.ColumnName) Then
        ' Add validation code here.
    End If
End Sub
```

> [!NOTE]
>  C# 프로젝트에서 데이터 집합 디자이너는 데이터 집합 및 데이터 집합의 개별 테이블에 대 한 partial 클래스 만듭니다. 데이터 집합 디자이너가에 대 한 이벤트 처리기에 자동으로 만들지 않으므로 <xref:System.Data.DataTable.ColumnChanging> 및 <xref:System.Data.DataTable.RowChanging> C# 같은 Visual Basic에서의 이벤트입니다. C# 프로젝트에서 이벤트를 처리 하 고 메서드는 기본 이벤트를 후크 하는 메서드를 수동으로 구성 해야 합니다. 다음 절차는 Visual Basic 및 C#에서 필요한 이벤트 처리기를 만드는 단계를 제공 합니다.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

#### <a name="to-add-validation-during-changes-to-individual-column-values"></a>개별 열 값을 변경 하는 동안 유효성 검사를 추가 하려면

1.  두 번 클릭 하 여 데이터 집합을 열고는 **.xsd** 파일 **솔루션 탐색기**합니다. 자세한 내용은 참조 [연습: 데이터 집합 디자이너에서 데이터 집합 만들기](walkthrough-creating-a-dataset-with-the-dataset-designer.md)합니다.

2.  유효성을 검사 하려는 열을 두 번 클릭 합니다. 이 작업을 만듭니다는 <xref:System.Data.DataTable.ColumnChanging> 이벤트 처리기입니다.

    > [!NOTE]
    >  데이터 집합 디자이너 자동으로 C# 이벤트에 대 한 이벤트 처리기를 만들지 않습니다. C#에서 이벤트를 처리 하는 코드는 다음 섹션에 포함 됩니다. `SampleColumnChangingEvent` 생성 되 고 다음로 후크는 <xref:System.Data.DataTable.ColumnChanging> 이벤트에는 <xref:System.Data.DataTable.EndInit%2A> 메서드.

3.  코드를 확인 하는 추가 `e.ProposedValue` 응용 프로그램의 요구 사항을 충족 하는 데이터를 포함 합니다. 제안 된 값을 수용할 수 없으면 오류가 포함 되어 있음을 나타내도록 열을 설정 합니다.

     다음 코드 예제를 확인 하 고 **수량** 열 0 보다 큰 값을 포함 합니다. 경우 **수량** 보다 작거나 0으로 열을 오류로 설정 되어 있습니다. `Else` 절 지웁니다 오류 **수량** 0 보다 큰 것입니다. 열 변경 이벤트 처리기의 코드는 다음과 같습니다.

    ```vb
    If (e.Column.ColumnName = Me.QuantityColumn.ColumnName) Then
        If CType(e.ProposedValue, Short) <= 0 Then
            e.Row.SetColumnError(e.Column, "Quantity must be greater than 0")
        Else
            e.Row.SetColumnError(e.Column, "")
        End If
    End If
    ```
    ```csharp
    // Add this code to the DataTable partial class.

    public override void EndInit()
    {
        base.EndInit();
        // Hook up the ColumnChanging event
        // to call the SampleColumnChangingEvent method.
        ColumnChanging += SampleColumnChangingEvent;
    }

    public void SampleColumnChangingEvent(object sender, System.Data.DataColumnChangeEventArgs e)
    {
        if (e.Column.ColumnName == QuantityColumn.ColumnName)
        {
            if ((short)e.ProposedValue <= 0)
            {
                e.Row.SetColumnError("Quantity", "Quantity must be greater than 0");
            }
            else
            {
                e.Row.SetColumnError("Quantity", "");
            }
        }
    }
    ```

## <a name="validate-changes-to-whole-rows"></a>전체 열에 변경 내용 유효성 검사
 처리 하 여 전체 행에서에서 값의 유효성 검사는 <xref:System.Data.DataTable.RowChanging> 이벤트입니다. <xref:System.Data.DataTable.RowChanging> 모든 열에 있는 값은 커밋할 때 이벤트가 발생 합니다. 유효성을 검사 해야 하는 <xref:System.Data.DataTable.RowChanging> 한 열에 값이 다른 열에 값에 의존 하는 경우 이벤트입니다. 예를 들어 Northwind의 Orders 테이블의 OrderDate 및 RequiredDate를 고려 합니다.

 주문 입력 되는 유효성 검사에서는 주문 OrderDate 앞에 있는 RequiredDate로 입력 되지 않도록 합니다. 이 예제에서는 OrderDate와 RequiredDate 열에 대 한 값 비교 될 필요 하므로 개별 열 변경 유효성을 검사 하는 의미가 없습니다.

 에 대 한 이벤트 처리기를 만들고는 <xref:System.Data.DataTable.RowChanging> 테이블의 제목 표시줄에 테이블 이름을 두 번 클릭 이벤트는 **데이터 집합 디자이너**합니다.

#### <a name="to-add-validation-during-changes-to-whole-rows"></a>전체 행을 변경 하는 동안 유효성 검사를 추가 하려면

1.  두 번 클릭 하 여 데이터 집합을 열고는 **.xsd** 파일 **솔루션 탐색기**합니다. 자세한 내용은 참조 [연습: 데이터 집합 디자이너에서 데이터 집합 만들기](walkthrough-creating-a-dataset-with-the-dataset-designer.md)합니다.

2.  디자이너에 있는 데이터 테이블의 제목 표시줄 두 번 클릭 합니다.

     Partial 클래스 만들어집니다는 `RowChanging` 이벤트 처리기 및 코드 편집기에서 열립니다.

    > [!NOTE]
    >  데이터 집합 디자이너에서는 대 한 이벤트 처리기를 자동으로 만들어지지 않습니다는 <xref:System.Data.DataTable.RowChanging> C# 프로젝트에서 이벤트입니다. 처리 하는 메서드를 만들어야 할는 <xref:System.Data.DataTable.RowChanging> 이벤트 및 테이블의 초기화 메서드에서 이벤트를 후크 다음에 코드를 실행된 합니다.

3.  Partial 클래스 선언 내에 사용자 코드를 추가 합니다.

4.  다음 코드는 동안 유효성을 검사 하는 사용자 코드를 추가 하는 위치를 보여 줍니다.는 <xref:System.Data.DataTable.RowChanging> 이벤트입니다. C# 예제에는 또한 최대 이벤트 처리기 메서드를 연결 하는 코드가 포함 되어는 `OrdersRowChanging` 이벤트입니다.

    ```vb
    Partial Class OrdersDataTable
        Private Sub OrdersDataTable_OrdersRowChanging(ByVal sender As System.Object, ByVal e As OrdersRowChangeEvent) Handles Me.OrdersRowChanging
            ' Add logic to validate columns here.
            If e.Row.RequiredDate <= e.Row.OrderDate Then
                ' Set the RowError if validation fails.
                e.Row.RowError = "Required Date cannot be on or before the OrderDate"
            Else
                ' Clear the RowError when validation passes.
                e.Row.RowError = ""
            End If
        End Sub
    End Class
    ```
    ```csharp
    partial class OrdersDataTable
    {
        public override void EndInit()
        {
            base.EndInit();
            // Hook up the event to the
            // RowChangingEvent method.
            OrdersRowChanging += RowChangingEvent;
        }

        public void RowChangingEvent(object sender, OrdersRowChangeEvent e)
        {
            // Perform the validation logic.
            if (e.Row.RequiredDate <= e.Row.OrderDate)
            {
                // Set the row to an error when validation fails.
                e.Row.RowError = "Required Date cannot be on or before the OrderDate";
            }
            else
            {
                // Clear the RowError if validation passes.
                e.Row.RowError = "";
            }
        }
    }
    ```

## <a name="see-also"></a>참고 항목

- [N 계층 데이터 응용 프로그램 개요](../data-tools/n-tier-data-applications-overview.md)
- [연습: N 계층 데이터 응용 프로그램 만들기](../data-tools/walkthrough-creating-an-n-tier-data-application.md)
- [데이터 집합의 데이터 유효성 검사](../data-tools/validate-data-in-datasets.md)