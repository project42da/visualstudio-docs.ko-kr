---
title: "연습: 서버의 통합 문서에서 캐시된 데이터 검색 | Microsoft Docs"
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
  - "데이터[Visual Studio에서 Office 개발], 서버에서 액세스"
  - "데이터 집합[Visual Studio에서 Office 개발], 서버에서 액세스"
  - "문서[Visual Studio에서 Office 개발], 서버 쪽 데이터 액세스"
  - "서버 쪽 데이터 액세스[Visual Studio에서 Office 개발]"
  - "통합 문서[Visual Studio에서 Office 개발], 데이터 검색"
ms.assetid: ef6d61e5-a498-4b38-8e2e-2e80706d854b
caps.latest.revision: 35
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 34
---
# 연습: 서버의 통합 문서에서 캐시된 데이터 검색
  이 연습에서는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스를 사용하여 Microsoft Office Excel을 시작하지 않고도 Excel 통합 문서에 캐시된 데이터 집합에서 데이터를 검색하는 방법을 보여 줍니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   AdventureWorksLT 데이터베이스에서 가져온 데이터를 포함하는 데이터 집합 정의  
  
-   Excel 통합 문서 프로젝트 및 콘솔 응용 프로그램 프로젝트에서 데이터 집합 인스턴스 만들기  
  
-   통합 문서의 데이터 집합에 바인딩된 <xref:Microsoft.Office.Tools.Excel.ListObject> 만들기 및 통합 문서가 열릴 때 <xref:Microsoft.Office.Tools.Excel.ListObject>에 데이터 채우기  
  
-   데이터 캐시에 통합 문서의 데이터 집합 추가  
  
-   Excel을 시작하지 않고 캐시된 데이터 집합의 데이터를 콘솔 응용 프로그램의 데이터 집합으로 읽어 들이기  
  
 이 연습에서는 개발 컴퓨터에서 코드를 실행하는 것으로 가정하지만 연습에서 소개하는 코드를 Excel이 설치되지 않은 서버에서 사용할 수도 있습니다.  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 또는 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]  
  
