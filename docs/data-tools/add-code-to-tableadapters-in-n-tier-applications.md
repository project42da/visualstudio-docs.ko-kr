---
title: N 계층 응용 프로그램에서 Tableadapter에 코드 추가
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- TableAdapters, n-tier applications
- n-tier applications, extending TableAdapters
ms.assetid: dafac00e-df9d-4d4a-95a6-e34b4d099425
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 70c889f6cccd5605758dce05b2a0c4d405aa6714
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="add-code-to-tableadapters-in-n-tier-applications"></a>N 계층 응용 프로그램에서 Tableadapter에 코드 추가
TableAdapter에 대 한 partial 클래스 파일을 만들고 코드를 추가 하 여 TableAdapter의 기능을 확장할 수 있습니다 (코드를 추가 하는 대신는 *DatasetName*합니다. DataSet.Designer 파일)입니다. Partial 클래스는 여러 개의 물리적 파일에서 나눌 수 특정 클래스에 대 한 코드를 사용 합니다. 자세한 내용은 참조 [부분](/dotnet/visual-basic/language-reference/modifiers/partial) 또는 [부분 (형식)](/dotnet/csharp/language-reference/keywords/partial-type)합니다.

TableAdapter를 정의 하는 코드는 데이터 집합에서 TableAdapter에 변경 사항이 발생할 때마다 생성 됩니다. 이 코드는 TableAdapter의 구성을 수정 하는 마법사를 실행 하는 동안 변경 될 때에 생성 됩니다. 코드를 TableAdapter의 재생성 하는 동안 삭제 되지 않도록 방지 하려면 TableAdapter의 partial 클래스 파일에 코드를 추가 합니다.

기본적으로 데이터 집합 및 TableAdapter 코드를 분리 한 후 결과는 각 프로젝트에 개별 클래스 파일이 합니다. 원래 프로젝트에는 파일인 *DatasetName*합니다. Designer.vb (또는 *DatasetName*합니다. Designer.cs) TableAdapter 코드가 들어 있는입니다. 에 지정 된 프로젝트는 **데이터 집합 프로젝트** 속성 라는 파일에 *DatasetName*합니다. DataSet.Designer.vb (또는 *DatasetName*합니다. DataSet.Designer.cs) 데이터 집합 코드를 포함 하 합니다.

> [!NOTE]
>  데이터 집합 및 TableAdapters를 분리할 때는 (설정 하 여는 **데이터 집합 프로젝트** 속성), 프로젝트의 기존 부분 데이터 집합 클래스가 자동으로 이동 되지 것입니다. 기존 부분 데이터 집합 클래스는 데이터 집합 프로젝트에 수동으로 이동 해야 합니다.

> [!NOTE]
> 생성 하기 위한 기능을 제공 하는 데이터 집합 <xref:System.Data.DataTable.ColumnChanging> 및 <xref:System.Data.DataTable.RowChanging> 유효성 검사가 필요한 경우 이벤트 처리기입니다. 자세한 내용은 참조 [n 계층 데이터 집합에 유효성 검사를 추가할](../data-tools/add-validation-to-an-n-tier-dataset.md)합니다.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="to-add-user-code-to-a-tableadapter-in-an-n-tier-application"></a>사용자 코드는 n 계층 응용 프로그램에서 TableAdapter를 추가 하려면

1.  .Xsd 파일을 포함 하는 프로젝트를 찾습니다.

2.  두 번 클릭 하 고 **.xsd** 파일을 열는 **데이터 집합 디자이너**합니다.

3.  코드를 추가 하 고 다음을 선택 하려면 TableAdapter를 마우스 오른쪽 단추로 클릭 **코드 보기**합니다.

     Partial 클래스 생성 되 고 코드 편집기에서 열립니다.

4.  Partial 클래스 선언 내에서 코드를 추가 합니다.

5.  다음 예제에서는 코드를 추가 하는 위치는 `CustomersTableAdapter` 에 `NorthwindDataSet`:

    ```vb
    Partial Public Class CustomersTableAdapter
        ' Add code here to add functionality
        ' to the CustomersTableAdapter.
    End Class
    ```

    ```csharp
    public partial class CustomersTableAdapter
    {
        // Add code here to add functionality
        // to the CustomersTableAdapter.
    }
    ```

## <a name="see-also"></a>참고자료

- [N 계층 데이터 응용 프로그램 개요](../data-tools/n-tier-data-applications-overview.md)
- [n 계층 응용 프로그램에서 데이터 집합에 코드 추가](../data-tools/add-code-to-datasets-in-n-tier-applications.md)
- [만들기 및 Tableadapter를 구성 합니다.](create-and-configure-tableadapters.md)
- [계층적 업데이트 개요](hierarchical-update.md)
