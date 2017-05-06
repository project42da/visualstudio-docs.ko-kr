---
title: "방법: ListObject 컨트롤에 새 행을 추가할 때 데이터 유효성 검사"
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
  - "컨트롤[Visual Studio에서 Office 개발], 데이터 유효성 검사"
  - "ListObject 컨트롤, 새 행"
  - "ListObject 컨트롤, 데이터 유효성 검사"
ms.assetid: 107bce92-e5ef-40be-8c05-cd6861d39d75
caps.latest.revision: 43
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 42
---
# 방법: ListObject 컨트롤에 새 행을 추가할 때 데이터 유효성 검사
  사용자는 데이터에 바인딩된 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤에 새 행을 추가할 수 있습니다. 데이터 원본에 대한 변경 내용을 커밋하기 전에 사용자 데이터의 유효성을 확인할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## 데이터 유효성 검사  
 데이터에 바인딩된 <xref:Microsoft.Office.Tools.Excel.ListObject>에 행을 추가할 때마다 <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeAddDataBoundRow> 이벤트가 발생합니다. 데이터 유효성 검사를 수행하도록 이 이벤트를 처리할 수 있습니다. 예를 들어 18세에서 65세 사이의 직원만 데이터 원본에 추가할 수 있도록 응용 프로그램에서 요구하는 경우 행이 추가되기 전에 입력한 나이가 이 범위에 포함되는지 확인할 수 있습니다.  
  
> [!NOTE]  
>  클라이언트뿐 아니라 서버에서의 사용자 입력도 항상 확인해야 합니다. 자세한 내용은 [보안 클라이언트 응용 프로그램](http://msdn.microsoft.com/library/6239592e-fa7d-4dea-9f00-d296d0048b01)을 참조하세요.  
  
#### 데이터 바인딩된 ListObject에 새 행을 추가할 때 데이터 유효성을 검사하려면  
  
1.  클래스 수준에서 ID 및 <xref:System.Data.DataTable>에 대한 변수를 만듭니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#8](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet1.cs#8)]
     [!code-vb[Trin_VstcoreHostControlsExcel#8](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet1.vb#8)]  
  
2.  새 <xref:System.Data.DataTable>을 만들고 `Sheet1` 클래스\(문서 수준 프로젝트\) 또는 `ThisAddIn` 클래스\(VSTO 추가 기능 프로젝트\)의 `Startup` 이벤트 처리기에 샘플 열과 데이터를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#9](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet1.cs#9)]
     [!code-vb[Trin_VstcoreHostControlsExcel#9](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet1.vb#9)]  
  
3.  `list1_BeforeAddDataBoundRow` 이벤트 처리기에 코드를 추가하여 입력된 나이가 허용 가능한 범위 내에 포함되는지 확인합니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#10](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet1.cs#10)]
     [!code-vb[Trin_VstcoreHostControlsExcel#10](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet1.vb#10)]  
  
## 코드 컴파일  
 이 코드 예제에서는 이 코드가 표시되는 워크시트에 `list1`이라는 기존 <xref:Microsoft.Office.Tools.Excel.ListObject>가 있는 것으로 간주합니다.  
  
## 참고 항목  
 [런타임에 VSTO 추가 기능에서 Word 문서 및 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [ListObject 컨트롤](../vsto/listobject-control.md)   
 [확장된 개체를 사용하여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [방법: 데이터에 ListObject 열 매핑](../vsto/how-to-map-listobject-columns-to-data.md)  
  
  