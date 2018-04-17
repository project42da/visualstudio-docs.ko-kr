---
title: '연습: 서버의 통합 문서에 데이터를 삽입 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- datasets [Office development in Visual Studio], accessing on server
- server-side data access [Office development in Visual Studio]
- data [Office development in Visual Studio], accessing on server
- documents [Office development in Visual Studio], server-side data access
- workbooks [Office development in Visual Studio], inserting data
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7257094aa0fb29c1b03878f5ac39c3d4f4864022
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-inserting-data-into-a-workbook-on-a-server"></a>연습: 서버의 통합 문서에 데이터 삽입
  이 연습에서는 Microsoft Office Excel 통합 문서에 사용 하 여 Excel을 시작 하지 않고 캐시 된 데이터 집합에 데이터를 삽입 하는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스입니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   AdventureWorksLT 데이터베이스의 데이터가 포함 된 데이터 집합을 정의 합니다.  
  
-   Excel 통합 문서 프로젝트와 콘솔 응용 프로그램 프로젝트에서 데이터 집합의 인스턴스 만들기  
  
-   만들기는 <xref:Microsoft.Office.Tools.Excel.ListObject> 통합 문서에서 데이터 집합에 바인딩된 합니다.  
  
-   통합 문서의 데이터 캐시에 데이터 집합을 추가 합니다.  
  
-   Excel을 시작 하지 않고 콘솔 응용 프로그램에서 코드를 실행 하 여 캐시 된 데이터 집합에 데이터를 삽입 합니다.  
  
 이 연습에서는 개발 컴퓨터에서 코드를 실행 하는 가정 하지만이 연습에서 보여 주는 코드 Excel이 설치 되지 않은 서버에서 사용할 수 있습니다.  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 또는 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]  
  
