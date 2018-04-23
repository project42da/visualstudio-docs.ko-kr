---
title: '방법: 엔터티 클래스에 유효성 검사 추가'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 61107da9-7fa3-4dba-b101-ae46536f52c4
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 6adcdd2d1bead72c1ff615731aa26be664f1f455
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-add-validation-to-entity-classes"></a>방법: 엔터티 클래스에 유효성 검사 추가
*유효성 검사* 엔터티 클래스는 확인의 데이터 개체에 입력 한 값 제약 조건 개체의 스키마 및 응용 프로그램에 설정 된 규칙을 준수 하는 프로세스입니다. 업데이트를 내부 데이터베이스에 보내기 전에 데이터의 유효성을 검사하면 오류를 줄일 수 있습니다. 또한 응용 프로그램과 데이터베이스 간에 발생할 수 있는 잠재적 라운드트립 횟수를 줄일 수 있습니다.

 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md) 삽입, 업데이트 하는 동안 실행 되 고 전체 엔터티 및 또한 동안과 그 후 개별 열을 삭제 하는 디자이너에서 생성 된 코드를 확장 하는 데 사용할 수 있는 부분 메서드를 제공 합니다. 변경합니다.

> [!NOTE]
>  이 항목에서는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]를 사용하여 엔터티 클래스에 유효성 검사를 추가하는 기본 단계를 설명합니다. 특정 엔터티 클래스를 참조 하지 않고이 일반 단계를 수행 하기 어려울 수 있습니다, 때문에 실제 데이터를 사용 하는 연습이 제공 되었습니다.

## <a name="adding-validation-for-changes-to-the-value-in-a-specific-column"></a>변경 내용에 대한 유효성 검사를 특정 열의 값에 추가
 이 절차는 열의 값이 변경될 때 데이터의 유효성을 검사하는 방법을 보여 줍니다. 유효성 검사는 사용자 인터페이스 대신 클래스 정의 내에서 수행되기 때문에 값에 대한 유효성 검사가 실패하면 예외가 throw됩니다. 응용 프로그램에서 열 값을 변경하려고 하는 코드에 대한 오류 처리를 구현하세요.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

#### <a name="to-validate-data-during-a-columns-value-change"></a>열의 값을 변경하는 동안 데이터의 유효성을 검사하려면

1.  열거나 새 LINQ to SQL 클래스 파일을 만듭니다 (**.dbml** 파일)에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다. (두 번 클릭 하 고 **.dbml** 파일을 **솔루션 탐색기**.)

2.  O/R 디자이너에서 유효성 검사를 추가 하 고 클릭 한 다음 클래스를 마우스 오른쪽 단추로 **코드 보기**합니다.

     선택한 엔터티 클래스의 partial 클래스와 함께 코드 편집기가 열립니다.

3.  커서를 partial 클래스에 놓습니다.

4.  Visual Basic 프로젝트의 경우

    1.  확장 된 **메서드 이름** 목록입니다.

    2.  찾을 **OnCOLUMNNAMEChanging** 유효성 검사를 추가 하려는 열에 대 한 메서드.

    3.  `OnCOLUMNNAMEChanging` 메서드가 partial 클래스에 추가 됩니다.

    4.  다음 코드를 추가하여 입력된 값을 먼저 확인한 다음 열에 입력된 값이 응용 프로그램에서 허용되는지 확인합니다. 다음 `value` 인수는 제안된 값을 포함하고 있으므로 이를 유효한 값으로 확인하는 논리를 추가합니다.

        ```vb
        If value.HasValue Then
            ' Add code to ensure that the value is acceptable.
            ' If value < 1 Then
            '    Throw New Exception("Invalid data!")
            ' End If
        End If
        ```

    C# 프로젝트의 경우:

    C# 프로젝트의 이벤트 처리기를 자동으로 생성 하지 않기 때문에 열 변경 부분 메서드를 만드는 IntelliSense를 사용할 수 있습니다. `partial`을 입력한 다음 사용 가능한 부분 메서드에 액세스하기 위한 공간을 입력합니다. 유효성 검사를 추가할 열에 대해 열 변경 메서드를 클릭합니다. 다음 코드는 열 변경 부분 메서드를 선택 하면 생성 되는 코드와 유사 합니다.

    ```csharp
    partial void OnCOLUMNNAMEChanging(COLUMNDATATYPE value)
        {
           throw new System.NotImplementedException();
        }
    ```

