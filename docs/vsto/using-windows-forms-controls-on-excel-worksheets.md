---
title: "Excel 워크시트에서 Windows Forms 컨트롤 사용 | Microsoft Docs"
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
  - "컨트롤[Visual Studio에서 Office 개발], Windows Forms 컨트롤"
  - "Excel[Visual Studio에서 Office 개발], Windows Forms 컨트롤"
  - "Windows Forms 컨트롤[Visual Studio에서 Office 개발], Excel"
ms.assetid: bbda7461-0d69-4b56-8ba3-418d63ba49db
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 16
---
# Excel 워크시트에서 Windows Forms 컨트롤 사용
  Windows Forms에 컨트롤을 추가할 때와 동일한 방식으로 Windows Forms 컨트롤을 Microsoft Office Excel 통합 문서에 추가할 수 있습니다.  문서의 컨트롤 작업에 대한 일반적인 내용은 [Office 문서의 Windows Forms 컨트롤 개요](../vsto/windows-forms-controls-on-office-documents-overview.md)를 참조하십시오.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## Excel의 컨트롤 고려 사항  
 Excel과 관련된 고려 사항이 몇 가지 있습니다.  
  
### 컨트롤 크기와 셀 크기 일치  
 부모 셀의 크기가 변경되면 컨트롤의 크기가 자동으로 조정되도록 설정할 수 있습니다.  자세한 내용은 [방법: 워크시트 셀에서 컨트롤 크기 조정](../vsto/how-to-resize-controls-within-worksheet-cells.md)을 참조하십시오.  
  
### 모든 워크시트에서 공유하는 구성 요소 추가  
 <xref:System.Data.DataSet>와 같이 모든 워크시트에서 공유할 구성 요소는 워크시트 대신 통합 문서 디자이너에 추가할 수 있습니다.  이 구성 요소는 구성 요소 트레이에 나타납니다.  
  
### 컨트롤을 포함하기 위한 수식  
 Excel에서 컨트롤을 선택하면 **수식 입력줄**에 **\=EMBED\("WinForms.Control.Host",""\)**가 표시됩니다.  이 텍스트는 필요하므로 삭제해서는 안 됩니다.  
  
## 참고 항목  
 [방법: 워크시트 셀에서 컨트롤 크기 조정](../vsto/how-to-resize-controls-within-worksheet-cells.md)   
 [방법: 인쇄할 때 워크시트에서 컨트롤 숨기기](../vsto/how-to-hide-controls-on-worksheets-when-printing.md)   
 [연습: CheckBox 컨트롤을 사용하여 워크시트 서식 변경](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md)   
 [연습: 워크시트에서 단추를 사용하여 텍스트 상자에 텍스트 표시](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md)   
 [연습: 워크시트에서 라디오 단추를 사용하여 차트 업데이트](../vsto/walkthrough-updating-a-chart-in-a-worksheet-using-radio-buttons.md)  
  
  