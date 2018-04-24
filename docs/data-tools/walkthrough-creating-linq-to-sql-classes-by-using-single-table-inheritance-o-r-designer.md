---
title: '연습: 단일 테이블 상속 (O R 디자이너)를 사용 하 여 LINQ to SQL 클래스 만들기'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 63bc6328-e0df-4655-9ce3-5ff74dbf69a4
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: d634032daae58c72dd1c24a89db5bd2eb353149a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-or-designer"></a>연습: 단일 테이블 상속을 사용하여 LINQ to SQL 클래스 만들기(O/R 디자이너)
[LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md) 관계형 시스템에서 일반적으로 구현 되므로 단일 테이블 상속을 지원 합니다. 이 연습에서 제공 하는 일반 단계에 따라 확장는 [하는 방법: O/R 디자이너를 사용 하 여 상속 구성](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md) 항목의 상속의 사용을 보여 주기 위해 몇 가지 실제 데이터를 제공 하 고는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다.

 이 연습에서는 다음 작업을 수행합니다.

-   데이터베이스 테이블을 만들고 그 안에 데이터를 추가합니다.

-   Windows Forms 응용 프로그램을 만듭니다.

-   [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 파일을 프로젝트에 추가합니다.

-   새 엔터티 클래스를 만듭니다.

-   상속을 사용하도록 엔터티 클래스를 구성합니다.

-   상속된 클래스를 쿼리합니다.

-   Windows Form에 데이터를 표시합니다.

## <a name="create-a-table-to-inherit-from"></a>상속에 사용될 테이블 만들기
 상속이 어떻게 작동하는지 보기 위해 작은 Person 테이블을 만들어서 기본 클래스로 사용한 다음 이를 상속하는 Employee 개체를 만듭니다.

#### <a name="to-create-a-base-table-to-demonstrate-inheritance"></a>상속을 보여 주기 위한 기본 테이블을 만들려면

1.  **서버 탐색기**/**데이터베이스 탐색기**를 마우스 오른쪽 단추로 클릭는 **테이블** 노드와 클릭 **새 테이블 추가**합니다.

    > [!NOTE]
    >  Northwind 데이터베이스 또는 테이블을 추가할 수 있는 기타 데이터베이스를 사용할 수 있습니다.

2.  테이블 디자이너에서 다음 열을 테이블에 추가합니다.

    |열 이름|데이터 형식|Null 허용|
    |-----------------|---------------|-----------------|
    |**ID**|**int**|**False**|
    |**Type**|**int**|**True**|
    |**FirstName**|**nvarchar(200)**|**False**|
    |**LastName**|**nvarchar(200)**|**False**|
    |**관리자**|**int**|**True**|

3.  ID 열을 기본 키로 설정합니다.

4.  테이블을 저장 하 고 이름을 **사람**합니다.

## <a name="add-data-to-the-table"></a>테이블에 데이터 추가
 속성이 올바르게 구성되었는지 확인하기 위해서는 단일 테이블 상속에서 각 클래스에 대한 몇 가지 데이터가 테이블에 필요합니다.

#### <a name="to-add-data-to-the-table"></a>테이블에 데이터를 추가하려면

1.  데이터 뷰에서 테이블을 엽니다. (마우스 오른쪽 단추로 클릭는 **사람** 테이블에 **서버 탐색기**/**데이터베이스 탐색기** 클릭 **테이블 데이터 표시**.)

2.  다음 데이터를 테이블로 복사합니다. (있습니다 수 복사한 다음 결과 창에는 전체 행을 선택 하 여 테이블에 붙여 넣습니다.)

    ||||||
    |-|-|-|-|-|
    |**ID**|**Type**|**FirstName**|**LastName**|**관리자**|
    |**1**|**1**|**Anne**|**월리스**|**NULL**|
    |**2**|**1**|**Carlos**|**Grilo**|**NULL**|
    |**3**|**1**|**Yael**|**Peled**|**NULL**|
    |**4**|**2**|**Gatis**|**Ozolins**|**1**|
    |**5**|**2**|**Andreas**|**Hauser**|**1**|
    |**6**|**2**|**Tiffany**|**Phuvasate**|**1**|
    |**7**|**2**|**Alexey**|**Orekhov**|**2**|
    |**8**|**2**|**Michał**|**Poliszkiewicz**|**2**|
    |**9**|**2**|**비상**|**파견 된 킴이**|**2**|
    |**10**|**2**|**Fabricio**|**Noriega**|**3**|
    |**11**|**2**|**구재석**|**Martin**|**3**|
    |**12**|**2**|**박 단은**|**Kwok**|**3**|

## <a name="create-a-new-project"></a>새 프로젝트 만들기
 테이블을 만든 후에는 상속 구성을 보여 주기 위한 새 프로젝트를 만듭니다.

#### <a name="to-create-the-new-windows-forms-application"></a>새 Windows Forms 응용 프로그램을 만들려면

1. Visual Studio에서에 **파일** 메뉴 선택 **새로**, **프로젝트...** .

