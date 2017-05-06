---
title: "연습: 캐시된 데이터 집합을 사용하여 마스터-세부 관계 만들기"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "데이터 캐싱[Visual Studio에서 Office 개발], 마스터/세부 관계"
  - "마스터-세부 테이블[Visual Studio에서 Office 개발], 연습"
ms.assetid: 419f4e07-c67f-4fc9-973a-bc794f349ac3
caps.latest.revision: 41
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 40
---
# 연습: 캐시된 데이터 집합을 사용하여 마스터-세부 관계 만들기
  이 연습에서는 워크시트에서 마스터\/세부 관계를 만드는 방법을 보여 주고 솔루션을 오프라인으로 사용할 수 있도록 데이터를 캐시하는 방법을 보여 줍니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 이 연습을 통해 다음과 같은 작업 방법을 배웁니다.  
  
-   워크시트에 컨트롤 추가  
  
-   워크시트에서 캐시할 데이터 집합 설정  
  
-   레코드를 스크롤할 수 있도록 코드 추가  
  
-   프로젝트 테스트  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 또는 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]  
  
-   Northwind SQL Server 샘플 데이터베이스에 대한 액세스 권한.  데이터베이스는 개발 컴퓨터 또는 서버에 있을 수 있습니다.  
  
-   SQL Server 데이터베이스에서 읽고 쓰기 위한 권한이 있어야 합니다.  
  
## 새 프로젝트 만들기  
 이 단계에서는 Excel 통합 문서 프로젝트를 만듭니다.  
  
#### 새 프로젝트를 만들려면  
  
1.  Visual Basic이나 C\#을 사용하여 **My Master\-Detail**이라는 Excel 통합 문서 프로젝트를 만듭니다.  **새 문서 만들기**가 선택되어 있는지 확인합니다.  자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하십시오.  
  
 Visual Studio의 디자이너에 새 Excel 통합 문서가 열리고 My Master\-Detail 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
## 데이터 소스 만들기  
 **데이터 소스** 창을 사용하여 형식화된 데이터 집합을 프로젝트에 추가합니다.  
  
#### 데이터 소스 만들기  
  
1.  경우는  **데이터 원본** 창이 표시 되지 않는,이, 메뉴 표시줄에서 선택 표시  **보기**,  **기타 Windows**,  **데이터 원본**.  
  
2.  선택  **새 데이터 소스 추가** 시작 하는  **데이터 소스 구성 마법사**.  
  
3.  **데이터베이스**를 선택하고 **다음**을 클릭합니다.  
  
4.  Northwind 샘플 SQL Server 데이터베이스에 대한 데이터 연결을 선택하거나 **새 연결** 단추를 사용하여 새 연결을 추가합니다.  
  
5.  연결을 선택하거나 만든 후 **다음**을 클릭합니다.  
  
6.  연결을 저장하는 옵션이 선택되어 있는 경우 선택을 취소하고 **다음**을 클릭합니다.  
  
7.  **데이터베이스 개체** 창에서 **테이블** 노드를 확장합니다.  
  
8.  **Orders** 테이블과 **Order Details** 테이블을 선택합니다.  
  
9. **마침**을 클릭합니다.  
  
 마법사에서 두 테이블이 **데이터 소스** 창에 추가됩니다.  **솔루션 탐색기**에 표시되는 프로젝트에 형식화된 데이터 집합도 추가됩니다.  
  
## 워크시트에 컨트롤 추가  
 이 단계에서는 명명된 범위, 목록 개체 및 두 개의 단추를 첫 번째 워크시트에 추가합니다.  먼저 **데이터 소스** 창에서 명명된 범위와 목록 개체를 추가하여 데이터 소스에 이를 자동으로 바인딩합니다.  그런 다음 **도구 상자**에서 단추를 추가합니다.  
  
#### 명명된 범위와 목록 개체를 추가하려면  
  
1.  확인은  **내 마스터 Detail.xlsx** 통합 문서가 Visual Studio 디자이너에 열려 있는와  **Sheet1** 표시 합니다.  
  
2.  **데이터 소스** 창을 열고 **Orders** 노드를 확장합니다.  
  
3.  **OrderID** 열을 선택한 다음 드롭다운 화살표가 나타나면 이를 클릭합니다.  
  
4.  드롭다운 목록에서 **NamedRange**를 클릭하고 **OrderID** 열을 **A2** 셀에 끌어 놓습니다.  
  
     `OrderIDNamedRange`라는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤이 **A2** 셀에 작성됩니다.  이와 함께 `OrdersBindingSource`라는 <xref:System.Windows.Forms.BindingSource>, 테이블 어댑터 및 <xref:System.Data.DataSet> 인스턴스가 프로젝트에 추가됩니다.  컨트롤이 <xref:System.Windows.Forms.BindingSource>에 바인딩되고, 이는 다시 <xref:System.Data.DataSet> 인스턴스에 바인딩됩니다.  
  
5.  **Orders** 테이블 아래의 열 밑으로 스크롤합니다.  목록 아래쪽에 **Order Details** 테이블이 있습니다. 이 테이블은 **Orders** 테이블의 자식이기 때문에 이와 같은 위치에 있습니다.  **Orders** 테이블과 동일한 수준에 있는 테이블이 아닌 이 **Order Details** 테이블을 선택한 다음 드롭다운 화살표를 클릭합니다.  
  
6.  드롭다운 목록에서 **ListObject**를 클릭하고 **OrderDetails** 테이블을 **A6** 셀에 끌어 놓습니다.  
  
