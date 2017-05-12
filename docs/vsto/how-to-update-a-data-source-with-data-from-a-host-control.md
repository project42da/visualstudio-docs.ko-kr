---
title: "방법: Host 컨트롤의 데이터로 데이터 원본 업데이트"
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
  - "문서[Visual Studio에서 Office 개발], 데이터 원본 업데이트"
  - "데이터[Visual Studio에서 Office 개발], 문서에서 데이터 원본 업데이트"
  - "호스트 컨트롤[Visual Studio에서 Office 개발], 데이터 원본 업데이트"
  - "Office 문서[Visual Studio에서 Office 개발], 데이터 원본"
ms.assetid: b91025af-1eaa-44ee-88f2-71ecaa7a0440
caps.latest.revision: 53
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 52
---
# 방법: Host 컨트롤의 데이터로 데이터 원본 업데이트
  호스트 컨트롤을 데이터 원본에 바인딩하고 해당 데이터 원본을 컨트롤에 있는 데이터의 변경 내용으로 업데이트할 수 있습니다. 이 프로세스는 크게 다음과 같은 두 가지 단계로 구성되어 있습니다.  
  
1.  컨트롤에 있는 수정된 데이터로 메모리 내 데이터 원본을 업데이트합니다. 일반적으로 메모리 내 데이터 원본은 <xref:System.Data.DataSet>, <xref:System.Data.DataTable> 또는 일부 다른 데이터 개체입니다.  
  
2.  데이터베이스를 메모리 내 데이터 원본의 변경된 데이터로 업데이트합니다. 이 작업은 데이터 원본이 SQL Server 또는 Microsoft Office Access 데이터베이스와 같이 백 엔드 데이터베이스에 연결된 경우에만 가능합니다.  
  
 호스트 컨트롤 및 데이터 바인딩에 대한 자세한 내용은 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md) 및 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)을 참조하세요.  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
## 메모리 내 데이터 원본 업데이트  
 기본적으로 단순 데이터 바인딩\(Word 문서의 콘텐츠 컨트롤 또는 Excel 워크시트의 명명된 범위 컨트롤 등\)을 사용하도록 설정된 호스트 컨트롤은 데이터 변경 내용을 메모리 내 데이터 원본에 저장하지 않습니다. 즉, 최종 사용자가 호스트 컨트롤에서 값을 변경한 다음 컨트롤에서 벗어나면 컨트롤의 새 값이 데이터 원본에 자동으로 저장되지 않습니다.  
  
 데이터 원본에 데이터를 저장하려면 런타임에 특정 이벤트에 대한 응답으로 데이터 원본을 업데이트하는 코드를 작성하거나, 컨트롤의 값이 변경되면 자동으로 데이터를 업데이트하도록 컨트롤을 구성하면 됩니다.  
  
 <xref:Microsoft.Office.Tools.Excel.ListObject> 변경 내용을 메모리 내 데이터 원본에 저장할 필요가 없습니다.<xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤을 데이터에 바인딩하면 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤은 추가 코드를 요구하지 않고 자동으로 변경 내용을 메모리 내 데이터 원본에 저장합니다.  
  
#### 런타임에 메모리 내 데이터 원본을 업데이트하려면  
  
-   컨트롤을 데이터 원본에 바인딩하는 <xref:System.Windows.Forms.Binding> 개체의 <xref:System.Windows.Forms.Binding.WriteValue%2A> 메서드를 호출합니다.  
  
     다음 예제에서는 Excel 워크시트의 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤의 변경 내용을 데이터 원본에 저장합니다. 이 예제에서는 해당 <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> 속성이 데이터 원본의 필드에 바인딩된 `namedRange1`이라는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤이 있다고 가정합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#1)]
     [!code-vb[Trin_VstcoreDataExcel#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#1)]  
  
### 메모리 내 데이터 원본을 자동으로 업데이트  
 또한 메모리 내 데이터 원본을 자동으로 업데이트하도록 컨트롤을 구성할 수도 있습니다. 문서 수준 프로젝트에서는 코드 또는 디자이너를 사용하여 이 작업을 수행할 수 있습니다. VSTO 추가 기능 프로젝트에서는 코드를 사용해야 합니다.  
  
##### 코드를 사용하여 메모리 내 데이터 원본을 자동으로 업데이트하도록 컨트롤을 설정하려면  
  
1.  컨트롤을 데이터 원본으로 바인딩하는 <xref:System.Windows.Forms.Binding> 개체의 System.Windows.Forms.DataSourceUpdateMode.OnPropertyChanged  모드를 사용합니다. 다음 두 가지 옵션으로 데이터 원본을 업데이트할 수 있습니다.  
  
    -   컨트롤의 유효성을 검사할 때 데이터 원본을 업데이트하려면 이 속성을 System.Windows.Forms.DataSourceUpdateMode.OnValidation으로 설정합니다.  
  
    -   컨트롤의 데이터 바인딩된 속성 값이 변경될 때 데이터 원본을 업데이트하려면 이 속성을 System.Windows.Forms.DataSourceUpdateMode.OnPropertyChanged로 설정합니다.  
  
        > [!NOTE]  
        >  System.Windows.Forms.DataSourceUpdateMode.OnPropertyChanged 옵션은 Word 호스트 컨트롤에는 적용되지 않습니다. Word가 문서 변경 또는 컨트롤 변경 알림을 제공하지 않기 때문입니다. 그러나 Word 문서의 Windows Forms 컨트롤에 대해서는 이 옵션을 사용할 수 있습니다.  
  
     다음 예제에서는 컨트롤의 값이 변경될 때 자동으로 데이터 원본을 업데이트하기 위해 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 구성합니다. 이 예제에서는 해당 <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> 속성이 데이터 원본의 필드에 바인딩된 `namedRange1`이라는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤이 있다고 가정합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#19](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#19)]
     [!code-vb[Trin_VstcoreDataExcel#19](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#19)]  
  
##### 디자이너를 사용하여 자동으로 메모리 내 데이터 원본을 업데이트하도록 컨트롤을 설정하려면  
  
1.  Visual Studio의 디자이너에서 Word 문서 또는 Excel 통합 문서를 엽니다.  
  
2.  데이터 원본을 자동으로 업데이트하려는 컨트롤을 클릭합니다.  
  
3.  **속성** 창에서 **\(DataBindings\)** 속성을 확장합니다.  
  
4.  **\(고급\)** 속성 옆에 있는 줄임표 단추\(![VisualStudioEllipsesButton 스크린 샷](../vsto/media/vbellipsesbutton.png "VisualStudioEllipsesButton 스크린 샷")\)를 클릭합니다.  
  
5.  **서식 지정 및 고급 바인딩** 대화 상자에서 **데이터 원본 업데이트 모드** 드롭다운 목록을 클릭하고 다음 값 중 하나를 선택합니다.  
  
    -   컨트롤의 유효성을 검사할 때 데이터 원본을 업데이트하려면 **OnValidation**을 선택합니다.  
  
    -   컨트롤의 데이터 바인딩된 속성 값이 변경될 때 데이터 원본을 업데이트하려면 **OnPropertyChanged**를 선택합니다.  
  
        > [!NOTE]  
        >  **OnPropertyChanged** 옵션은 Word 호스트 컨트롤에는 적용되지 않습니다. Word가 문서 변경 또는 컨트롤 변경 알림을 제공하지 않기 때문입니다. 그러나 Word 문서의 Windows Forms 컨트롤에 대해서는 이 옵션을 사용할 수 있습니다.  
  
6.  **서식 지정 및 고급 바인딩** 대화 상자를 닫습니다.  
  
## 데이터베이스 업데이트  
 메모리 내 데이터 원본이 데이터베이스와 연결된 경우 데이터베이스를 데이터 원본에 대한 변경 내용으로 업데이트해야 합니다. 데이터베이스를 업데이트하는 방법에 대한 자세한 내용은 [데이터 집합에 데이터 저장](../Topic/Saving%20data%20back%20to%20the%20database.md) 및 [방법: TableAdapter를 사용하여 데이터 업데이트](../data-tools/update-data-by-using-a-tableadapter.md)를 참조하세요.  
  
#### 데이터베이스를 업데이트하려면  
  
1.  컨트롤에 대한 <xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 메서드를 호출합니다.  
  
     디자인 타임에 데이터 바인딩된 컨트롤을 문서나 통합 문서에 추가하면 <xref:System.Windows.Forms.BindingSource>가 자동으로 생성됩니다.<xref:System.Windows.Forms.BindingSource>는 해당 컨트롤을 프로젝트의 형식화된 데이터 집합에 연결합니다. 자세한 내용은 [BindingSource 구성 요소 개요](http://msdn.microsoft.com/library/be838caf-fcb0-4b68-827f-58b2c04b747f)을 참조하세요.  
  
     다음 코드 예제에서는 프로젝트가 `customersBindingSource`라는 <xref:System.Windows.Forms.BindingSource>를 포함하고 있다고 가정합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#20](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#20)]
     [!code-vb[Trin_VstcoreDataExcel#20](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#20)]  
  
2.  프로젝트에서 생성된 TableAdapter의 `Update` 메서드를 호출합니다.  
  
     디자인 타임에 데이터 바인딩된 컨트롤을 문서나 통합 문서에 추가하면 TableAdapter가 자동으로 생성됩니다.TableAdapter는 프로젝트의 형식화된 데이터 집합을 데이터베이스에 연결합니다. 자세한 내용은 [TableAdapter 개요](/visual-studio/data-tools/tableadapter-overview)을 참조하세요.  
  
     다음 코드 예제는 Northwind 데이터베이스의 Customers 테이블에 연결되어 있고 프로젝트에 `customersTableAdapter`라는 TableAdapter 및 `northwindDataSet`이라는 형식화된 데이터 집합이 포함되어 있다고 가정합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#21](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#21)]
     [!code-vb[Trin_VstcoreDataExcel#21](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#21)]  
  
## 참고 항목  
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [데이터 집합에 데이터 저장](../Topic/Saving%20data%20back%20to%20the%20database.md)   
 [방법: TableAdapter를 사용하여 데이터 업데이트](../data-tools/update-data-by-using-a-tableadapter.md)   
 [방법: 워크시트에서 데이터베이스 레코드 스크롤](../vsto/how-to-scroll-through-database-records-in-a-worksheet.md)   
 [방법: 데이터베이스의 데이터로 워크시트 채우기](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [방법: 개체의 데이터로 문서 채우기](../vsto/how-to-populate-documents-with-data-from-objects.md)   
 [방법: 데이터베이스의 데이터로 문서 채우기](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [방법: 서비스의 데이터로 문서 채우기](../vsto/how-to-populate-documents-with-data-from-services.md)  
  
  