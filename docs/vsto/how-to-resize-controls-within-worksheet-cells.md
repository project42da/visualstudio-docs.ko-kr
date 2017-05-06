---
title: "방법: 워크시트 셀에서 컨트롤 크기 조정"
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
  - "컨트롤[Visual Studio에서 Office 개발], 크기 조정"
  - "관리되는 컨트롤, 크기 조정"
  - "Windows Forms 컨트롤[Visual Studio에서 Office 개발], 크기 조정"
  - "워크시트, 크기 조정"
ms.assetid: 1439db4a-e64b-4381-a6e6-605ba94db3de
caps.latest.revision: 33
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 32
---
# 방법: 워크시트 셀에서 컨트롤 크기 조정
  워크시트에서 열이나 행의 크기를 조정하면 크기가 변경된 셀의 높이나 너비에 맞도록 셀에 포함된 모든 호스트 컨트롤의 크기가 자동으로 조정됩니다.  Windows Forms 컨트롤은 기본적으로 크기가 자동으로 조정되지 않습니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 디자인 타임에 컨트롤을 추가하는 경우 각 컨트롤에 대해 위치 지정 옵션을 설정해야 합니다.  
  
 Windows Forms 컨트롤을 프로그래밍 방식으로 추가하고 범위 인수를 지정하면 범위 내의 셀 크기를 조정할 때 컨트롤의 크기가 자동으로 조정됩니다.  자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)을 참조하십시오.  
  
## 디자인 타임에 컨트롤 크기 조정  
  
#### 디자인 타임에 셀과 함께 컨트롤 크기를 조정하려면  
  
1.  **도구 상자**에서 Windows Forms 컨트롤을 워크시트로 끌어 놓습니다.  
  
2.  컨트롤을 마우스 오른쪽 단추로 클릭한 다음 **컨트롤 서식**을 클릭합니다.  
  
3.  **컨트롤 서식** 대화 상자에서 **속성** 탭을 클릭합니다.  
  
4.  **개체 위치**에서 **위치와 크기 변함** 옵션을 선택하고 **확인**을 클릭합니다.  
  
     컨트롤이 들어 있는 셀의 크기를 조정하면 컨트롤의 크기가 해당 셀에 맞도록 조정됩니다.  
  
## 런타임에 컨트롤 크기 조정  
 런타임에 Windows Forms 컨트롤을 추가하고 <xref:Microsoft.Office.Interop.Excel.Range>를 컨트롤의 위치로 전달하면 범위가 포함된 워크시트 셀의 크기를 조정할 때 컨트롤 크기도 자동으로 조정됩니다.  
  
#### 런타임에 셀과 함께 컨트롤 크기를 조정하려면  
  
1.  컨트롤을 범위 A1에 추가합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/Sheet1.cs#5)]
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#5](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/VB/Sheet1.vb#5)]  
  
     컨트롤이 들어 있는 셀의 크기를 조정하면 컨트롤의 크기가 해당 셀에 맞도록 조정됩니다.  
  
## 컨트롤 배치 다시 설정  
 `Placement` 속성을 다음 <xref:Microsoft.Office.Interop.Excel.XlPlacement> 값 중 하나로 설정하여 컨트롤의 배치와 크기를 다시 설정할 수 있습니다.  
  
-   <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlFreeFloating>  
  
-   <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlMove>  
  
-   <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlMoveAndSize>  
  
#### 컨트롤이 셀과 함께 크기 조정되거나 이동하지 않도록 컨트롤의 동작을 변경하려면  
  
1.  컨트롤의 배치 속성을 호출하고 값을 <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlFreeFloating>으로 설정합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#6](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/Sheet1.cs#6)]
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#6](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/VB/Sheet1.vb#6)]  
  
## 참고 항목  
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [방법: Office 문서에 Windows Forms 컨트롤 추가](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [방법: 인쇄할 때 워크시트에서 컨트롤 숨기기](../vsto/how-to-hide-controls-on-worksheets-when-printing.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Office 문서에서 Windows Forms 컨트롤에 대한 제한 사항](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  