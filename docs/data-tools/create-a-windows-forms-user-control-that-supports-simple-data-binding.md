---
title: 단순 데이터 바인딩을 지 원하는 사용자 정의 컨트롤 만들기
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom controls [Visual Studio], Data Sources Window
- Data Sources Window, controls
ms.assetid: b1488366-6dfb-454e-9751-f42fd3f3ddfb
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: a484388223b7dae62f165e13b2fc75368b0e642f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="create-a-windows-forms-user-control-that-supports-simple-data-binding"></a>단순 데이터 바인딩을 지 원하는 Windows Forms 사용자 정의 컨트롤 만들기
Windows 응용 프로그램에서 폼에 데이터를 표시할 때의 기존 컨트롤을 선택할 수 있습니다는 **도구 상자**, 하거나 응용 프로그램에 표준 컨트롤에서 사용할 수 없는 기능이 필요한 경우 사용자 지정 컨트롤을 제작할 수 있습니다. 이 연습에서는 <xref:System.ComponentModel.DefaultBindingPropertyAttribute>를 구현하는 컨트롤을 만드는 방법을 보여줍니다. <xref:System.ComponentModel.DefaultBindingPropertyAttribute>를 구현하는 컨트롤은 데이터에 바인딩할 수 있는 속성 한 개를 포함할 수 있습니다. 이러한 컨트롤은 <xref:System.Windows.Forms.TextBox> 또는 <xref:System.Windows.Forms.CheckBox>와 비슷합니다.

 컨트롤 제작에 대 한 자세한 내용은 참조 하십시오. [디자인 타임에 Windows Forms 컨트롤 개발](/dotnet/framework/winforms/controls/developing-windows-forms-controls-at-design-time)합니다.

 데이터 바인딩 시나리오에서 사용 하기 위해 컨트롤을 작성할 때 다음 데이터 바인딩 특성 중 하나를 구현 해야 합니다.

|데이터 바인딩 특성 사용|
|-----------------------------------|
|단일 데이터 열이나 속성을 표시하는 <xref:System.ComponentModel.DefaultBindingPropertyAttribute> 등의 단순 컨트롤에 대해 <xref:System.Windows.Forms.TextBox>를 구현합니다. 이 연습 페이지에서 해당 프로세스에 대해 설명합니다.|
|데이터 목록 또는 테이블을 표시하는 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> 등의 컨트롤에 대해 <xref:System.Windows.Forms.DataGridView>를 구현합니다. 자세한 내용은 참조 [복잡 한 데이터 바인딩을 지 원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md)합니다.|
|데이터 목록 또는 테이블을 표시하는 동시에 단일 열이나 속성도 제공해야 하는 <xref:System.ComponentModel.LookupBindingPropertiesAttribute> 등의 컨트롤에 대해 <xref:System.Windows.Forms.ComboBox>를 구현합니다. 자세한 내용은 참조 [조회 데이터 바인딩을 지 원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)합니다.|

 이 연습에서는 테이블 내 단일 열의 데이터를 표시하는 단순 컨트롤을 만듭니다. 이 예에서는 Northwind 샘플 데이터베이스 `Phone` 테이블의 `Customers` 열을 사용합니다. 간단한 사용자 정의 컨트롤 표준 전화 번호 형식으로 사용 하 여에 고객의 전화 번호를 표시 됩니다는 <xref:System.Windows.Forms.MaskedTextBox> 전화 번호에 마스크를 설정 하 고 있습니다.

 이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.

-   새 **Windows Forms 응용 프로그램**합니다.

-   새로 추가 **사용자 정의 컨트롤** 프로젝트에 있습니다.

-   사용자 컨트롤을 시각적으로 디자인합니다.

-   `DefaultBindingProperty` 특성을 구현합니다.

-   포함 된 데이터 집합 만들기는 **데이터 소스 구성** 마법사.

-   설정의 **전화** 열에는 **데이터 소스** 창 새 컨트롤을 사용 합니다.

-   새 컨트롤에 데이터를 표시할 폼을 만듭니다.

## <a name="prerequisites"></a>전제 조건
이 연습에서는 Northwind 샘플 데이터베이스 및 SQL Server Express LocalDB를 사용 합니다.

