---
title: "연습: 문서 수준 프로젝트의 단순 데이터 바인딩 | Microsoft Docs"
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
- data binding [Office development in Visual Studio], worksheet cell to Database field
- worksheets [Office development in Visual Studio], binding worksheet cell to Database field
- Database field [Office development in Visual Studio]
- data [Office development in Visual Studio], binding data
- simple data binding [Office development in Visual Studio]
ms.assetid: 6b8fd638-af13-4ea1-b1c0-2763e2d8ae23
caps.latest.revision: "58"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 36053a8ef415e35f1244d0e379a49a46ea24f33d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-simple-data-binding-in-a-document-level-project"></a>연습: 문서 수준 프로젝트의 단순 데이터 바인딩
  이 연습에서는 문서 수준 프로젝트의 데이터 바인딩의 기본 사항을 보여 줍니다. SQL Server 데이터베이스의 단일 데이터 필드는 Microsoft Office Excel의 명명된 된 범위에 바인딩되어 있습니다. 이 연습에는 테이블의 모든 레코드를 스크롤할 수 있도록 하는 컨트롤을 추가 하는 방법을 보여 줍니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   Excel 프로젝트에 대 한 데이터 원본을 만드는 중입니다.  
  
-   워크시트에 컨트롤을 추가 합니다.  
  
-   데이터베이스 레코드 스크롤입니다.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 또는 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]  
  
-   Northwind SQL Server 예제 데이터베이스를 사용 하 여 서버에 액세스 합니다.  
  
-   사용 권한에서 읽기 / 쓰기를 SQL Server 데이터베이스입니다.  
  
## <a name="creating-a-new-project"></a>새 프로젝트 만들기  
 이 단계에서는 Excel 통합 문서 프로젝트를 만듭니다.  
  
#### <a name="to-create-a-new-project"></a>새 프로젝트를 만들려면  
  
1.  이름의 Excel 통합 문서 프로젝트를 만들 **단순 데이터 바인딩 내**, Visual Basic 또는 C#을 사용 하 여 합니다. 다음 사항을 확인 **새 문서** 을 선택 합니다. 자세한 내용은 [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하세요.  
  
 Visual Studio 디자이너에서 새 Excel 통합 문서를 열고 추가 된 **단순 데이터 바인딩 내** 프로젝트를 **솔루션 탐색기**합니다.  
  
## <a name="creating-the-data-source"></a>데이터 소스 만들기  
 **데이터 원본** 창을 사용하여 형식화된 데이터 집합을 프로젝트에 추가합니다.  
  
#### <a name="to-create-the-data-source"></a>데이터 소스를 만들려면  
  
1.  **데이터 소스** 창이 표시되지 않으면 메뉴 모음에서 **보기**, **다른 창**, **데이터 소스**를 차례로 선택하여 이를 표시합니다.  
  
2.  **새 데이터 소스 추가** 를 선택하여 **데이터 소스 구성 마법사**를 시작합니다.  
  
3.  선택 **데이터베이스** 클릭 하 고 **다음**합니다.  
  
4.  Northwind 샘플 SQL Server 데이터베이스에 데이터 연결을 선택 하거나 사용 하 여 새 연결 추가 **새 연결** 단추입니다.  
  
5.  연결을 선택 했거나 만든 후 클릭 **다음**합니다.  
  
6.  옵션을 선택 하는 경우 연결을 저장 하 고 클릭 한 다음의 선택을 취소 **다음**합니다.  
  
7.  확장 된 **테이블** 에서 노드는 **데이터베이스 개체** 창.  
  
8.  옆에 확인란을 선택 된 **고객** 테이블입니다.  
  
9. **마침**을 클릭합니다.  
  
 마법사에 추가 된 **고객** 테이블는 **데이터 원본** 창. 또한 형식화 된 데이터 집합에 표시 되는 프로젝트에 추가 **솔루션 탐색기**합니다.  
  
