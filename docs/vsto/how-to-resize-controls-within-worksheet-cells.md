---
title: '방법: 워크시트 셀에서 컨트롤의 크기를 조정 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], resizing
- managed controls, resizing
- worksheets, resizing
- Windows Forms controls [Office development in Visual Studio], resizing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b145d4435cdb295c94897424b318d328f995c340
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-resize-controls-within-worksheet-cells"></a>방법: 워크시트 셀에서 컨트롤 크기 조정
  워크시트에 행 또는 열 크기를 조정 하면 자동으로 셀에 포함 된 모든 호스트 컨트롤 크기를 조정한 셀의 너비 또는 높이 크기를 조정 합니다. Windows Forms 컨트롤 기본적으로 자동으로 크기가 조정 되지 않습니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 디자인 타임에 컨트롤을 추가 하는 경우 각 컨트롤에 대 한 옵션을 위치를 설정 해야 합니다.  
  
 Windows Forms 컨트롤을 프로그래밍 방식으로 추가 하 고 범위 인수를 제공 하는 경우 범위 내에 있는 셀의 크기를 조정할 때 컨트롤이 자동으로 조정 합니다. 자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)을 참조하세요.  
  
## <a name="resizing-controls-at-design-time"></a>디자인 타임에 컨트롤의 크기 조정  
  
#### <a name="to-make-controls-resize-with-cells-at-design-time"></a>컨트롤 디자인 타임에 셀 크기를 조정 하려면  
  
1.  **도구 상자**, 워크시트에 Windows Forms 컨트롤을 끌어 옵니다.  
  
2.  컨트롤을 마우스 오른쪽 단추로 누른 **컨트롤 서식**합니다.  
  
3.  에 **컨트롤 서식** 대화 상자를 클릭는 **속성** 탭 합니다.  
  
4.  **개체 위치**, 선택는 **이동 하 고 셀 크기** 옵션을 선택한 다음 클릭 **확인**합니다.  
  
     컨트롤이 포함 된 셀 크기를 조정할 때 컨트롤의 셀에 맞게 크기가 조정 합니다.  
  
## <a name="resizing-controls-at-run-time"></a>런타임 시 컨트롤의 크기 조정  
 런타임에 Windows Forms 컨트롤을 추가 하 고 전달 하는 경우는 <xref:Microsoft.Office.Interop.Excel.Range> 컨트롤에 대 한 위치로 컨트롤 자동으로 조정 될 때 범위에 포함 된 워크시트 셀의 크기를 조정 합니다.  
  
#### <a name="to-make-controls-resize-with-cells-at-run-time"></a>컨트롤 런타임 시 셀 크기를 조정 하려면  
  
1.  컨트롤을 범위 a 1 추가 합니다.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#5](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#5)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#5)]  
  
     컨트롤이 포함 된 셀 크기를 조정할 때 컨트롤의 셀에 맞게 크기가 조정 합니다.  
  
## <a name="resetting-control-placement"></a>컨트롤 배치를 다시 설정  
 배치와 설정 하 여 컨트롤의 크기를 다시 설정할 수는 `Placement` 속성을 다음 중 하나로 <xref:Microsoft.Office.Interop.Excel.XlPlacement> 값:  
  
-   <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlFreeFloating>  
  
-   <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlMove>  
  
-   <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlMoveAndSize>  
  
#### <a name="to-change-the-behavior-of-a-control-so-that-it-does-not-resize-or-move-with-the-cell"></a>크기를 조정 하거나 셀으로 이동 하지 않는 되도록 컨트롤의 동작을 변경 하려면  
  
1.  컨트롤의 배치 속성을 호출 하 고 값을 설정 <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlFreeFloating>합니다.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#6](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#6)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#6](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#6)]  
  
## <a name="see-also"></a>참고 항목  
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [방법: Office 문서에 Windows Forms 컨트롤 추가](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [방법: 인쇄할 때 워크시트에서 컨트롤 숨기기](../vsto/how-to-hide-controls-on-worksheets-when-printing.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Office 문서에서 Windows Forms 컨트롤에 대한 제한 사항](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  