---
title: "연습: 문서 수준 프로젝트의 단순 데이터 바인딩"
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
  - "데이터[Visual Studio에서 Office 개발], 데이터 바인딩"
  - "데이터 바인딩[Visual Studio에서 Office 개발], 워크시트 셀을 데이터베이스 필드에"
  - "데이터베이스 필드[Visual Studio에서 Office 개발]"
  - "단순 데이터 바인딩[Visual Studio에서 Office 개발]"
  - "워크시트[Visual Studio에서 Office 개발], 워크시트 셀을 데이터베이스 필드에 바인딩"
ms.assetid: 6b8fd638-af13-4ea1-b1c0-2763e2d8ae23
caps.latest.revision: 58
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 57
---
# 연습: 문서 수준 프로젝트의 단순 데이터 바인딩
  이 연습에서는 문서 수준 프로젝트의 데이터 바인딩에 대한 기본적인 사항을 보여 줍니다.  SQL Server 데이터베이스의 데이터 필드 하나는 Microsoft Office Excel의 명명된 범위에 바인딩됩니다.  또한 이 연습에서는 표의 모든 레코드를 스크롤하는 데 사용할 수 있는 컨트롤을 추가하는 방법을 보여 줍니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   Excel 프로젝트의 데이터 소스 만들기  
  
-   워크시트에 컨트롤 추가  
  
-   데이터베이스 레코드 스크롤  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 또는 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]  
  
-   Northwind SQL Server 샘플 데이터베이스가 있는 서버에 액세스할 수 있어야 합니다.  
  
-   SQL Server 데이터베이스에서 읽고 쓰기 위한 권한이 있어야 합니다.  
  
## 새 프로젝트 만들기  
 이 단계에서는 Excel 통합 문서 프로젝트를 만듭니다.  
  
#### 새 프로젝트를 만들려면  
  
1.  Visual Basic이나 C\#을 사용하여 **My Simple Data Binding**이라는 Excel 통합 문서 프로젝트를 만듭니다.  **새 문서 만들기**가 선택되어 있는지 확인합니다.  자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하십시오.  
  
 Visual Studio의 디자이너에 새 Excel 통합 문서가 열리고 My Simple Data Binding 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
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
  
8.  **Customers** 테이블 옆에 있는 확인란을 선택합니다.  
  
9. **마침**을 클릭합니다.  
  
 마법사에서 **Customers** 테이블이 **데이터 소스** 창에 추가됩니다.  **솔루션 탐색기**에 표시되는 프로젝트에 형식화된 데이터 집합도 추가됩니다.  
  
## 워크시트에 컨트롤 추가  
 이 연습을 진행하려면 첫 번째 워크시트에 두 개의 명명된 범위와 네 개의 단추가 있어야 합니다.  먼저 **데이터 소스** 창에서 명명된 범위 두 개를 추가하여 데이터 소스에 이 범위를 자동으로 바인딩합니다.  그런 다음 **도구 상자**에서 단추를 추가합니다.  
  
#### 명명된 범위 두 개를 추가하려면  
  
1.  확인은  **내 간단한 데이터 Binding.xlsx** 통합 문서가 Visual Studio 디자이너에 열려 있는와  **Sheet1** 표시 합니다.  
  
2.  **데이터 소스** 창을 열고 **Customers** 노드를 확장합니다.  
  
3.  **CompanyName** 열을 선택한 다음 드롭다운 화살표가 나타나면 이를 클릭합니다.  
  
4.  드롭다운 목록에서 **NamedRange**를 선택하고 **CompanyName** 열을 셀 **A1**에 끌어 놓습니다.  
  
     `companyNameNamedRange`라는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤이 셀 **A1**에 작성됩니다.  이와 함께 `customersBindingSource`라는 <xref:System.Windows.Forms.BindingSource>, 테이블 어댑터 및 <xref:System.Data.DataSet> 인스턴스가 프로젝트에 추가됩니다.  컨트롤이 <xref:System.Windows.Forms.BindingSource>에 바인딩되고, 이는 다시 <xref:System.Data.DataSet> 인스턴스에 바인딩됩니다.  
  
5.  **데이터 소스** 창에서 **CustomerID** 열을 선택한 다음 드롭다운 화살표가 나타나면 이를 클릭합니다.  
  
6.  드롭다운 목록에서 **NamedRange**를 클릭하고 **CustomerID** 열을 셀 **B1**에 끌어 놓습니다.  
  
7.  `customerIDNamedRange`라는 다른 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤이 셀 **B1**에 작성되고 <xref:System.Windows.Forms.BindingSource>에 바인딩됩니다.  
  
#### 단추 네 개를 추가하려면  
  