## <a name="adding-controls-to-the-worksheet"></a>워크시트에 컨트롤 추가  
 이 연습에서는 두 개의 명명 된 범위와 첫 번째 워크시트에 단추 4 개 필요합니다. 먼저에서 두 개의 명명 된 범위를 추가 **데이터 소스** 창 하는 데이터 원본에 자동 바인딩됩니다. 단추를 추가 하는 다음으로 **도구 상자**합니다.  
  
#### <a name="to-add-two-named-ranges"></a>두 개의 명명 된 범위를 추가 하려면  
  
1.  되어 있는지 확인는 **내 단순 데이터 Binding.xlsx** Visual Studio 디자이너에 통합 문서가 열려 있는 **Sheet1** 표시 합니다.  
  
2.  열기는 **데이터 원본** 창을 확장 하 고는 **고객** 노드.  
  
3.  선택은 **CompanyName** 열을 다음 표시 되는 드롭다운 화살표를 클릭 합니다.  
  
4.  선택 **NamedRange** 다음 끌어서 드롭 다운 목록에는 **CompanyName** 셀으로 열 **A1**합니다.  
  
     A <xref:Microsoft.Office.Tools.Excel.NamedRange> 라는 컨트롤 `companyNameNamedRange` 셀에 작성 **A1**합니다. 같은 시간에는 <xref:System.Windows.Forms.BindingSource> 라는 `customersBindingSource`, 테이블 어댑터 및 <xref:System.Data.DataSet> 인스턴스는 프로젝트에 추가 됩니다. 컨트롤이 바인딩되는 <xref:System.Windows.Forms.BindingSource>에 바인딩된 차례로 <xref:System.Data.DataSet> 인스턴스.  
  
5.  선택의 **CustomerID** 열에는 **데이터 원본** 창 다음 표시 되는 드롭다운 화살표를 클릭 합니다.  
  
6.  클릭 **NamedRange** 다음 끌어서 드롭 다운 목록에는 **CustomerID** 셀으로 열 **B1**합니다.  
  
7.  다른 <xref:Microsoft.Office.Tools.Excel.NamedRange> 라는 컨트롤 `customerIDNamedRange` 셀에 작성 **B1**에 바인딩되고는 <xref:System.Windows.Forms.BindingSource>합니다.  
  
#### <a name="to-add-four-buttons"></a>네 개의 단추를 추가 하려면  
  
1.  **공용 컨트롤** 탭은 **도구 상자**, 추가 <xref:System.Windows.Forms.Button> 컨트롤을 셀 **A3** 워크시트의 합니다.  
  
     이 단추 이름이 `Button1`합니다.  
  
2.  표시 된 것 처럼 이름이 되도록이 순서 대로 다음 셀에 나머지 세 개의 단추를 추가 합니다.  
  
    |셀|(이름)|  
    |----------|--------------|  
    |B3|Button2|  
    |C3|Button3|  
    |D3|Button4|  
  
 다음 단계를 단추, 텍스트를 추가 하 고 C#의 이벤트 처리기를 추가 하는 것입니다.  
  
## <a name="initializing-the-controls"></a>컨트롤을 초기화합니다.  
 단추 텍스트를 설정 하는 동안 이벤트 처리기를 추가 하 고는 <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> 이벤트입니다.  
  
#### <a name="to-initialize-the-controls"></a>컨트롤을 초기화 하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **Sheet1.vb** 또는 **Sheet1.cs**, 클릭 하 고 **코드 보기** 바로 가기 메뉴.  
  
