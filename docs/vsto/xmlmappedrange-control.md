---
title: "XmlMappedRange 컨트롤 | Microsoft Docs"
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
- XMLMappedRange control, data binding
- XMLMappedRange control
- XMLMappedRange control, events
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: f4b78da11efafff45f34b3dc4ab9e7f1349a2e8a
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="xmlmappedrange-control"></a>XmlMappedRange 컨트롤
  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤은 반복 되지 않는 스키마 요소는 Microsoft Office Excel에서 셀에 매핑될 때에 생성 되는 범위입니다. 예를 들어는 `maxOccurs` 스키마 요소의 특성은 1입니다. Visual Studio에서 매핑된 XML 범위를 만든 후 Excel 개체 모델을 트래버스 하지 않고 직접 프로그래밍할 수 있습니다. 삭제할 수 있습니다는 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 요소 매핑을 제거 될 때 Excel 내에서 제어 합니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 ![비디오에 링크](../vsto/media/playvideo.gif "비디오에 링크") 관련된 동영상 데모를 참조 하십시오. [어떻게 수행 할까요 사용 하 여 XML의에서 매핑 Excel?](http://go.microsoft.com/fwlink/?LinkID=130288)합니다.  
  
## <a name="binding-data-to-the-control"></a>컨트롤에 데이터 바인딩  
 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤은 단일 데이터 필드 (단순 데이터 바인딩)에 대 한 바인딩을 지원 합니다. <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤 수 복잡 한 데이터 바인딩을 지원 하 고 반복 스키마 요소는 셀에 매핑될 때 자동으로 만들어집니다. 자세한 내용은 [ListObject Control](../vsto/listobject-control.md)을 참조하세요.  
  
 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 사용 하 여 데이터 소스에 바인딩된 컨트롤에서 <xref:System.Windows.Forms.Control.DataBindings%2A> 속성입니다. 경우는 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> Visual Studio에서 자동으로 매핑된 셀의 데이터에서 데이터 집합을 생성 하 고 해당 데이터 집합에 바인딩됩니다 워크시트 셀에 추가 됩니다. 기본 데이터 바인딩 속성은 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 은 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Value2%2A>합니다.  
  
 바인딩된 데이터 집합의 데이터가 임의 메커니즘을 통해 업데이트 되는 경우는 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤이 변경 내용을 반영 합니다.  
  
## <a name="formatting"></a>서식  
 에 동일한 서식을 적용할 수 있습니다는 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤에 적용할 수 있는 한 <xref:Microsoft.Office.Interop.Excel.Range>합니다. 여기에는 테두리, 글꼴, 숫자 서식 및 스타일이 포함됩니다.  
  
## <a name="events"></a>이벤트  
 에 대해 사용할 수 있는 이벤트는 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 제어 됩니다.  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Change>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Selected>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Deselected>  
  
-   <xref:System.ComponentModel.Component.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.SelectionChange>  
  
## <a name="see-also"></a>참고 항목  
 [확장 된 개체를 사용 하 여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [방법: 워크시트에 XMLMappedRange 컨트롤 추가](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)   
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [방법: Visual Studio 내에서 워크시트에 스키마 매핑](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  