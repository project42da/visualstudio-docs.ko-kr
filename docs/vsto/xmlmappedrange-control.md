---
title: "XmlMappedRange 컨트롤"
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
  - "XMLMappedRange 컨트롤"
  - "XMLMappedRange 컨트롤, 데이터 바인딩"
  - "XMLMappedRange 컨트롤, 이벤트"
ms.assetid: af1ae1b7-6cbe-4d6b-bc22-d9a3c8740665
caps.latest.revision: 40
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 39
---
# XmlMappedRange 컨트롤
  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤은 반복되지 않는 스키마 요소를 Microsoft Office Excel의 셀에 매핑하는 경우에만 만들어지는 범위입니다.  예를 들어 스키마 요소의 `maxOccurs` 특성이 1인 경우,  Visual Studio에서 XML이 매핑된 범위가 만들어진 후 Excel 개체 모델을 트래버스하지 않고도 이 범위에 대해 직접 프로그래밍을 할 수 있습니다.  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤은 요소 매핑을 제거하는 경우에만 Excel 내에서 삭제할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 ![비디오에 링크](../vsto/media/playvideo.png "비디오에 링크") 관련 비디오 데모를 보려면 [How Do I: Use XML Mapping in Excel?](http://go.microsoft.com/fwlink/?LinkID=130288)을 참조하십시오.  
  
## 컨트롤에 데이터 바인딩  
 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤은 단일 데이터 필드에 대한 바인딩\(단순 데이터 바인딩\)을 지원합니다.  <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤은 복합 데이터 바인딩을 지원할 수 있으며 반복되는 스키마 요소를 셀에 매핑하는 경우 자동으로 작성됩니다.  자세한 내용은 [ListObject 컨트롤](../vsto/listobject-control.md)을 참조하십시오.  
  
 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤은 <xref:System.Windows.Forms.Control.DataBindings%2A> 속성을 사용하여 데이터 소스에 바인딩됩니다.  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange>를 워크시트 셀에 추가하면 Visual Studio를 통해 매핑된 셀의 데이터에서 데이터 집합이 자동으로 생성되고 컨트롤이 이 데이터 집합에 바인딩됩니다.  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange>의 기본 데이터 바인딩 속성은 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Value2%2A>입니다.  
  
 바인딩된 데이터 집합의 데이터가 어떤 메커니즘을 통해 업데이트되면 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤이 변경 내용을 반영합니다.  
  
## 형식 지정  
 <xref:Microsoft.Office.Interop.Excel.Range>에 적용할 수 있는 것과 동일한 형식을 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange>에 적용할 수 있습니다.  여기에는 테두리, 글꼴, 숫자 형식 및 스타일이 포함됩니다.  
  
## 이벤트  
 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤에 사용할 수 있는 이벤트는 다음과 같습니다.  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Change>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Selected>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Deselected>  
  
-   <xref:System.ComponentModel.Component.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.SelectionChange>  
  
## 참고 항목  
 [확장된 개체를 사용하여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [방법: 워크시트에 XMLMappedRange 컨트롤 추가](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)   
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [방법: Visual Studio 내에서 워크시트에 스키마 매핑](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  