2. 확장 **Visual C#** 또는 **Visual Basic** 왼쪽 창에서 선택 **클래식 Windows 데스크톱**합니다.

3. 가운데 창에서 선택 된 **Windows Forms 앱** 프로젝트 형식을 합니다.

4. 프로젝트 이름을 **InheritanceWalkthrough**를 선택한 후 **확인**합니다.

     **InheritanceWalkthrough** 프로젝트 생성 되며에 추가할 **솔루션 탐색기**합니다.

## <a name="add-a-linq-to-sql-classes-file-to-the-project"></a>프로젝트에 LINQ to SQL 클래스 파일 추가

#### <a name="to-add-a-linq-to-sql-file-to-the-project"></a>프로젝트에 LINQ to SQL 파일을 추가하려면

1.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.

2.  클릭는 **LINQ to SQL 클래스** 템플릿과 클릭 **추가**합니다.

     .dbml 파일이 프로젝트에 추가되고 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]가 열립니다.

## <a name="create-the-inheritance-by-using-the-or-designer"></a>O/R 디자이너를 사용하여 상속 만들기
 드래그 하 여 상속 구성는 **상속** 에서 개체는 **도구 상자** 디자인 화면으로 합니다.

#### <a name="to-create-the-inheritance"></a>상속을 만들려면

1.  **서버 탐색기**/**데이터베이스 탐색기**로 이동 된 **사람** 앞에서 만든 테이블입니다.

2.  끌어서는 **사람** 테이블는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 디자인 화면입니다.

3.  두 번째 끌어 **사람** 테이블는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 에 해당 이름을 변경 하 고 **직원**합니다.

4.  삭제는 **관리자** 속성은 **사람** 개체입니다.

5.  삭제는 **형식**, **ID**, **FirstName**, 및 **LastName** 에서 속성의 **직원** 개체입니다. (즉, 삭제 하는 모든 속성을 제외 하 고 **관리자**.)

6.  **개체 관계형 디자이너** 탭은 **도구 상자**을 만듭니다는 **상속** 사이 **사람** 및  **직원** 개체입니다. 이 작업을 수행 하려면는 **상속** 항목에 **도구 상자** 마우스 단추를 놓습니다. 그런 다음을 클릭는 **직원** 개체 차례로 **사람** 개체에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다. 상속 선의 화살표가 가리키는 **사람** 개체입니다.

7.  클릭는 **상속** 디자인 화면에서 선을 합니다.

8.  설정의 **판별자 속성** 속성을 **형식**합니다.

9. 설정의 **Derived Class Discriminator Value** 속성을 **2**합니다.

10. 설정의 **Base Class Discriminator Value** 속성을 **1**합니다.

11. 설정의 **Inheritance Default** 속성을 **사람**합니다.

12. 프로젝트를 빌드합니다.

## <a name="query-the-inherited-class-and-display-the-data-on-the-form"></a>상속된 클래스 쿼리 및 폼에 데이터 표시
 이제 개체 모델에서 특정 클래스에 대해 쿼리하는 폼에 일부 코드를 추가할 수 있습니다.

#### <a name="to-create-a-linq-query-and-display-the-results-on-the-form"></a>LINQ 쿼리를 만들고 폼에 결과를 표시하려면

1.  끌어서는 **ListBox** Form1으로 합니다.

2.  폼을 두 번 클릭하여 `Form1_Load` 이벤트 처리기를 만듭니다.

3.  다음 코드를 `Form1_Load` 이벤트 처리기에 추가합니다.

    ```vb
    Dim dc As New DataClasses1DataContext
    Dim results = From emp In dc.Persons _
        Where TypeOf emp Is Employee _
        Select emp

    For Each Emp As Employee In results
        ListBox1.Items.Add(Emp.LastName)
    Next
    ```

    ```csharp
    NorthwindDataContext dc = new DataClasses1DataContext();
    var results = from emp in dc.Persons
                  where emp is Employee
                  select emp;

    foreach(Employee Emp in results)
    {
        listBox1.Items.Add(Emp.LastName)
    }
    ```

## <a name="test-the-application"></a>응용 프로그램을 테스트합니다.
 응용 프로그램을 실행하고 목록 상자에 표시된 레코드가 모두 직원(Type 열의 값이 2인 레코드)인지 확인합니다.

#### <a name="to-test-the-application"></a>응용 프로그램을 테스트하려면

1.  F5 키를 누릅니다.

2.  Type 열의 값이 2인 레코드만 표시되는지 확인합니다.

3.  폼을 닫아 디버깅을 (에 **디버그** 메뉴를 클릭 하 여 **디버깅 중지**.)

## <a name="see-also"></a>참고자료

- [LINQ to SQL Tools in Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)(Visual Studio의 LINQ to SQL 도구)
- [연습: LINQ to SQL 클래스 (O R 디자이너) 만들기](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 합니다.](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [방법: Visual Basic 또는 C#에서 개체 모델 생성](/dotnet/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp)