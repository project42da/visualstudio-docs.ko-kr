---
title: "방법: ListObject 컨트롤을 데이터로 채우기 | Microsoft Docs"
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
  - "데이터 원본 연결 끊기"
  - "ListObject 컨트롤, 데이터 원본 연결 끊기"
  - "ListObject 컨트롤, 데이터로 채우기"
  - "데이터[Visual Studio에서 Office 개발], 워크시트에 추가"
  - "데이터 바인딩, ListObject 컨트롤"
  - "워크시트, 데이터로 채우기"
ms.assetid: bf692c77-f5cc-456a-9a5c-84ed3067d7eb
caps.latest.revision: 27
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 26
---
# 방법: ListObject 컨트롤을 데이터로 채우기
  신속하게 문서에 데이터를 추가하는 방법으로 데이터 바인딩을 사용할 수 있습니다. 목록 개체에 데이터를 바인딩한 후 해당 데이터를 표시하지만 더 이상 데이터 원본에 바인딩되지 않도록 목록 개체의 연결을 끊을 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 ![비디오에 링크](../vsto/media/playvideo.png "비디오에 링크") 관련 동영상 데모는 [어떻게 할까요?: Excel에서 SharePoint 목록에 연결된 목록 만들기](http://go.microsoft.com/fwlink/?LinkID=130263)를 참조하세요.  
  
### ListObject 컨트롤에 데이터를 바인딩하려면  
  
1.  클래스 수준에서 <xref:System.Data.DataTable>을 만듭니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#20](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet4.cs#20)]
     [!code-vb[Trin_VstcoreHostControlsExcel#20](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet4.vb#20)]  
  
2.  `Sheet1` 클래스\(문서 수준 프로젝트\) 또는 `ThisAddIn` 클래스\(응용 프로그램 수준 프로젝트\)의 `Startup` 이벤트 처리기에서 샘플 열과 데이터를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#21](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet4.cs#21)]
     [!code-vb[Trin_VstcoreHostControlsExcel#21](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet4.vb#21)]  
  
3.  <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> 메서드를 호출하고 표시할 순서대로 열 이름을 전달합니다. 목록 개체의 열 순서는 <xref:System.Data.DataTable>에 표시되는 순서와 다를 수 있습니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#22](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet4.cs#22)]
     [!code-vb[Trin_VstcoreHostControlsExcel#22](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet4.vb#22)]  
  
### 데이터 원본에서 ListObject 컨트롤의 연결을 끊으려면  
  
1.  `List1`의 <xref:Microsoft.Office.Tools.Excel.ListObject.Disconnect%2A> 메서드를 호출합니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#23](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet4.cs#23)]
     [!code-vb[Trin_VstcoreHostControlsExcel#23](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet4.vb#23)]  
  
## 코드 컴파일  
 이 코드 예제에서는 이 코드가 표시되는 워크시트에 `list1`이라는 기존 <xref:Microsoft.Office.Tools.Excel.ListObject>가 있는 것으로 간주합니다.  
  
## 참고 항목  
 [런타임에 VSTO 추가 기능에서 Word 문서 및 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [방법: 데이터에 ListObject 열 매핑](../vsto/how-to-map-listobject-columns-to-data.md)   
 [확장된 개체를 사용하여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [ListObject 컨트롤](../vsto/listobject-control.md)   
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [방법: 데이터베이스의 데이터로 워크시트 채우기](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [방법: 서비스의 데이터로 문서 채우기](../vsto/how-to-populate-documents-with-data-from-services.md)  
  
  