## <a name="adding-validation-for-updates-to-an-entity-class"></a>업데이트에 대한 유효성 검사를 엔터티 클래스에 추가
 변경하는 동안 값을 검사하는 작업 이외에도 전체 엔터티 클래스에 대해 업데이트를 시도할 때 데이터의 유효성을 검사할 수도 있습니다. 비즈니스 규칙에서 여러 열의 값에 대한 비교를 요구하는 경우 업데이트를 시도하는 동안 유효성 검사가 해당 작업을 수행합니다. 다음 절차는 전체 엔터티 클래스를 업데이트하려고 할 때 유효성을 검사하는 방법을 보여 줍니다.

> [!NOTE]
>  전체 엔터티 클래스 업데이트에 대한 유효성 검사 코드는 특정 엔터티 클래스의 partial 클래스가 아니라 partial <xref:System.Data.Linq.DataContext> 클래스에서 실행됩니다.

#### <a name="to-validate-data-during-an-update-to-an-entity-class"></a>엔터티 클래스에 대한 업데이트 동안 데이터의 유효성을 검사하려면

1.  열거나 새 LINQ to SQL 클래스 파일을 만듭니다 (**.dbml** 파일)에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다. (두 번 클릭 하 고 **.dbml** 파일을 **솔루션 탐색기**.)

2.  O/R 디자이너의 빈 영역을 마우스 오른쪽 단추로 클릭 하 고 클릭 **코드 보기**합니다.

     `DataContext`의 partial 클래스와 함께 코드 편집기가 열립니다.

3.  커서를 `DataContext`의 partial 클래스에 놓습니다.

4.  Visual Basic 프로젝트의 경우

    1.  확장 된 **메서드 이름** 목록입니다.

    2.  클릭 **UpdateENTITYCLASSNAME**합니다.

    3.  `UpdateENTITYCLASSNAME` 메서드가 partial 클래스에 추가 됩니다.

    4.  다음 코드에 표시된 것과 같은 `instance` 인수를 사용하여 개별 열 값에 액세스합니다.

        ```vb
        If (instance.COLUMNNAME = x) And (instance.COLUMNNAME = y) Then
            Dim ErrorMessage As String = "Invalid data!"
            Throw New Exception(ErrorMessage)
        End If
        ```

    C# 프로젝트의 경우:

    C# 프로젝트의 이벤트 처리기를 자동으로 생성 하지 않기 때문에 IntelliSense를 사용 하 여 partial를 만들 수 있습니다 `UpdateCLASSNAME` 메서드. `partial`을 입력한 다음 사용 가능한 부분 메서드에 액세스하기 위한 공간을 입력합니다. 유효성 검사를 추가할 클래스에 대해 업데이트 메서드를 클릭합니다. 다음과 유사한 코드를 선택 하면 생성 되는 코드는 `UpdateCLASSNAME` 부분 메서드:

    ```csharp
    partial void UpdateCLASSNAME(CLASSNAME instance)
    {
        if ((instance.COLUMNNAME == x) && (instance.COLUMNNAME = y))
        {
            string ErrorMessage = "Invalid data!";
            throw new System.Exception(ErrorMessage);
        }
    }
    ```

## <a name="see-also"></a>참고자료

- [LINQ to SQL Tools in Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)(Visual Studio의 LINQ to SQL 도구)
- [데이터 유효성 검사](../data-tools/validate-data-in-datasets.md)
- [LINQ to SQL (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/index)