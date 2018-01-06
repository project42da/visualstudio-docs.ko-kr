---
title: "연습: 캐시 된 데이터 집합을 사용 하 여 마스터 세부 관계 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- master-detail tables [Office development in Visual Studio], walkthroughs
- data caching [Office development in Visual Studio], Master/Detail Relation
ms.assetid: 419f4e07-c67f-4fc9-973a-bc794f349ac3
caps.latest.revision: "41"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 124f4ca6450b5fe19bc707627dfed03e46307cff
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-master-detail-relation-using-a-cached-dataset"></a>연습: 캐시 된 데이터 집합을 사용 하 여 마스터 세부 관계 만들기
  이 연습에서는 워크시트에서 마스터/세부 관계를 만드는 솔루션을 오프 라인으로 사용할 수 있도록 데이터를 캐시 하는 방법을 보여 줍니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.  
  
-   워크시트에 컨트롤을 추가 합니다.  
  
-   데이터 집합 워크시트에 캐시를 설정 합니다.  
  
-   레코드를 스크롤할 수 있도록 코드를 추가 합니다.  
  
-   프로젝트를 테스트 합니다.  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 또는 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]  
  
-   Northwind SQL Server 예제 데이터베이스에 액세스 합니다. 데이터베이스 개발 컴퓨터 또는 서버 수 있습니다.  
  
-   사용 권한에서 읽기 / 쓰기를 SQL Server 데이터베이스입니다.  
  
## <a name="creating-a-new-project"></a>새 프로젝트 만들기  
 이 단계에서는 Excel 통합 문서 프로젝트를 만듭니다.  
  
#### <a name="to-create-a-new-project"></a>새 프로젝트를 만들려면  
  
1.  이름의 Excel 통합 문서 프로젝트를 만들 **내 마스터-세부**, Visual Basic 또는 C#을 사용 하 여 합니다. 다음 사항을 확인 **새 문서** 을 선택 합니다. 자세한 내용은 [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하세요.  
  
 Visual Studio 디자이너에서 새 Excel 통합 문서를 열고 추가 된 **내 마스터-세부** 프로젝트를 **솔루션 탐색기**합니다.  
  
## <a name="creating-the-data-source"></a>데이터 소스 만들기  
 **데이터 원본** 창을 사용하여 형식화된 데이터 집합을 프로젝트에 추가합니다.  
  
#### <a name="to-create-the-data-source"></a>데이터 소스를 만들려면  
  
1.  **데이터 소스** 창이 표시되지 않으면 메뉴 모음에서 **보기**, **다른 창**, **데이터 소스**를 차례로 선택하여 이를 표시합니다.  
  
2.  **새 데이터 소스 추가** 를 선택하여 **데이터 소스 구성 마법사**를 시작합니다.  
  
3.  선택 **데이터베이스** 클릭 하 고 **다음**합니다.  
  
4.  Northwind 샘플 SQL Server 데이터베이스에 데이터 연결을 선택 하거나 새 연결을 사용 하 여 추가 된 **새 연결** 단추입니다.  
  
5.  을 선택 하거나 연결을 만든 후 클릭 **다음**합니다.  
  
6.  옵션을 선택 하는 경우 연결을 저장 하 고 클릭 한 다음의 선택을 취소 **다음**합니다.  
  
7.  확장 된 **테이블** 에서 노드는 **데이터베이스 개체** 창.  
  
8.  선택 된 **Orders** 테이블 및 **Order Details** 테이블입니다.  
  
9. **마침**을 클릭합니다.  
  
 두 개의 테이블을 추가 하는 마법사는 **데이터 소스** 창. 또한 형식화 된 데이터 집합에 표시 되는 프로젝트에 추가 **솔루션 탐색기**합니다.  
  
## <a name="adding-controls-to-the-worksheet"></a>워크시트에 컨트롤 추가  
 이 단계에서는 첫 번째 워크시트의 명명된 된 범위, 목록 개체 및 두 개의 단추를 추가 합니다. 먼저 명명된 된 범위와 목록 개체를 추가 하는 **데이터 소스** 창 하는 데이터 원본에 자동 바인딩됩니다. 단추를 추가 하는 다음으로 **도구 상자**합니다.  
  