1.  SQL Server Express LocalDB가 없는 경우 설치에서 [SQL Server Express 다운로드 페이지](https://www.microsoft.com/sql-server/sql-server-editions-express), 또는 **Visual Studio 설치 관리자**합니다. Visual Studio 설치 관리자 SQL Server Express LocalDB의 일부로 설치할 수 있습니다는 **데이터 저장 및 처리** 작업 또는 개별 구성 요소입니다.

2.  다음 단계를 수행 하 여 Northwind 샘플 데이터베이스를 설치 합니다.

    1. Visual Studio에서 열고는 **SQL Server 개체 탐색기** 창. (SQL Server 개체 탐색기의 일부로 설치 되는 **데이터 저장 및 처리** Visual Studio 설치 관리자에서 작업 합니다.) 확장 된 **SQL Server** 노드. LocalDB 인스턴스를 마우스 오른쪽 단추로 클릭 하 고 선택 **새 쿼리 중...** .

       쿼리 편집기 창이 열립니다.

    2. 복사는 [Northwind Transact SQL 스크립트](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) 를 클립보드에 복사 합니다. 이 T-SQL 스크립트를 처음부터 Northwind 데이터베이스를 만들고 데이터로 채웁니다.

    3. 쿼리 편집기에 T-SQL 스크립트를 붙여 넣습니다.를 선택한 후는 **Execute** 단추입니다.

       짧은 시간 후 쿼리 실행이 완료 되 하 고 Northwind 데이터베이스 생성 됩니다.

## <a name="create-a-windows-forms-application"></a>Windows Forms 응용 프로그램 만들기
 첫 번째 단계를 만드는 것을 **Windows Forms 응용 프로그램**합니다.

#### <a name="to-create-the-new-windows-project"></a>새 Windows 프로젝트를 만들려면

1. Visual Studio에서에 **파일** 메뉴 선택 **새로**, **프로젝트...** .

2. 확장 **Visual C#** 또는 **Visual Basic** 왼쪽 창에서 선택 **클래식 Windows 데스크톱**합니다.

3. 가운데 창에서 선택 된 **Windows Forms 앱** 프로젝트 형식을 합니다.

4. 프로젝트 이름을 **SimpleControlWalkthrough**를 선택한 후 **확인**합니다.

     **SimpleControlWalkthrough** 프로젝트 생성 되며에 추가할 **솔루션 탐색기**합니다.

## <a name="add-a-user-control-to-the-project"></a>프로젝트에 사용자 컨트롤 추가
 이 연습에서 단순 데이터 바인딩 가능한 컨트롤을 만듭니다.는 **사용자 정의 컨트롤**, 추가 **사용자 정의 컨트롤** 항목의 **SimpleControlWalkthrough** 프로젝트.

#### <a name="to-add-a-user-control-to-the-project"></a>프로젝트에 사용자 컨트롤을 추가하려면

1.  **프로젝트** 메뉴 선택 **사용자 정의 컨트롤 추가**합니다.

2.  형식 `PhoneNumberBox` 이름 영역 및 클릭 **추가**합니다.

     **PhoneNumberBox** 에 컨트롤이 추가 되 **솔루션 탐색기**는 디자이너에서 열립니다.

## <a name="design-the-phonenumberbox-control"></a>PhoneNumberBox 컨트롤 디자인
 이 연습에서는 기존 <xref:System.Windows.Forms.MaskedTextBox>를 확장하여 `PhoneNumberBox` 컨트롤을 만듭니다.

#### <a name="to-design-the-phonenumberbox-control"></a>PhoneNumberBox 컨트롤을 디자인하려면

1.  끌어서는 <xref:System.Windows.Forms.MaskedTextBox> 에서 **도구 상자** 사용자 정의 컨트롤의 디자인 화면으로 합니다.

2.  스마트 태그를 선택는 <xref:System.Windows.Forms.MaskedTextBox> 방금 끌어왔습니다 및 선택 **마스크 설정**합니다.

3.  선택 **전화 번호** 에 **입력 마스크** 대화 상자와 클릭 **확인** 여 마스크를 설정 합니다.

## <a name="add-the-required-data-binding-attribute"></a>필수 데이터 바인딩 특성 추가
 데이터 바인딩을 지원하는 단순 컨트롤에 대해 <xref:System.ComponentModel.DefaultBindingPropertyAttribute>를 구현합니다.

#### <a name="to-implement-the-defaultbindingproperty-attribute"></a>DefaultBindingProperty 특성을 구현하려면

1.  `PhoneNumberBox` 컨트롤을 코드 보기로 전환합니다. (에 **보기** 메뉴 선택 **코드**.)

2.  `PhoneNumberBox`의 코드를 다음 코드로 바꿉니다.

     [!code-csharp[VbRaddataDisplaying#3](../data-tools/codesnippet/CSharp/create-a-windows-forms-user-control-that-supports-simple-data-binding_1.cs)]
     [!code-vb[VbRaddataDisplaying#3](../data-tools/codesnippet/VisualBasic/create-a-windows-forms-user-control-that-supports-simple-data-binding_1.vb)]

3.  **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.

## <a name="create-a-data-source-from-your-database"></a>데이터베이스에서 데이터 원본 만들기
 이 단계는 **데이터 소스 구성**마법사를 사용 하는 데이터 원본을 기반으로 `Customers` Northwind 샘플 데이터베이스의 테이블입니다. 연결을 만들려면 Northwind 샘플 데이터베이스에 액세스해야 합니다. Northwind 샘플 데이터베이스 설정에 대 한 자세한 내용은 참조 [하는 방법: 샘플 데이터베이스 설치](../data-tools/installing-database-systems-tools-and-samples.md)합니다.

#### <a name="to-create-the-data-source"></a>데이터 소스를 만들려면

1.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.

2.  에 **데이터 원본** 창에서 **새 데이터 소스 추가** 시작 하는 **데이터 소스 구성** 마법사.

3.  에 **데이터 소스 형식 선택** 페이지에서 **데이터베이스**, 클릭 하 고 **다음**합니다.

4.  에 **데이터 연결 선택** 페이지에서 다음 중 하나를 수행 합니다.

    -   Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.

    -   선택 **새 연결** 시작 하는 **연결 추가/수정** 대화 상자.

5.  데이터베이스에서 암호를 요구 하는 경우 중요 한 데이터를 포함 한 다음 클릭 옵션을 선택 **다음**합니다.

6.  에 **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지 **다음**합니다.

7.  에 **데이터베이스 개체 선택** 페이지는 **테이블** 노드.

8.  선택 된 `Customers` 테이블을 마우스 클릭 **마침**합니다.

     **NorthwindDataSet** 프로젝트에 추가 및 `Customers` 테이블에 표시는 **데이터 소스** 창.

## <a name="set-the-phone-column-to-use-the-phonenumberbox-control"></a>PhoneNumberBox 컨트롤을 사용 하도록 phone 열 설정
 내에서 **데이터 소스** 창에서 항목을 폼으로 끌기 전에 만들 컨트롤을 설정할 수 있습니다.

#### <a name="to-set-the-phone-column-to-bind-to-the-phonenumberbox-control"></a>PhoneNumberBox 컨트롤에 바인딩되도록 Phone 열을 설정하려면

1.  열기 **Form1** 디자이너에서 합니다.

2.  확장 된 **고객** 에서 노드는 **데이터 원본** 창.

3.  드롭다운 화살표를 클릭는 **고객** 노드를 선택 하 고 **세부 정보** 컨트롤 목록에서 합니다.

4.  드롭다운 화살표를 클릭는 **전화** 열을 선택 하 고 **사용자 지정**합니다.

5.  선택 된 **PhoneNumberBox** 목록에서 **연결 된 컨트롤** 에 **데이터 UI 사용자 지정 옵션** 대화 상자.

6.  드롭다운 화살표를 클릭는 **전화** 열을 선택 하 고 **PhoneNumberBox**합니다.

## <a name="add-controls-to-the-form"></a>폼에 컨트롤 추가
 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수 있습니다는 **데이터 소스** 창에서 폼으로 합니다.

#### <a name="to-create-data-bound-controls-on-the-form"></a>폼에서 데이터 바인딩된 컨트롤을 만들려면

-   주 끌어 **고객** 에서 노드는 **데이터 원본** 창에서 폼으로 있는지 확인 하 고는 `PhoneNumberBox` 컨트롤을 사용 하 여 데이터 표시는 `Phone` 열입니다.

     설명 레이블이 있는 데이터 바인딩된 컨트롤이 레코드 탐색을 위한 도구 모음인 <xref:System.Windows.Forms.BindingNavigator>와 함께 폼에 나타납니다. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), CustomersTableAdapter, <xref:System.Windows.Forms.BindingSource>, 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소 트레이에 나타납니다.

## <a name="run-the-application"></a>응용 프로그램 실행

#### <a name="to-run-the-application"></a>응용 프로그램을 실행하려면

-   F5 키를 눌러 응용 프로그램을 실행합니다.

## <a name="next-steps"></a>다음 단계
 응용 프로그램 요구 사항에 따라 데이터 바인딩을 지원하는 컨트롤을 만든 후 몇 단계를 더 수행해야 할 수도 있습니다. 일반적으로 수행하는 몇 가지 단계는 다음과 같습니다.

-   다른 응용 프로그램에서 다시 사용할 수 있도록 컨트롤 라이브러리에 사용자 지정 컨트롤을 배치합니다.

-   보다 복잡한 데이터 바인딩 시나리오를 지원하는 컨트롤을 만듭니다. 자세한 내용은 참조 [복잡 한 데이터 바인딩을 지 원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md) 및 [조회 데이터 바인딩을 지 원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)합니다.

## <a name="see-also"></a>참고 항목

- [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)