-   AdventureWorksLT 샘플 데이터베이스가 연결되어 있는 Microsoft SQL Server 또는 Microsoft SQL Server Express의 실행 중인 인스턴스에 대한 액세스 권한.  AdventureWorksLT 데이터베이스는 [CodePlex 웹 사이트](http://go.microsoft.com/fwlink/?linkid=87843)에서 다운로드할 수 있습니다.  데이터베이스 연결에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
    -   SQL Server Management Studio 또는 SQL Server Management Studio Express를 사용하여 데이터베이스를 연결하려면 [방법: 데이터베이스 연결\(SQL Server Management Studio\)](http://msdn.microsoft.com/ko-kr/b4efb0ae-cfe6-4d81-a4b4-6e4916885caa)을 참조하십시오.  
  
    -   명령줄을 사용하여 데이터베이스를 연결하려면 [방법: SQL Server Express에 데이터베이스 파일 첨부](http://msdn.microsoft.com/ko-kr/0f8e42b5-7a8c-4c30-8c98-7d2bdc8dcc68)를 참조하십시오.  
  
## 데이터 집합을 정의하는 클래스 라이브러리 프로젝트 만들기  
 Excel 통합 문서 프로젝트와 콘솔 응용 프로그램에서 같은 데이터 집합을 사용하려면 두 프로젝트에서 모두 참조되는 별도의 어셈블리에 데이터 집합을 정의해야 합니다.  이 연습에서는 클래스 라이브러리 프로젝트에서 데이터 집합을 정의합니다.  
  
#### 클래스 라이브러리 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
3.  템플릿 창에서 **Visual C\#** 또는 **Visual Basic**을 확장한 다음 **창**을 클릭합니다.  
  
4.  프로젝트 템플릿 목록에서 **클래스 라이브러리**를 선택합니다.  
  
5.  **이름** 상자에 **AdventureWorksDataSet**을 입력합니다.  
  
6.  **찾아보기**를 클릭하여 %UserProfile%\\My Documents\(Windows XP 또는 이전 버전의 경우\) 또는 %UserProfile%\\Documents\(Windows Vista의 경우\) 폴더로 이동한 다음 **폴더 선택**을 클릭합니다.  
  
7.  **새 프로젝트** 대화 상자에서 **솔루션용 디렉터리 만들기** 확인란이 선택되어 있지 않은지 확인합니다.  
  
8.  **확인**을 클릭합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 **솔루션 탐색기**에 **AdventureWorksDataSet** 프로젝트가 추가되고 **Class1.cs** 또는 **Class1.vb** 코드 파일이 열립니다.  
  
9. **솔루션 탐색기**에서 **Class1.cs** 또는 **Class1.vb**를 마우스 오른쪽 단추로 클릭한 다음 **삭제**를 클릭합니다.  이 연습에서는 이러한 파일이 필요하지 않습니다.  
  
## 클래스 라이브러리 프로젝트에서 데이터 집합 정의  
 SQL Server 2005의 AdventureWorksLT 데이터베이스에서 가져온 데이터를 포함하는 형식화된 데이터 집합을 정의합니다.  이 연습의 뒷부분에서는 Excel 통합 문서 프로젝트와 콘솔 응용 프로그램 프로젝트에서 이 데이터 집합을 참조하게 됩니다.  
  
 이 데이터 집합은 AdventureWorksLT 데이터베이스의 Product 테이블에 있는 데이터를 나타내는 *형식화된 데이터 집합*입니다.  형식화된 데이터 집합에 대한 자세한 내용은 [Visual Studio에서 데이터 집합 작업](../data-tools/dataset-tools-in-visual-studio.md)를 참조하십시오.  
  
#### 클래스 라이브러리 프로젝트에서 형식화된 데이터 집합을 정의하려면  
  
1.  **솔루션 탐색기**에서 **AdventureWorksDataSet** 프로젝트를 클릭합니다.  
  
2.  경우는  **데이터 원본** 창이 표시 되지 않는,이, 메뉴 표시줄에서 선택 표시  **보기**,  **기타 Windows**,  **데이터 원본**.  
  
3.  선택  **새 데이터 소스 추가** 시작 하는  **데이터 소스 구성 마법사**.  
  
4.  **데이터베이스**를 클릭하고 **다음**을 클릭합니다.  
  
5.  AdventureWorksLT 데이터베이스에 대한 기존 연결이 있으면 해당 연결을 선택하고 **다음**을 클릭합니다.  
  
     그렇지 않으면 **새 연결**을 클릭하고 **연결 추가** 대화 상자에서 새 연결을 만듭니다.  자세한 내용은 [방법: 데이터베이스의 데이터에 연결](../Topic/How%20to:%20Connect%20to%20Data%20in%20a%20Database.md)을 참조하십시오.  
  
6.  **Save the Connection String to the Application Configuration File** 페이지에서 **Next**을 클릭합니다.  
  
7.  **데이터베이스 개체 선택** 페이지에서 **테이블**을 확장한 다음 **Product \(SalesLT\)**를 선택합니다.  
  
8.  **마침**을 클릭합니다.  
  
     **AdventureWorksDataSet** 프로젝트에 AdventureWorksLTDataSet.xsd 파일이 추가됩니다.  이 파일은 다음 항목을 정의합니다.  
  
    -   이름이 `AdventureWorksLTDataSet`인 형식화된 데이터 집합.  이 데이터 집합은 AdventureWorksLT 데이터베이스의 Product 테이블에 있는 콘텐츠를 나타냅니다.  
  
    -   이름이 `ProductTableAdapter`인 TableAdapter.  이 TableAdapter는 `AdventureWorksLTDataSet`에서 데이터를 읽고 쓰는 데 사용할 수 있습니다.  자세한 내용은 [TableAdapter 개요](/visual-studio/data-tools/tableadapter-overview)을 참조하십시오.  
  
     이 연습의 뒷부분에서 이들 개체를 모두 사용하게 됩니다.  
  
9. **솔루션 탐색기**에서 **AdventureWorksDataSet**을 마우스 오른쪽 단추로 클릭하고 **빌드**를 클릭합니다.  
  
     프로젝트가 오류 없이 빌드되는지 확인합니다.  
  
## Excel 통합 문서 프로젝트 만들기  
 데이터에 대한 인터페이스를 구현하는 Excel 통합 문서 프로젝트를 만듭니다.  이 연습의 뒷부분에서 데이터를 표시하는 <xref:Microsoft.Office.Tools.Excel.ListObject>를 만들고 통합 문서의 데이터 캐시에 데이터 집합의 인스턴스를 추가하게 됩니다.  
  
#### Excel 통합 문서 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**에서 **AdventureWorksDataSet** 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **새 프로젝트**를 클릭합니다.  
  
2.  템플릿 창에서 확장  **C\#** 또는  **Visual Basic**를 차례로 확장 하 고  **Office\/SharePoint**.  
  
3.  아래 확장 된  **Office\/SharePoint** 노드를 선택 된  **Office 추가 기능** 노드.  
  
4.  프로젝트 템플릿 목록에서 선택 된  **Excel 2010 통합 문서** 또는  **통합 2013** 프로젝트.  
  
5.  **이름** 상자에 **AdventureWorksReport**를 입력합니다.  위치를 수정하지 마십시오.  
  
6.  **확인**을 클릭합니다.  
  
     **Visual Studio Tools for Office 프로젝트 마법사**가 열립니다.  
  
7.  **새 문서 만들기**를 선택하고 **확인**을 클릭합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]의 디자이너에서 **AdventureWorksReport** 통합 문서가 열리고 **솔루션 탐색기**에 **AdventureWorksReport** 프로젝트가 추가됩니다.  
  
## Excel 통합 문서 프로젝트의 데이터 소스에 데이터 집합 추가  
 Excel 통합 문서에 데이터 집합을 표시하려면 먼저 Excel 통합 문서 프로젝트의 데이터 소스에 데이터 집합을 추가해야 합니다.  
  
#### Excel 통합 문서 프로젝트의 데이터 소스에 데이터 집합을 추가하려면  
  
1.  **솔루션 탐색기**의 **AdventureWorksReport** 프로젝트에서 **Sheet1.cs** 또는 **Sheet1.vb**를 두 번 클릭합니다.  
  
     통합 문서가 디자이너에서 열립니다.  
  
2.  **데이터** 메뉴에서 **새 데이터 소스 추가**를 클릭합니다.  
  
     **데이터 소스 구성 마법사**가 열립니다.  
  
3.  **개체**를 클릭하고 **다음**을 클릭합니다.  
  
4.  **바인딩할 개체 선택** 페이지에서 **참조 추가**를 클릭합니다.  
  
5.  **프로젝트** 탭에서 **AdventureWorksDataSet**을 클릭한 다음 **확인**을 클릭합니다.  
  
6.  **AdventureWorksDataSet** 어셈블리의 **AdventureWorksDataSet** 네임스페이스에서 **AdventureWorksLTDataSet**을 클릭한 다음 **마침**을 클릭합니다.  
  
     **데이터 소스** 창이 열리고 데이터 소스 목록에 **AdventureWorksLTDataSet**이 추가됩니다.  
  
## 데이터 집합의 인스턴스에 바인딩된 ListObject 만들기  
 통합 문서에서 데이터 집합을 표시하려면 해당 데이터 집합의 인스턴스에 바인딩된 <xref:Microsoft.Office.Tools.Excel.ListObject>를 만듭니다.  컨트롤을 데이터에 바인딩하는 방법에 대한 자세한 내용은 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)을 참조하십시오.  
  
#### 데이터 집합의 인스턴스에 바인딩된 ListObject를 만들려면  
  
1.  **데이터 소스** 창의 **AdventureWorksDataSet**에서 **AdventureWorksLTDataSet** 노드를 확장합니다.  
  
2.  **Product** 노드를 선택하면 나타나는 드롭다운 화살표를 클릭하고 드롭다운 목록에서 **ListObject**를 선택합니다.  
  
     드롭다운 화살표가 표시되지 않으면 디자이너에 통합 문서가 열려 있는지 확인합니다.  
  
3.  **Product** 테이블을 A1 셀에 끌어 놓습니다.  
  
     `productListObject`라는 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤이 워크시트에 A1 셀부터 만들어집니다.  이와 함께 `adventureWorksLTDataSet`이라는 데이터 집합 개체와 `productBindingSource`라는 <xref:System.Windows.Forms.BindingSource>가 프로젝트에 추가됩니다.  <xref:Microsoft.Office.Tools.Excel.ListObject>가 <xref:System.Windows.Forms.BindingSource>에 바인딩되고, 이는 다시 데이터 집합 개체에 바인딩됩니다.  
  
## 데이터 캐시에 데이터 집합 추가  
 Excel 통합 문서 프로젝트의 외부에 있는 코드에서 통합 문서의 데이터 집합에 액세스할 수 있도록 하려면 데이터 집합을 데이터 캐시에 추가해야 합니다.  데이터 캐시에 대한 자세한 내용은 [문서 수준 사용자 지정의 캐시된 데이터](../vsto/cached-data-in-document-level-customizations.md) 및 [데이터 캐싱](../vsto/caching-data.md)을 참조하십시오.  
  
#### 데이터 캐시에 데이터 집합을 추가하려면  
  
1.  디자이너에서 **adventureWorksLTDataSet**을 클릭합니다.  
  
2.  **속성** 창에서 **Modifiers** 속성을 **Public**으로 설정합니다.  
  
3.  **CacheInDocument** 속성을 **True**로 설정합니다.  
  
## 통합 문서의 데이터 집합 초기화  
 콘솔 응용 프로그램을 사용하여 캐시된 데이터 집합에서 데이터를 검색하려면 먼저 캐시된 데이터 집합에 데이터를 채워야 합니다.  
  
#### 통합 문서의 데이터 집합을 초기화하려면  
  
1.  **솔루션 탐색기**에서 **Sheet1.cs** 또는 **Sheet1.vb** 파일을 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 클릭합니다.  
  
2.  `Sheet1_Startup` 이벤트 처리기를 다음 코드로 바꿉니다.  이 코드에서는 캐시된 데이터 집합이 현재 비어 있는 경우 **AdventureWorksDataSet** 프로젝트에 정의된 `ProductTableAdapter` 클래스의 인스턴스를 사용하여  에 이 데이터 집합에 데이터를 채웁니다.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#8](../snippets/csharp/VS_Snippets_OfficeSP/Trin_CachedDataWalkthroughs/CS/AdventureWorksReport/Sheet1.cs#8)]
     [!code-vb[Trin_CachedDataWalkthroughs#8](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_CachedDataWalkthroughs/VB/AdventureWorksReport/Sheet1.vb#8)]  
  
## 검사점  
 Excel 통합 문서 프로젝트를 빌드한 후 실행하여 오류 없이 컴파일 및 실행되는지 확인합니다.  또한 이 작업을 통해 캐시된 데이터 집합을 채우고 통합 문서에 데이터를 저장합니다.  
  
#### 프로젝트를 빌드하여 실행하려면  
  
1.  **솔루션 탐색기**에서 **AdventureWorksReport** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **디버그**를 선택한 다음 **새 인스턴스 시작**을 클릭합니다.  
  
     프로젝트가 빌드되고 Excel에서 통합 문서가 열립니다.  다음을 확인합니다.  
  
    -   <xref:Microsoft.Office.Tools.Excel.ListObject>에 데이터가 채워져 있는지 확인합니다.  
  
    -   <xref:Microsoft.Office.Tools.Excel.ListObject>의 첫 번째 행에 대한 **ListPrice** 열의 값이 1431.5인지 확인합니다.  이 연습의 뒷부분에서는 콘솔 응용 프로그램을 사용하여 **ListPrice** 열의 값을 수정하게 됩니다.  
  
2.  통합 문서를 저장합니다.  파일 이름이나 통합 문서의 위치를 수정하지 마십시오.  
  
3.  Excel을 닫습니다.  
  
## 콘솔 응용 프로그램 프로젝트 만들기  
 통합 문서의 캐시된 데이터 집합에 있는 데이터를 수정하는 데 사용할 콘솔 응용 프로그램 프로젝트를 만듭니다.  
  
#### 콘솔 응용 프로그램 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**에서 **AdventureWorksDataSet** 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **새 프로젝트**를 클릭합니다.  
  
2.  **프로젝트 형식** 창에서 **Visual C\#** 또는 **Visual Basic**을 확장한 다음 **Windows**를 클릭합니다.  
  
3.  **템플릿** 창에서 **콘솔 응용 프로그램**을 선택합니다.  
  
4.  **이름** 상자에 **DataReader**를 입력합니다.  위치를 수정하지 마십시오.  
  
5.  **확인**을 클릭합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 **솔루션 탐색기**에 **DataReader** 프로젝트가 추가되고 **Program.cs** 또는 **Module1.vb** 코드 파일이 열립니다.  
  
## 콘솔 응용 프로그램을 사용하여 캐시된 데이터 집합에서 데이터 검색  
 콘솔 응용 프로그램에서 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스를 사용하여 데이터를 로컬 `AdventureWorksLTDataSet` 개체로 읽어 들입니다.  로컬 데이터 집합이 캐시된 데이터 집합의 데이터로 초기화되었는지 확인하기 위해 응용 프로그램에서는 로컬 데이터 집합의 행 수를 표시합니다.  
  
#### 캐시된 데이터 집합에서 데이터를 검색하려면  
  
1.  **솔루션 탐색기**에서 **DataReader** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다.  
  
2.  에  **.NET** 탭에서 Microsoft.visualstudio.tools.applications.serverdocument를 선택 합니다.  
  
3.  **확인**을 클릭합니다.  
  
4.  **솔루션 탐색기**에서 **DataReader** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다.  
  
5.  **프로젝트** 탭에서 **AdventureWorksDataSet**을 선택하고 **확인**을 클릭합니다.  
  
6.  코드 편집기에서 Program.cs 또는 Module1.vb 파일을 엽니다.  
  
7.  코드 파일의 맨 위에 다음 **using**\(C\#의 경우\) 또는 **Imports**\(Visual Basic의 경우\) 문을 추가합니다.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_CachedDataWalkthroughs/CS/DataWriter/Program.cs#1)]
     [!code-vb[Trin_CachedDataWalkthroughs#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_CachedDataWalkthroughs/VB/DataWriter/Module1.vb#1)]  
  
8.  `Main` 메서드에 다음 코드를 추가합니다.  이 코드는 다음 개체를 선언합니다.  
  
    -   **AdventureWorksDataSet** 프로젝트에 정의된 `AdventureWorksLTDataSet` 형식의 인스턴스  
  
    -   **AdventureWorksReport** 프로젝트의 빌드 폴더에 있는 AdventureWorksReport 통합 문서의 경로  
  
    -   통합 문서의 데이터 캐시에 액세스하는 데 사용할 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 개체  
  
        > [!NOTE]  
        >  다음 코드에서는 .xlsx 확장명을 사용하여 통합 문서를 저장했다고 가정합니다.  프로젝트의 통합 문서가 다른 확장명을 사용하는 경우에는 경로를 필요한 대로 수정하십시오.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#10](../snippets/csharp/VS_Snippets_OfficeSP/Trin_CachedDataWalkthroughs/CS/DataWriter/Program.cs#10)]
     [!code-vb[Trin_CachedDataWalkthroughs#10](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_CachedDataWalkthroughs/VB/DataWriter/Module1.vb#10)]  
  
9. 이전 단계에서 추가한 코드 뒤에 있는 `Main` 메서드에 다음 코드를 추가합니다.  이 코드는 다음 작업을 수행합니다.  
  
    -   <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스의 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> 속성을 사용하여 통합 문서에서 캐시된 데이터 집합에 액세스합니다.  
  
    -   캐시된 데이터 집합의 데이터를 로컬 데이터 집합으로 읽어 들입니다.  
  
    -   로컬 데이터 집합의 행 수를 표시하여 데이터가 있는지 확인합니다.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#11](../snippets/csharp/VS_Snippets_OfficeSP/Trin_CachedDataWalkthroughs/CS/DataWriter/Program.cs#11)]
     [!code-vb[Trin_CachedDataWalkthroughs#11](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_CachedDataWalkthroughs/VB/DataWriter/Module1.vb#11)]  
  
10. **빌드** 메뉴에서 **DataReader 빌드**를 클릭합니다.  
  
## 프로젝트 테스트  
 콘솔 응용 프로그램을 실행하면 로컬 데이터 집합의 행 수가 표시됩니다.  
  
#### 통합 문서를 테스트하려면  
  
1.  **솔루션 탐색기**에서 **DataReader** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **디버그**를 가리킨 다음 **새 인스턴스 시작**을 클릭합니다.  
  
     응용 프로그램에서 로컬 데이터 집합의 행 수가 295개라고 보고하는지 확인합니다.  
  
2.  Enter 키를 눌러 응용 프로그램을 닫습니다.  
  
## 다음 단계  
 캐시된 데이터를 작업에 사용하는 방법에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   Excel을 시작하지 않고 캐시된 데이터 집합의 데이터 변경.  자세한 내용은 [연습: 서버의 통합 문서에서 캐시된 데이터 변경](../vsto/walkthrough-changing-cached-data-in-a-workbook-on-a-server.md)을 참조하십시오.  
  
## 참고 항목  
 [연습: 서버의 통합 문서에 데이터 삽입](../vsto/walkthrough-inserting-data-into-a-workbook-on-a-server.md)   
 [연습: 서버의 통합 문서에서 캐시된 데이터 변경](../vsto/walkthrough-changing-cached-data-in-a-workbook-on-a-server.md)   
 [Windows Forms 응용 프로그램에서 데이터에 연결](/visual-studio/data-tools/connecting-to-data-in-windows-forms-applications)  
  
  