#### <a name="to-add-a-named-range-and-a-list-object"></a>명명된 된 범위와 목록 개체를 추가 하려면  
  
1.  되어 있는지 확인는 **내 마스터 Detail.xlsx** Visual Studio 디자이너에 통합 문서가 열려 있는 **Sheet1** 표시 합니다.  
  
2.  열기는 **데이터 원본** 창 확장는 **Orders** 노드.  
  
3.  선택은 **OrderID** 열을 다음 표시 되는 드롭다운 화살표를 클릭 합니다.  
  
4.  클릭 **NamedRange** 다음 끌어서 드롭 다운 목록에는 **OrderID** 셀으로 열 **A2**합니다.  
  
     A <xref:Microsoft.Office.Tools.Excel.NamedRange> 라는 컨트롤 `OrderIDNamedRange` 셀에 작성 **A2**합니다. 같은 시간에는 <xref:System.Windows.Forms.BindingSource> 라는 `OrdersBindingSource`, 테이블 어댑터 및 <xref:System.Data.DataSet> 인스턴스는 프로젝트에 추가 됩니다. 컨트롤이 바인딩되는 <xref:System.Windows.Forms.BindingSource>에 바인딩된 차례로 <xref:System.Data.DataSet> 인스턴스.  
  
5.  아래에 있는 열을 아래로 넘어가면는 **Orders** 테이블입니다. 목록의 맨 아래에는 **Order Details** ; 테이블의 자식 이기 때문에 여기는 **Orders** 테이블입니다. 이 옵션을 선택 **Order Details** 테이블을 동일한 수준으로 중이 아닌는 **Orders** 테이블을 선택한 다음 표시 되는 드롭다운 화살표를 클릭 합니다.  
  
6.  클릭 **ListObject** 다음 끌어서 드롭 다운 목록에는 **OrderDetails** 테이블 셀으로 **A6**합니다.  
  
7.  A <xref:Microsoft.Office.Tools.Excel.ListObject> 라는 컨트롤 **Order_DetailsListObject** 셀에 작성 **A6**에 바인딩되고는 <xref:System.Windows.Forms.BindingSource>합니다.  
  
#### <a name="to-add-two-buttons"></a>두 개의 단추를 추가 하려면  
  
1.  **공용 컨트롤** 탭은 **도구 상자**, 추가 <xref:System.Windows.Forms.Button> 컨트롤을 셀 **A3** 워크시트의 합니다.  
  
     이 단추 이름이 `Button1`합니다.  
  
2.  다른 항목 추가 <xref:System.Windows.Forms.Button> 컨트롤을 셀 **B3** 워크시트의 합니다.  
  
     이 단추 이름이 `Button2`합니다.  
  
 다음으로 문서에서 캐시를 매길 데이터 집합을 표시 합니다.  
  
## <a name="caching-the-dataset"></a>데이터 집합 캐싱  
 데이터 집합을 공개을 설정 하 여 문서에 캐시 되어야 데이터 집합 표시는 **CacheInDocument** 속성입니다.  
  
#### <a name="to-cache-the-dataset"></a>데이터 집합을 캐시 하려면  
  
1.  선택 **NorthwindDataSet** 구성 요소 트레이에 합니다.  
  
2.  에 **속성** 창에서 변경 된 **한정자** 속성을 **공용**합니다.  
  
     데이터 집합 캐싱을 활성화 하려면 공용 이어야 합니다.  
  
3.  변경 된 **CacheInDocument** 속성을 **True**합니다.  
  
 다음 단계를 단추, 텍스트를 추가 하 고 C#의 이벤트 처리기를 연결 하는 코드를 추가 하는 것입니다.  
  
## <a name="initializing-the-controls"></a>컨트롤을 초기화합니다.  
 단추 텍스트를 설정 하는 동안 이벤트 처리기를 추가 하 고는 <xref:Microsoft.Office.Tools.Excel.Workbook.Startup> 이벤트입니다.  
  