1.  **도구 상자**의 **공용 컨트롤** 탭에서 <xref:System.Windows.Forms.Button> 컨트롤을 워크시트의 **A3** 셀에 추가합니다.  
  
     이 단추의 이름이 `Button1`로 설정됩니다.  
  
2.  나머지 세 개의 단추를 다음 셀에 아래 순서에 따라 추가하여 각 이름을 다음과 같이 설정합니다.  
  
    |셀|\(이름\)|  
    |-------|------------|  
    |B3|Button2|  
    |C3|Button3|  
    |D3|Button4|  
  
 다음 단계에서는 단추에 텍스트를 추가합니다. C\#의 경우 이벤트 처리기를 추가합니다.  
  
## 컨트롤 초기화  
 단추 텍스트를 설정하고 <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> 이벤트를 진행하는 동안 필요한 이벤트 처리기를 추가합니다.  
  
#### 컨트롤을 초기화하려면  
  
1.  **솔루션 탐색기**에서 마우스 오른쪽 단추로 **Sheet1.vb** 또는 **Sheet1.cs**를 클릭한 다음 바로 가기 메뉴에서 **코드 보기**를 클릭합니다.  
  
2.  `Sheet1_Startup` 메서드에 다음 코드를 추가하여 각 단추의 텍스트를 설정합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#2)]
     [!code-vb[Trin_VstcoreDataExcel#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#2)]  
  
3.  C\#의 경우 `Sheet1_Startup` 메서드에 단추 클릭 이벤트에 대한 이벤트 처리기를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#3)]  
  
 이제 사용자가 레코드를 탐색할 수 있도록 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트를 처리하는 코드를 추가합니다.  
  
## 레코드를 스크롤할 수 있도록 코드 추가  
 레코드에서 이동하기 위한 코드를 각 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 추가합니다.  
  
#### 첫 번째 레코드로 이동하려면  
  
1.  `Button1` 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 추가하고 다음 코드를 추가하여 첫 번째 레코드로 이동할 수 있도록 합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#4)]
     [!code-vb[Trin_VstcoreDataExcel#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#4)]  
  
#### 이전 레코드로 이동하려면  
  
1.  `Button2` 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 추가하고 다음 코드를 추가하여 하나 뒤의 위치로 이동할 수 있도록 합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#5)]
     [!code-vb[Trin_VstcoreDataExcel#5](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#5)]  
  
#### 다음 레코드로 이동하려면  
  
1.  `Button3` 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 추가하고 다음 코드를 추가하여 하나 앞의 위치로 이동할 수 있도록 합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#6](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#6)]
     [!code-vb[Trin_VstcoreDataExcel#6](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#6)]  
  
#### 마지막 레코드로 이동하려면  
  
1.  `Button4` 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 추가하고 다음 코드를 추가하여 마지막 레코드로 이동할 수 있도록 합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#7](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#7)]
     [!code-vb[Trin_VstcoreDataExcel#7](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#7)]  
  
## 응용 프로그램 테스트  
 이제 통합 문서를 테스트하여 데이터베이스의 레코드를 탐색할 수 있는지 확인합니다.  
  
#### 통합 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  **A1** 및 **B1** 셀에 첫 번째 레코드가 나타나는지 확인합니다.  
  
3.  **\>** \(`Button3`\) 단추를 클릭하고 **A1** 및 **B1** 셀에 다음 레코드가 나타나는지 확인합니다.  
  
4.  다른 스크롤 단추를 클릭하고 레코드가 원하는 대로 변경되는지 확인합니다.  
  
## 다음 단계  
 이 연습에서는 데이터베이스의 필드에 명명된 범위를 바인딩하는 기본적인 방법을 보여 줍니다.  다음에 수행할 수 있는 작업은 다음과 같습니다.  
  
-   오프라인으로 사용할 수 있도록 데이터를 캐시합니다.  자세한 내용은 [방법: 오프라인이나 서버에서 사용할 데이터 캐싱](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)을 참조하십시오.  
  
-   필드 하나가 아니라 테이블의 여러 필드에 셀을 바인딩합니다.  자세한 내용은 [연습: 문서 수준 프로젝트의 복합 데이터 바인딩](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md)을 참조하십시오.  
  
-   <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 사용하여 레코드를 스크롤합니다.  자세한 내용은 [방법: Windows Forms BindingNavigator 컨트롤을 사용하여 데이터 탐색](http://msdn.microsoft.com/library/0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb)을 참조하십시오.  
  
## 참고 항목  
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Office 솔루션의 데이터](../vsto/data-in-office-solutions.md)   
 [연습: 문서 수준 프로젝트의 복합 데이터 바인딩](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md)  
  
  