2.  다음 코드를 추가 하는 `Sheet1_Startup` 각 단추에 대 한 텍스트를 설정 하는 메서드.  
  
     [!code-csharp[Trin_VstcoreDataExcel#2](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#2)]
     [!code-vb[Trin_VstcoreDataExcel#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#2)]  
  
3.  C#, click 이벤트를 단추에 대 한 이벤트 처리기를 추가 `Sheet1_Startup` 메서드.  
  
     [!code-csharp[Trin_VstcoreDataExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#3)]  
  
 이제 처리 하는 코드를 추가할는 <xref:System.Windows.Forms.Control.Click> 이벤트 단추의 사용자 레코드를 찾을 수 있도록 합니다.  
  
## <a name="adding-code-to-enable-scrolling-through-the-records"></a>레코드를 스크롤할 수 있도록 코드를 추가 합니다.  
 코드를 추가 하는 <xref:System.Windows.Forms.Control.Click> 레코드 간에 이동 하려면 각 단추의 이벤트 처리기입니다.  
  
#### <a name="to-move-to-the-first-record"></a>첫 번째 레코드로 이동 하려면  
  
1.  에 대 한 이벤트 처리기를 추가 <xref:System.Windows.Forms.Control.Click> 의 이벤트는 `Button1` 단추를 선택한 첫 번째 레코드로 이동 하려면 다음 코드를 추가 합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#4](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#4)]
     [!code-vb[Trin_VstcoreDataExcel#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#4)]  
  
#### <a name="to-move-to-the-previous-record"></a>이전 레코드로 이동 하려면  
  
1.  에 대 한 이벤트 처리기를 추가 <xref:System.Windows.Forms.Control.Click> 의 이벤트는 `Button2` 단추를 클릭 한 위치를 1 씩 다시 이동 하려면 다음 코드를 추가 합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#5)]
     [!code-vb[Trin_VstcoreDataExcel#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#5)]  
  
#### <a name="to-move-to-the-next-record"></a>다음 레코드로 이동 하려면  
  
1.  에 대 한 이벤트 처리기를 추가 <xref:System.Windows.Forms.Control.Click> 의 이벤트는 `Button3` 단추를 클릭 한 다음 코드 하나씩 이동 하는 위치를 추가 합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#6](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#6)]
     [!code-vb[Trin_VstcoreDataExcel#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#6)]  
  
#### <a name="to-move-to-the-last-record"></a>마지막 레코드를 이동 하려면  
  
1.  에 대 한 이벤트 처리기를 추가 <xref:System.Windows.Forms.Control.Click> 의 이벤트는 `Button4` 단추를 클릭 한 다음 코드 이동 마지막 레코드를 추가 합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#7](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#7)]
     [!code-vb[Trin_VstcoreDataExcel#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#7)]  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
 이제 통합 문서는 데이터베이스의 레코드를 찾아볼 수 있습니다를 테스트할 수 있습니다.  
  
#### <a name="to-test-your-workbook"></a>통합 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  첫 번째 레코드 셀에 나타나는지 확인 **A1** 및 **B1**합니다.  
  
3.  클릭는  **>**  (`Button3`) 단추를 선택한 다음 레코드 셀에 나타나는지 확인 **A1** 및 **B1**합니다.  
  
4.  예상 대로 레코드 변경 되는지 확인 하려면 다른 스크롤 단추를 클릭 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 연습에서는 명명된 된 범위는 데이터베이스의 필드에 바인딩하는 기본적인 보여 줍니다. 다음으로 수행할 수 있는 몇 가지 작업은 다음과 같습니다.  
  
-   오프 라인으로 사용할 수 있도록 데이터를 캐시 합니다. 자세한 내용은 참조 [하는 방법: 캐시 데이터는 서버 또는 오프 라인으로 사용에 대 한](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)합니다.  
  
-   한 필드를 대신 테이블의 여러 열에 셀을 바인딩하십시오. 자세한 내용은 참조 [연습: 문서 수준 프로젝트의 복합 데이터 바인딩](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md)합니다.  
  
-   사용 하 여 한 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 레코드를 스크롤합니다. 자세한 내용은 참조 [하는 방법: Windows Forms BindingNavigator 컨트롤을 사용 하 여 데이터 탐색](/dotnet/framework/winforms/controls/bindingnavigator-control-overview-windows-forms)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Office 솔루션의 데이터](../vsto/data-in-office-solutions.md)   
 [연습: 문서 수준 프로젝트의 복합 데이터 바인딩](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md)  
  
  