#### <a name="to-initialize-the-data-and-the-controls"></a>데이터 및 컨트롤을 초기화 하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **Sheet1.vb** 또는 **Sheet1.cs**, 클릭 하 고 **코드 보기** 바로 가기 메뉴.  
  
2.  다음 코드를 추가 하는 `Sheet1_Startup` 단추에 대 한 텍스트를 설정 하는 메서드.  
  
     [!code-vb[Trin_VstcoreDataExcel#15](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet2.vb#15)]
     [!code-csharp[Trin_VstcoreDataExcel#15](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet2.cs#15)]  
  
3.  C#, click 이벤트를 단추에 대 한 이벤트 처리기를 추가 `Sheet1_Startup` 메서드.  
  
     [!code-csharp[Trin_VstcoreDataExcel#16](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet2.cs#16)]  
  
## <a name="adding-code-to-enable-scrolling-through-the-records"></a>레코드를 스크롤할 수 있도록 코드를 추가 합니다.  
 코드를 추가 하는 <xref:System.Windows.Forms.Control.Click> 레코드 간에 이동 하려면 각 단추의 이벤트 처리기입니다.  
  
#### <a name="to-scroll-through-the-records"></a>레코드를 스크롤하려면  
  
1.  에 대 한 이벤트 처리기를 추가 <xref:System.Windows.Forms.Control.Click> 이벤트의 `Button1`, 레코드를 뒤로 이동 하려면 다음 코드를 추가 합니다.  
  
     [!code-vb[Trin_VstcoreDataExcel#17](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet2.vb#17)]
     [!code-csharp[Trin_VstcoreDataExcel#17](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet2.cs#17)]  
  
2.  에 대 한 이벤트 처리기를 추가 <xref:System.Windows.Forms.Control.Click> 이벤트의 `Button2`, 레코드를 진행 하려면 다음 코드를 추가 합니다.  
  
     [!code-vb[Trin_VstcoreDataExcel#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet2.vb#18)]
     [!code-csharp[Trin_VstcoreDataExcel#18](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet2.cs#18)]  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
 이제 데이터가 예상 대로 나타나는지 하 고 솔루션을 오프 라인으로 사용할 수 있는 통합 문서를 테스트할 수 있습니다.  
  
#### <a name="to-test-the-data-caching"></a>데이터 캐싱 테스트 하려면  
  
1.  **F5**키를 누릅니다.  
  
2.  명명 된 범위와 목록 개체는 데이터 원본의 데이터로 채워집니다 확인 합니다.  
  
3.  단추를 클릭 하 여 일부 레코드를 스크롤하십시오.  
  
4.  통합 문서를 저장 하 고 통합 문서 및 Visual Studio를 닫습니다.  
  
5.  데이터베이스에 연결을 사용 하지 않도록 설정 합니다. 데이터베이스는 서버에 있는 경우 컴퓨터에서 네트워크 케이블을 분리 하거나 데이터베이스가 개발 컴퓨터에 있으면 SQL Server 서비스를 중지 합니다.  
  
6.  Excel을 연 다음 **내 마스터 Detail.xlsx** (\My Master-Detail\bin Visual basic에서 또는 C#에서 \My Master-Detail\bin\debug) \bin 디렉터리의 합니다.  
  
7.  일부 끊기면 워크시트 정상적으로 작동을 확인할 레코드를 스크롤하십시오.  
  
8.  데이터베이스에 다시 연결 합니다. 컴퓨터 네트워크에 다시 연결 데이터베이스는 서버에 있는 경우 또는 데이터베이스가 개발 컴퓨터에 SQL Server 서비스를 시작 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 연습에서는 워크시트에서 마스터/세부 데이터 관계를 만드는 데이터 집합을 캐시 하는 기본적인 방법을 보여 줍니다. 다음으로 수행할 수 있는 몇 가지 작업은 다음과 같습니다.  
  
-   솔루션을 배포 합니다. 자세한 내용은 참조 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Office 솔루션의 데이터](../vsto/data-in-office-solutions.md)   
 [데이터 캐싱](../vsto/caching-data.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)  
  
  