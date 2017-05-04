---
title: "연습: 문서 수준 프로젝트의 복합 데이터 바인딩 | Microsoft Docs"
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
  - "복합 데이터[Visual Studio에서 Office 개발]"
  - "데이터[Visual Studio에서 Office 개발], 데이터 바인딩"
  - "데이터 바인딩[Visual Studio에서 Office 개발], 여러 열"
  - "여러 열 데이터 바인딩[Visual Studio에서 Office 개발]"
ms.assetid: 32ffad3d-fba4-476a-99b8-ef440434f4e1
caps.latest.revision: 50
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 49
---
# 연습: 문서 수준 프로젝트의 복합 데이터 바인딩
  이 연습에서는 문서 수준 프로젝트의 복합 데이터 바인딩에 대한 기본적인 사항을 보여 줍니다.  Microsoft Office Excel 워크시트의 여러 셀을 Northwind SQL Server 데이터베이스의 필드에 바인딩할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   통합 문서 프로젝트에 데이터 추가  
  
-   워크시트에 데이터 바인딩된 컨트롤 추가  
  
-   데이터 변경 내용을 데이터베이스에 다시 저장  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 또는 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]  
  
-   Northwind SQL Server 샘플 데이터베이스가 있는 서버에 액세스할 수 있어야 합니다.  
  
-   SQL Server 데이터베이스에서 읽고 쓰기 위한 권한이 있어야 합니다.  
  
## 새 프로젝트 만들기  
 첫 번째 단계는 Excel 통합 문서 프로젝트 만들기입니다.  
  
#### 새 프로젝트를 만들려면  
  
1.  **My Complex Data Binding**이라는 이름의 Excel 통합 문서 프로젝트를 만듭니다.  마법사에서 **새 문서 만들기**를 선택합니다.  
  
     자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하십시오.  
  
     Visual Studio의 디자이너에 새 Excel 통합 문서가 열리고 My Complex Data Binding 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
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
  
8.  **Employees** 테이블 옆에 있는 확인란을 선택합니다.  
  
9. **마침**을 클릭합니다.  
  
 마법사에서 **Employees** 테이블이 **데이터 소스** 창에 추가됩니다.  **솔루션 탐색기**에 표시되는 프로젝트에 형식화된 데이터 집합도 추가됩니다.  
  
## 워크시트에 컨트롤 추가  
 통합 문서가 열리면 워크시트에 **Employees** 테이블이 표시됩니다.  사용자는 데이터를 변경하고 단추를 클릭하여 해당 변경 내용을 다시 데이터베이스에 다시 저장할 수 있습니다.  
  
 워크시트를 테이블에 자동으로 바인딩하려면 **데이터 소스** 창에서 워크시트에 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤을 추가합니다.  사용자가 변경 내용을 저장할 수 있도록 하려면 **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 추가합니다.  
  
#### 목록 개체를 추가하려면  
  
1.  확인은  **내 복잡 한 데이터 Binding.xlsx** 통합 문서가 Visual Studio 디자이너에 열려 있는와  **Sheet1** 표시 합니다.  
  
2.  **데이터 소스** 창을 열고 **Employees** 노드를 선택합니다.  
  
3.  드롭다운 화살표가 나타나면 이 화살표를 클릭합니다.  
  
4.  드롭다운 목록에서 **ListObject**를 선택합니다.  
  
5.  **Employees** 테이블을 **A6** 셀에 끌어 놓습니다.  
  
     `EmployeesListObject`라는 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤이 셀 **A6**에 작성됩니다.  이와 함께 `EmployeesBindingSource`라는 <xref:System.Windows.Forms.BindingSource>, 테이블 어댑터 및 <xref:System.Data.DataSet> 인스턴스가 프로젝트에 추가됩니다.  컨트롤이 <xref:System.Windows.Forms.BindingSource>에 바인딩되고, 이는 다시 <xref:System.Data.DataSet> 인스턴스에 바인딩됩니다.  
  
#### 단추를 추가하려면  
  
1.  **도구 상자**의 **공용 컨트롤** 탭에서 <xref:System.Windows.Forms.Button> 컨트롤을 워크시트의 셀 **A4**에 추가합니다.  
  
 다음 단계에서는 워크시트가 열릴 때 단추에 텍스트를 추가합니다.  
  
## 컨트롤 초기화  
 <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> 이벤트 처리기에서 단추에 텍스트를 추가합니다.  
  
#### 컨트롤을 초기화하려면  
  
1.  **솔루션 탐색기**에서 마우스 오른쪽 단추로 **Sheet1.vb** 또는 **Sheet1.cs**를 클릭한 다음 바로 가기 메뉴에서 **코드 보기**를 클릭합니다.  
  