7.  **Order\_DetailsListObject**라는 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤이 **A6** 셀에 작성되고 <xref:System.Windows.Forms.BindingSource>에 바인딩됩니다.  
  
#### 단추 두 개를 추가하려면  
  
1.  **도구 상자**의 **공용 컨트롤** 탭에서 <xref:System.Windows.Forms.Button> 컨트롤을 워크시트의 **A3** 셀에 추가합니다.  
  
     이 단추의 이름이 `Button1`로 설정됩니다.  
  
2.  다른 <xref:System.Windows.Forms.Button> 컨트롤을 워크시트의 **B3** 셀에 추가합니다.  
  
     이 단추의 이름이 `Button2`로 설정됩니다.  
  
 이제 문서에서 캐시할 데이터 집합을 표시합니다.  
  
## 데이터 집합 캐싱  
 데이터 집합을 공용으로 표시하고 **CacheInDocument** 속성을 설정하여 문서에서 캐시할 데이터 집합을 표시합니다.  
  
#### 데이터 집합을 캐시하려면  
  
1.  구성 요소 트레이에서 **NorthwindDataSet**를 선택합니다.  
  
2.  **속성** 창에서 **Modifiers** 속성을 **Public**으로 변경합니다.  
  
     캐싱을 활성화하려면 데이터 집합이 공용이어야 합니다.  
  
3.  **CacheInDocument** 속성을 **True**로 변경합니다.  
  
 다음 단계에서는 단추에 텍스트를 추가합니다. C\#의 경우 이벤트 처리기에 후크하는 코드도 추가합니다.  
  
## 컨트롤 초기화  
 단추 텍스트를 설정하고 <xref:Microsoft.Office.Tools.Excel.Workbook.Startup> 이벤트 발생 시 사용할 이벤트 처리기를 추가합니다.  
  
#### 데이터와 컨트롤을 초기화하려면  
  
1.  **솔루션 탐색기**에서 마우스 오른쪽 단추로 **Sheet1.vb** 또는 **Sheet1.cs**를 클릭한 다음 바로 가기 메뉴에서 **코드 보기**를 클릭합니다.  
  
2.  `Sheet1_Startup` 메서드에 다음 코드를 추가하여 단추의 텍스트를 설정합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#15](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet2.cs#15)]
     [!code-vb[Trin_VstcoreDataExcel#15](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet2.vb#15)]  
  
3.  C\#의 경우 `Sheet1_Startup` 메서드에 단추 클릭 이벤트에 대한 이벤트 처리기를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#16](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet2.cs#16)]  
  
## 레코드를 스크롤할 수 있도록 코드 추가  
 레코드에서 이동하기 위한 코드를 각 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 추가합니다.  
  
#### 레코드를 스크롤하려면  
  
1.  `Button1`의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 추가하고 다음 코드를 추가하여 레코드에서 뒤로 이동할 수 있도록 합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#17](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet2.cs#17)]
     [!code-vb[Trin_VstcoreDataExcel#17](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet2.vb#17)]  
  
2.  `Button2`의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 추가하고 다음 코드를 추가하여 레코드에서 앞으로 이동할 수 있도록 합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#18](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet2.cs#18)]
     [!code-vb[Trin_VstcoreDataExcel#18](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet2.vb#18)]  
  
## 응용 프로그램 테스트  
 이제 통합 문서를 테스트하여 데이터가 예상대로 표시되는지 확인하고 솔루션을 오프라인으로 사용할 수 있는지 확인합니다.  
  
#### 데이터 캐싱을 테스트하려면  
  
1.  **F5** 키를 누릅니다.  
  
2.  명명된 범위와 목록 개체가 데이터 소스의 데이터로 채워지는지 확인합니다.  
  
3.  단추를 클릭하여 레코드 일부를 스크롤합니다.  
  
4.  통합 문서를 저장한 다음 통합 문서와 Visual Studio를 닫습니다.  
  
5.  데이터베이스에 대한 연결을 해제합니다.  데이터베이스가 서버에 있는 경우 네트워크 케이블을 컴퓨터에서 분리하고, 데이터베이스가 개발 컴퓨터에 있는 경우 SQL Server 서비스를 중지합니다.  
  
6.  Excel을 연 다음  **내 마스터 Detail.xlsx** \\bin 디렉터리 \(Visual Basic \\My Master\-Detail\\bin 또는 \\my master\-detail\\bin\\debug에서 C\#\).  
  
7.  레코드 일부를 스크롤하여 네트워크가 연결되지 않은 상태에서도 워크시트가 올바르게 작동하는지 확인합니다.  
  
8.  데이터베이스에 다시 연결합니다.  데이터베이스가 서버에 있는 경우 컴퓨터를 네트워크에 다시 연결하고, 데이터베이스가 개발 컴퓨터에 있는 경우 SQL Server 서비스를 시작합니다.  
  
## 다음 단계  
 이 연습에서는 워크시트에 마스터\/세부 데이터 관계를 만들고 데이터 집합을 캐시하는 기본적인 방법을 보여 줍니다.  다음에 수행할 수 있는 작업은 다음과 같습니다.  
  
-   솔루션을 배포합니다.  자세한 내용은 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)를 참조하십시오.  
  
## 참고 항목  
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Office 솔루션의 데이터](../vsto/data-in-office-solutions.md)   
 [데이터 캐싱](../vsto/caching-data.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)  
  
  