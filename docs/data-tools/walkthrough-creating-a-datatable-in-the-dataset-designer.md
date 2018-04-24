---
title: '연습: 데이터 집합 디자이너에서 DataTable 만들기'
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- DataTable objects, creating
- Dataset Designer, creating data tables
- tables [Visual Studio], creating
- data [Visual Studio], Dataset Designer
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: b5d359908a488e744a059f73a7ad058c249a6a40
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="walkthrough-creating-a-datatable-in-the-dataset-designer"></a>연습: 데이터 집합 디자이너에서 DataTable 만들기

이 연습을 만드는 방법을 설명는 <xref:System.Data.DataTable> (없이 TableAdapter)를 사용 하는 **데이터 집합 디자이너**합니다. Tableadapter를 포함 하는 데이터 테이블을 만드는 방법에 대 한 정보를 참조 하십시오. [만들기 및 Tableadapter를 구성](../data-tools/create-and-configure-tableadapters.md)합니다.

이 연습에서 설명하는 작업은 다음과 같습니다.

-   새 Windows Forms 응용 프로그램 프로젝트 만들기

-   응용 프로그램에 새 데이터 집합 추가

-   데이터 집합에 새 데이터 테이블을 추가합니다.

-   데이터 테이블에 열을 추가합니다.

-   테이블에 대 한 기본 키 설정

## <a name="creating-a-new-windows-forms-application"></a>새 Windows Forms 응용 프로그램 만들기

### <a name="to-create-a-new-windows-forms-application-project"></a>새 Windows Forms 응용 프로그램 프로젝트를 만들려면

1. Visual Studio에서에 **파일** 메뉴 선택 **새로**, **프로젝트...** .

2. 확장 **Visual C#** 또는 **Visual Basic** 왼쪽 창에서 선택 **클래식 Windows 데스크톱**합니다.

3. 가운데 창에서 선택 된 **Windows Forms 앱** 프로젝트 형식을 합니다.

4. 프로젝트 이름을 **DataTableWalkthrough**를 선택한 후 **확인**합니다.

     **DataTableWalkthrough** 프로젝트 생성 되며에 추가할 **솔루션 탐색기**합니다.

## <a name="adding-a-new-dataset-to-the-application"></a>응용 프로그램에 새 데이터 집합 추가

### <a name="to-add-a-new-dataset-item-to-the-project"></a>프로젝트에 새 데이터 집합 항목을 추가 하려면

1.  에 **프로젝트** 메뉴 선택 **새 항목 추가...** .

     새 항목 추가 대화 상자가 나타납니다.

2.  왼쪽 창에서 선택 **데이터**을 선택한 후 **DataSet** 가운데 창에서.

3.  **추가**를 선택합니다.

     라는 파일을 추가 하는 visual Studio **DataSet1.xsd** 프로젝트에서 엽니다는 **데이터 집합 디자이너**합니다.

## <a name="adding-a-new-datatable-to-the-dataset"></a>데이터 집합에 새 DataTable 추가

### <a name="to-add-a-new-data-table-to-the-dataset"></a>데이터 집합에 새 데이터 테이블을 추가 하려면

1.  끌어서는 **DataTable** 에서 **DataSet** 탭은 **도구 상자** 에 **데이터 집합 디자이너**합니다.

     라는 테이블 **DataTable1** 데이터 집합에 추가 됩니다.

2.  제목 표시줄을 클릭 **DataTable1** 하 고 이름을 `Music`합니다.

## <a name="adding-columns-to-the-datatable"></a>DataTable에 열 추가

### <a name="to-add-columns-to-the-datatable"></a>DataTable에 열을 추가 하려면

1.  마우스 오른쪽 단추로 클릭는 **음악** 테이블입니다. 가리킨 **추가**, 클릭 하 고 **열**합니다.

2.  열의 이름을 `SongID`합니다.

3.  에 **속성** 창에서 설정 된 <xref:System.Data.DataColumn.DataType%2A> 속성을 <xref:System.Int16?displayProperty=fullName>합니다.

4.  이 프로세스를 반복 하 고 다음 열을 추가 합니다.

     `SongTitle`: <xref:System.String?displayProperty=fullName>

     `Artist`: <xref:System.String?displayProperty=fullName>

     `Genre`: <xref:System.String?displayProperty=fullName>

## <a name="setting-the-primary-key-for-the-table"></a>테이블에 대 한 기본 키 설정

모든 데이터 테이블에 기본 키가 있어야 합니다. 기본 키 데이터 테이블에서 특정 레코드를 고유 하 게 식별합니다.

### <a name="to-set-the-primary-key-of-the-data-table"></a>데이터 테이블의 기본 키를 설정 하려면

-   마우스 오른쪽 단추로 클릭는 **SongID** 열을 마우스 클릭 한 다음 **기본 키 설정**합니다.

     열쇠 아이콘 옆에 표시 된 **SongID** 열입니다.

## <a name="saving-your-project"></a>프로젝트를 저장합니다.

### <a name="to-save-the-datatablewalkthrough-project"></a>DataTableWalkthrough 프로젝트를 저장 하려면

-   에 **파일** 메뉴를 클릭 하 여 **모두 저장**합니다.

## <a name="see-also"></a>참고자료

- [Visual Studio에서 데이터 집합 만들기 및 구성](../data-tools/create-and-configure-datasets-in-visual-studio.md)
- [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)
- [데이터 유효성 검사](../data-tools/validate-data-in-datasets.md)
- [데이터 저장](../data-tools/saving-data.md)