2.  `Sheet1_Startup` 메서드에 다음 코드를 추가하여 `button`의 텍스트를 설정합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#8](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet3.cs#8)]
     [!code-vb[Trin_VstcoreDataExcel#8](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet3.vb#8)]  
  
3.  C\#의 경우에만 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 `Sheet1_Startup` 메서드에 추가합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#9](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet3.cs#9)]  
  
 이제 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트를 처리할 코드를 추가합니다.  
  
## 데이터베이스에 변경 내용 저장  
 데이터에 대한 모든 변경 내용은 이를 데이터베이스에 다시 명시적으로 저장하지 않는 한 로컬 데이터 집합에만 적용됩니다.  
  
#### 데이터베이스에 변경 내용을 저장하려면  
  
1.  `button`의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 추가하고 다음 코드를 추가하여 데이터 집합의 모든 변경 내용을 데이터베이스에 다시 커밋할 수 있도록 합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#10](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet3.cs#10)]
     [!code-vb[Trin_VstcoreDataExcel#10](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet3.vb#10)]  
  
## 응용 프로그램 테스트  
 이제 통합 문서를 테스트하여 데이터가 예상대로 표시되는지 확인하고 목록 개체에서 데이터를 조작 가능한지 확인할 수 있습니다.  
  
#### 데이터 바인딩을 테스트하려면  
  
-   F5 키를 누릅니다.  
  
     통합 문서를 열 때 **Employees** 테이블의 데이터로 목록 개체가 채워지는지 확인합니다.  
  
#### 데이터를 수정하려면  
  
1.  셀 **B7**을 클릭합니다. 이 셀에는 **Davolio**라는 이름이 들어 있어야 합니다.  
  
2.  Anderson이라는 이름을 입력한 다음 Enter 키를 누릅니다.  
  
#### 열 머리글을 수정하려면  
  
1.  **LastName**이라는 열 머리글이 들어 있는 셀을 클릭합니다.  
  
2.  두 단어 사이에 공백을 추가하여 Last Name을 입력한 다음 Enter 키를 누릅니다.  
  
#### 데이터를 저장하려면  
  
1.  워크시트에서 **저장**을 클릭합니다.  
  
2.  Excel을 종료합니다.  변경 내용을 저장할지 묻는 메시지가 나타나면 **아니요**를 클릭합니다.  
  
3.  F5 키를 눌러 프로젝트를 다시 실행합니다.  
  
     목록 개체가 **Employees** 테이블의 데이터로 채워집니다.  
  
4.  셀 **B7**의 이름이 여전히 Anderson인 것을 확인할 수 있습니다. 이 이름은 이전에 변경하여 데이터베이스에 다시 저장한 데이터입니다.  열 머리글은 단어 사이에 공백이 없는 원래 형태인 **LastName**으로 다시 변경되었습니다. 열 머리글은 데이터베이스에 바인딩되어 있지 않고 워크시트에 대한 변경 내용을 저장하지 않았기 때문입니다.  
  
#### 새 행을 추가하려면  
  
1.  목록 개체 안의 셀을 선택합니다.  
  
     목록 아래쪽에 새 행이 나타나고 새 행의 첫 번째 셀에 별표\(**\***\)가 표시됩니다.  
  
2.  빈 행에 다음 정보를 입력합니다.  
  
    |EmployeeID|LastName|FirstName|제목|  
    |----------------|--------------|---------------|--------|  
    |10|Ito|Shu|Sales Manager|  
  
#### 행을 삭제하려면  
  
-   워크시트의 가장 왼쪽에 있는 번호 16\(16행\)을 마우스 오른쪽 단추로 클릭하고 **삭제**를 클릭합니다.  
  
#### 목록의 행을 정렬하려면  
  
1.  목록 안의 셀을 선택합니다.  
  
     각 열 머리글에 화살표 단추가 나타납니다.  
  
2.  **Last Name** 열 머리글의 화살표 단추를 클릭합니다.  
  
3.  **오름차순 정렬**을 클릭합니다.  
  
     각 행이 성을 기준으로 알파벳 순서에 따라 정렬됩니다.  
  
#### 정보를 필터링하려면  
  
1.  목록 안의 셀을 선택합니다.  
  
2.  **Title** 열 머리글의 화살표 단추를 클릭합니다.  
  
3.  **Sales Representative**를 클릭합니다.  
  
     **Title** 열에 **Sales Representative**가 있는 행만 목록에 표시됩니다.  
  
4.  **Title** 열 머리글의 화살표 단추를 다시 클릭합니다.  
  
5.  **\(모두\)**를 클릭합니다.  
  
     필터링이 제거되고 모든 행이 나타납니다.  
  
## 다음 단계  
 이 연습에서는 데이터베이스의 테이블을 목록 개체에 바인딩하는 기본적인 방법을 보여 줍니다.  다음에 수행할 수 있는 작업은 다음과 같습니다.  
  
-   오프라인으로 사용할 수 있도록 데이터를 캐시합니다.  자세한 내용은 [방법: 오프라인이나 서버에서 사용할 데이터 캐싱](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)을 참조하십시오.  
  
-   솔루션을 배포합니다.  자세한 내용은 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)을 참조하십시오.  
  
-   필드와 테이블 사이에 마스터\/세부 항목 관계를 만듭니다.  자세한 내용은 [연습: 캐시된 데이터 집합을 사용하여 마스터-세부 관계 만들기](../vsto/walkthrough-creating-a-master-detail-relation-using-a-cached-dataset.md)을 참조하십시오.  
  
## 참고 항목  
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Office 솔루션의 데이터](../vsto/data-in-office-solutions.md)   
 [연습: 문서 수준 프로젝트의 단순 데이터 바인딩](../vsto/walkthrough-simple-data-binding-in-a-document-level-project.md)  
  
  