-   AdventureWorksLT 샘플 데이터베이스가 연결 된 Microsoft SQL Server Express 또는 Microsoft SQL Server의 실행 중인 인스턴스 액세스 권한. AdventureWorksLT 데이터베이스를 다운로드할 수 있습니다는 [CodePlex 웹 사이트](http://go.microsoft.com/fwlink/?linkid=87843)합니다. 데이터베이스 연결에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
    -   SQL Server Management Studio 또는 SQL Server Management Studio Express를 사용하여 데이터베이스를 연결하려면 [방법: 데이터베이스 연결(SQL Server Management Studio)](http://msdn.microsoft.com/en-us/b4efb0ae-cfe6-4d81-a4b4-6e4916885caa)을 참조하세요.  
  
    -   명령줄을 사용하여 데이터베이스를 연결하려면 [방법: SQL Server Express에 데이터베이스 파일 연결](http://msdn.microsoft.com/en-us/0f8e42b5-7a8c-4c30-8c98-7d2bdc8dcc68)을 참조하세요.  
  
## <a name="creating-a-class-library-project-that-defines-a-dataset"></a>데이터 집합을 정의 하는 클래스 라이브러리 프로젝트 만들기  
 Excel 통합 문서 프로젝트와 콘솔 응용 프로그램에서 같은 데이터 집합을 사용 하려면 두 프로젝트 모두에 의해 참조 되는 별도 어셈블리에 데이터 집합을 정의 해야 합니다. 이 연습에서는 클래스 라이브러리 프로젝트에서 데이터 집합을 정의 합니다.  
  
#### <a name="to-create-the-class-library-project"></a>클래스 라이브러리 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
3.  템플릿 창에서 확장 **Visual C#** 또는 **Visual Basic**, 클릭 하 고 **Windows**합니다.  
  
4.  프로젝트 템플릿 목록에서 선택 **클래스 라이브러리**합니다.  
  
5.  에 **이름** 상자에서 입력 **AdventureWorksDataSet**합니다.  
  
6.  클릭 **찾아보기**, 해당 %UserProfile%\My 문서 (Windows XP 및 이전) 또는 %UserProfile%\Documents (Windows Vista)에 대 한 폴더를 탐색 하 고 클릭 **폴더 선택**합니다.  
  
7.  에 **새 프로젝트** 대화 상자에서 **솔루션용 디렉터리 만들기** 확인란을 선택 하지 않습니다.  
  
8.  **확인**을 클릭합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 추가 **AdventureWorksDataSet** 프로젝트를 **솔루션 탐색기** 열립니다는 **Class1.cs** 또는 **Class1.vb** 코드 파일.  
  
9. **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **Class1.cs** 또는 **Class1.vb**, 클릭 하 고 **삭제**합니다. 이 연습에 대 한이 파일이 필요가 없습니다.  
  
## <a name="defining-a-dataset-in-the-class-library-project"></a>클래스 라이브러리 프로젝트에서 데이터 집합 정의  
 SQL Server 2005 용 AdventureWorksLT 데이터베이스의 데이터를 포함 하는 형식화 된 데이터 집합을 정의 합니다. 이 연습의 뒷부분에서 Excel 통합 문서 프로젝트와 콘솔 응용 프로그램 프로젝트에서이 데이터 집합을 참조 하 게 됩니다.  
  
 데이터 집합은 한 *형식화 된 데이터 집합* AdventureWorksLT 데이터베이스의 Product 테이블의 데이터를 나타내는입니다. 형식화 된 데이터 집합에 대 한 자세한 내용은 참조 [Visual Studio의 데이터 집합 도구](/visualstudio/data-tools/dataset-tools-in-visual-studio)합니다.  
  
#### <a name="to-define-a-typed-dataset-in-the-class-library-project"></a>클래스 라이브러리 프로젝트에서 형식화 된 데이터 집합을 정의 하려면  
  
1.  **솔루션 탐색기**, 클릭는 **AdventureWorksDataSet** 프로젝트.  
  
2.  **데이터 소스** 창이 표시되지 않으면 메뉴 모음에서 **보기**, **다른 창**, **데이터 소스**를 차례로 선택하여 이를 표시합니다.  
  
3.  **새 데이터 소스 추가** 를 선택하여 **데이터 소스 구성 마법사**를 시작합니다.  
  
4.  **데이터베이스**를 클릭하고 **다음**을 클릭합니다.  
  
5.  AdventureWorksLT 데이터베이스에 기존 연결을 설정한 경우이 연결을 선택 하 고 클릭 **다음**합니다.  
  
     그렇지 않은 경우 **새 연결**을 클릭하고 **연결 추가** 대화 상자를 사용하여 새 연결을 만듭니다. 자세한 내용은 참조 [하는 방법: 데이터베이스의 데이터에 연결](../vsto/walkthrough-inserting-data-into-a-workbook-on-a-server.md)합니다.  
  
6.  **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지에서 **다음**을 클릭합니다.  
  
7.  에 **데이터베이스 개체 선택** 페이지 **테이블** 선택 **Product (SalesLT)**합니다.  
  
8.  **마침**을 클릭합니다.  
  
     AdventureWorksLTDataSet.xsd 파일이에 추가 되 고 **AdventureWorksDataSet** 프로젝트. 이 파일은 다음 항목을 정의합니다.  
  
    -   `AdventureWorksLTDataSet`라는 형식화된 데이터 집합 이 데이터 집합은 AdventureWorksLT 데이터베이스에서는 Product 테이블의 내용을 나타냅니다.  
  
    -   라는 TableAdapter `ProductTableAdapter`합니다. 데이터 읽기 및 쓰기에이 TableAdapter를 사용할 수는 `AdventureWorksLTDataSet`합니다. 자세한 내용은 [TableAdapter Overview](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview)을 참조하세요.  
  
     이 연습 뒷부분에서는 이러한 두 개체를 모두 사용합니다.  
  
9. **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **AdventureWorksDataSet** 클릭 **빌드**합니다.  
  
     프로젝트가 오류 없이 빌드되는지 확인합니다.  
  
## <a name="creating-an-excel-workbook-project"></a>Excel 통합 문서 프로젝트 만들기  
 데이터에 대 한 인터페이스에 대 한 Excel 통합 문서 프로젝트를 만듭니다. 이 연습의 뒷부분에서는 만들어집니다는 <xref:Microsoft.Office.Tools.Excel.ListObject> 데이터를 표시 하 고 통합 문서의 데이터 캐시에 데이터 집합의 인스턴스를 추가 합니다.  
  
#### <a name="to-create-the-excel-workbook-project"></a>Excel 통합 문서 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **AdventureWorksDataSet** 솔루션을 가리키고 **추가**, 클릭 하 고 **새 프로젝트**합니다.  
  
2.  템플릿 창에서 **Visual C#** 또는 **Visual Basic**을 확장한 다음 **Office/SharePoint**를 확장합니다.  
  
3.  확장된 **Office/SharePoint** 노드 아래에서 **Office 추가 기능** 노드를 선택합니다.  
  
4.  프로젝트 템플릿 목록에서 **Excel 2010 통합 문서** 또는 **Excel 2013 통합 문서** 프로젝트를 선택합니다.  
  
5.  에 **이름** 상자에서 입력 **AdventureWorksReport**합니다. 위치를 수정 하지 마십시오.  
  
6.  **확인**을 클릭합니다.  
  
     **Visual Studio Tools for Office 프로젝트 마법사** 가 열립니다.  
  
7.  되도록 **새 문서** 을 선택한 클릭 **확인**합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 열립니다는 **AdventureWorksReport** 디자이너에서 통합 문서 추가 **AdventureWorksReport** 프로젝트를 **솔루션 탐색기**합니다.  
  
## <a name="adding-the-dataset-to-data-sources-in-the-excel-workbook-project"></a>Excel 통합 문서 프로젝트에서 데이터 원본에 데이터 집합 추가  
 Excel 통합 문서에서 데이터 집합을 표시할 수 있습니다, 전에 Excel 통합 문서 프로젝트에서 데이터 원본에 데이터 집합을 먼저 추가 해야 합니다.  
  
#### <a name="to-add-the-dataset-to-the-data-sources-in-the-excel-workbook-project"></a>Excel 통합 문서 프로젝트에서 데이터 원본에는 데이터 집합을 추가 하려면  
  
1.  **솔루션 탐색기**를 두 번 클릭 **Sheet1.cs** 또는 **Sheet1.vb** 아래는 **AdventureWorksReport** 프로젝트.  
  
     디자이너에서 열립니다.  
  
2.  **데이터** 메뉴에서 **새 데이터 소스 추가**를 클릭합니다.  
  
     **데이터 소스 구성 마법사** 열립니다.  
  
3.  클릭 **개체**, 클릭 하 고 **다음**합니다.  
  
4.  에 **바인딩할 개체 선택** 페이지를 클릭 합니다. **참조 추가**합니다.  
  
5.  에 **프로젝트** 탭을 클릭 **AdventureWorksDataSet** 클릭 하 고 **확인**합니다.  
  
6.  아래는 **AdventureWorksDataSet** 의 네임 스페이스는 **AdventureWorksDataSet** 어셈블리를 클릭 하 여 **AdventureWorksLTDataSet** 클릭 하 고 **마침** .  
  
     **데이터 원본** 창이 열리고 및 **AdventureWorksLTDataSet** 데이터 원본의 목록에 추가 됩니다.  
  
## <a name="creating-a-listobject-that-is-bound-to-an-instance-of-the-dataset"></a>데이터 집합 인스턴스에 바인딩된 ListObject 만들기  
 통합 문서에서 데이터 집합을 표시 하려면 만듭니다는 <xref:Microsoft.Office.Tools.Excel.ListObject> 데이터 집합 인스턴스에 바인딩되어 있습니다. 데이터에 컨트롤을 바인딩하는 방법에 대한 자세한 내용은 [Binding Data to Controls in Office Solutions](../vsto/binding-data-to-controls-in-office-solutions.md)을 참조하세요.  
  
#### <a name="to-create-a-listobject-that-is-bound-to-an-instance-of-the-dataset"></a>데이터 집합 인스턴스에 바인딩된 ListObject를 만들려면  
  
1.  에 **데이터 원본** 창 확장는 **AdventureWorksLTDataSet** 노드 아래의 **AdventureWorksDataSet**합니다.  
  
2.  선택 된 **제품** 노드를 선택 하 고, 나타나는 드롭다운 화살표를 클릭 **ListObject** 드롭 다운 목록에서 합니다.  
  
     드롭다운 화살표 나타나지 않으면 통합 문서를 디자이너에서 열려 있는지 확인 합니다.  
  
3.  끌어서는 **제품** A1 셀에는 테이블입니다.  
  
     A <xref:Microsoft.Office.Tools.Excel.ListObject> 라는 컨트롤 `productListObject` A1 셀에 시작 하는 워크시트에 만들어집니다. 동시, 라는 dataset 개체 `adventureWorksLTDataSet` 및 <xref:System.Windows.Forms.BindingSource> 라는 `productBindingSource` 프로젝트에 추가 합니다. <xref:Microsoft.Office.Tools.Excel.ListObject> 가 <xref:System.Windows.Forms.BindingSource>에 바인딩된 다음 데이터 집합 개체에 바인딩됩니다.  
  
## <a name="adding-the-dataset-to-the-data-cache"></a>데이터 캐시에 데이터 집합 추가  
 통합 문서에서 데이터 집합에 액세스 하려면 Excel 통합 문서 프로젝트 외부에서 코드를 사용 하도록 설정 하려면 데이터 캐시에 데이터 집합을 추가 해야 합니다. 데이터 캐시에 대 한 자세한 내용은 참조 [문서 수준 사용자 지정의 캐시 된 데이터](../vsto/cached-data-in-document-level-customizations.md) 및 [데이터 캐싱](../vsto/caching-data.md)합니다.  
  
#### <a name="to-add-the-dataset-to-the-data-cache"></a>데이터 캐시에 데이터 집합을 추가 하려면  
  
1.  디자이너에서 클릭 **adventureWorksLTDataSet**합니다.  
  
2.  에 **속성** 창에서 설정 된 **한정자** 속성을 **공용**합니다.  
  
3.  설정의 **CacheInDocument** 속성을 **True**합니다.  
  
## <a name="checkpoint"></a>검사점  
 빌드 및 실행 Excel 통합 문서 프로젝트를 컴파일 및 오류 없이 실행 되는지 확인 하십시오.  
  
#### <a name="to-build-and-run-the-project"></a>프로젝트를 빌드하여 실행하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **AdventureWorksReport** 프로젝트 **디버그**, 클릭 하 고 **새 인스턴스 시작**합니다.  
  
     프로젝트는 만들어지고 통합 문서가 Excel에서 열립니다. <xref:Microsoft.Office.Tools.Excel.ListObject> 에 **Sheet1** 비어 때문에 `adventureWorksLTDataSet` 아직 데이터 캐시의 개체에 데이터가 없습니다. 다음 섹션을 사용 하 여 콘솔 응용 프로그램을 채우는 `adventureWorksLTDataSet` 데이터로 개체입니다.  
  
2.  Excel을 닫습니다. 변경 내용을 저장 하지 마십시오.  
  
## <a name="creating-a-console-application-project"></a>콘솔 응용 프로그램 프로젝트 만들기  
 통합 문서에서 캐시 된 데이터 집합에서 데이터를 삽입 하는 데는 콘솔 응용 프로그램 프로젝트를 만듭니다.  
  
#### <a name="to-create-the-console-application-project"></a>콘솔 응용 프로그램 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **AdventureWorksDataSet** 솔루션을 가리키고 **추가**, 클릭 하 고 **새 프로젝트**합니다.  
  
2.  에 **프로젝트 형식** 창 확장 **Visual C#** 또는 **Visual Basic**, 클릭 하 고 **Windows**합니다.  
  
3.  에 **템플릿** 창 선택 **콘솔 응용 프로그램**합니다.  
  
4.  에 **이름** 상자에서 입력 **DataWriter**합니다. 위치를 수정 하지 마십시오.  
  
5.  **확인**을 클릭합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 추가 **DataWriter** 프로젝트를 **솔루션 탐색기** 열립니다는 **Program.cs** 또는 **Module1.vb** 코드 파일.  
  
## <a name="adding-data-to-the-cached-dataset-by-using-the-console-application"></a>콘솔 응용 프로그램을 사용 하 여 캐시 된 데이터 집합에 데이터 추가  
 사용 하 여는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 데이터로 통합 문서에서 캐시 된 데이터 집합을 채우는 데 콘솔 응용 프로그램에서 클래스입니다.  
  
#### <a name="to-add-data-to-the-cached-dataset"></a>데이터 캐시 된 데이터 집합에 추가 하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **DataWriter** 프로젝트 **참조 추가**합니다.  
  
2.  에 **.NET** 탭에서 **Microsoft.VisualStudio.Tools.Applications.ServerDocument**합니다.  
  
3.  **확인**을 클릭합니다.  
  
4.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **DataWriter** 프로젝트 **참조 추가**합니다.  
  
5.  에 **프로젝트** 탭에서 **AdventureWorksDataSet**를 클릭 하 고 **확인**합니다.  
  
6.  코드 편집기에서 Program.cs 또는 Module1.vb 파일을 엽니다.  
  
7.  다음 추가 **를 사용 하 여** (에 대 한 C#) 또는 **Imports** (Visual Basic의 경우)에 대 한 코드 파일의 맨 위에 문을 합니다.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#1](../vsto/codesnippet/CSharp/AdventureWorksDataSet/DataWriter/Program.cs#1)]
     [!code-vb[Trin_CachedDataWalkthroughs#1](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/DataWriter/Module1.vb#1)]  
  
8.  `Main` 메서드에 다음 코드를 추가합니다. 이 코드는 다음과 같은 개체를 선언합니다.  
  
    -   인스턴스는 `AdventureWorksLTDataSet` 및 `ProductTableAdapter` 에 정의 된 형식에는 **AdventureWorksDataSet** 프로젝트.  
  
    -   빌드 폴더에서 AdventureWorksReport 통합 문서에 대 한 경로 **AdventureWorksReport** 프로젝트.  
  
    -   A <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 통합 문서의 데이터 캐시에 액세스 하는 데 사용할 개체입니다.  
  
        > [!NOTE]  
        >  다음 코드에서는 파일 확장명이.xlsx 통합 문서를 사용 하는 가정 합니다. 프로젝트의 통합 문서가 다른 파일 확장명을 필요에 따라 경로 수정 합니다.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#3](../vsto/codesnippet/CSharp/AdventureWorksDataSet/DataWriter/Program.cs#3)]
     [!code-vb[Trin_CachedDataWalkthroughs#3](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/DataWriter/Module1.vb#3)]  
  
9. 다음 코드를 추가 하 고 `Main` 이전 단계에서 추가한 코드 뒤의 메서드. 이 코드는 다음 작업을 수행합니다.  
  
    -   테이블 어댑터를 사용 하 여 형식화 된 dataset 개체를 채웁니다.  
  
    -   사용 하 여는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> 의 속성은 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 통합 문서에서 캐시 된 데이터 집합에 액세스 하는 클래스입니다.  
  
    -   사용 하 여는 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.SerializeDataInstance%2A> 로컬 형식화 된 데이터 집합의 데이터로 캐시 된 데이터 집합을 채우는 데 메서드.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#4](../vsto/codesnippet/CSharp/AdventureWorksDataSet/DataWriter/Program.cs#4)]
     [!code-vb[Trin_CachedDataWalkthroughs#4](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/DataWriter/Module1.vb#4)]  
  
10. **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **DataWriter** 프로젝트를 가리키도록 **디버그**, 클릭 하 고 **새 인스턴스 시작**합니다.  
  
     프로젝트는 만들어지고 콘솔 응용 프로그램 통합 문서에서 캐시 된 데이터 집합의 데이터를 저장 하는 응용 프로그램 및 로컬 데이터 집합을 채울 때 여러 가지 상태 메시지가 표시 됩니다. Enter 키를 눌러 응용 프로그램을 닫습니다.  
  
## <a name="testing-the-workbook"></a>통합 문서를 테스트합니다.  
 통합 문서를 열 때는 <xref:Microsoft.Office.Tools.Excel.ListObject> 이제 콘솔 응용 프로그램을 사용 하 여 캐시 된 데이터 집합에 추가 된 데이터가 표시 됩니다.  
  
#### <a name="to-test-the-workbook"></a>통합 문서를 테스트 하려면  
  
1.  계속 열려 있으면 Visual Studio 디자이너에서 AdventureWorksReport 통합 문서를 닫습니다.  
  
2.  파일 탐색기에서의 빌드 폴더에 있는 AdventureWorksReport 통합 문서를 열 여 **AdventureWorksReport** 프로젝트. 빌드 폴더는 기본적으로 다음 위치 중 하나에:  
  
    -   %UserProfile%\My Documents\AdventureWorksReport\bin\Debug (Windows XP 및 이전)  
  
    -   (Windows Vista)에 대 한 %UserProfile%\Documents\AdventureWorksReport\bin\Debug  
  
3.  되어 있는지 확인은 <xref:Microsoft.Office.Tools.Excel.ListObject> 통합 문서를 연 후 데이터로 채워집니다.  
  
## <a name="next-steps"></a>다음 단계  
 다음이 항목에서는 캐시 된 데이터를 사용 하는 방법에 대 한 자세히 알아볼 수 있습니다.  
  
-   Excel을 시작 하지 않고 캐시 된 데이터 집합의 데이터를 변경 합니다. 자세한 내용은 참조 [연습: 서버의 통합 문서에서 캐시 된 데이터 변경](../vsto/walkthrough-changing-cached-data-in-a-workbook-on-a-server.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 서버의 통합 문서에서 캐시 된 데이터 변경](../vsto/walkthrough-changing-cached-data-in-a-workbook-on-a-server.md)   
 [Windows Forms 응용 프로그램에서 데이터에 연결](/visualstudio/data-tools/connecting-to-data-in-windows-forms-applications)  
  
  