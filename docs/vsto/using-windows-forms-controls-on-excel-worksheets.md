---
title: "Windows Forms Excel 워크시트에서 컨트롤 사용 | Microsoft Docs"
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
- Windows Forms controls [Office development in Visual Studio], Excel
- Excel [Office development in Visual Studio], Windows Forms controls
- controls [Office development in Visual Studio], Window Forms controls
ms.assetid: bbda7461-0d69-4b56-8ba3-418d63ba49db
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7bbd9c19698a9c81b5af29d27bba91b8aa36dcd2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="using-windows-forms-controls-on-excel-worksheets"></a>Excel 워크시트에서 Windows Forms 컨트롤 사용
  Windows Forms에 컨트롤을 추가 하는 동일한 방식으로 Microsoft Office Excel 통합 문서에 Windows Forms 컨트롤을 추가할 수 있습니다. 문서에서 컨트롤 사용에 대 한 일반 정보를 참조 하십시오. [Office 문서 개요에 Windows Forms 컨트롤](../vsto/windows-forms-controls-on-office-documents-overview.md)합니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="control-considerations-for-excel"></a>Excel에 대 한 제어 고려 사항  
 Excel과 관련 된 몇 가지 고려 사항이 있습니다.  
  
### <a name="matching-control-size-to-cell-size"></a>셀 크기에 컨트롤 크기 맞춤  
 부모 셀의 크기가 변경될 때 자동으로 컨트롤의 크기가 조정되도록 설정할 수 있습니다. 자세한 내용은 참조 [하는 방법: 워크시트 셀 내에서 컨트롤의 크기를 조정](../vsto/how-to-resize-controls-within-worksheet-cells.md)합니다.  
  
### <a name="adding-components-that-are-shared-by-all-worksheets"></a>모든 워크시트에서 공유되는 구성 요소 추가  
 <xref:System.Data.DataSet>등 모든 워크시트에서 공유하려는 구성 요소는 워크시트 대신 통합 문서 디자이너에 추가할 수 있습니다. 이러한 구성 요소는 구성 요소 트레이에 표시됩니다.  
  
### <a name="formula-for-embedding-controls"></a>컨트롤 포함 수식  
 Excel에서 컨트롤을 선택하는 경우 **수식 입력줄** 에 **=EMBED("WinForms.Control.Host","")**가 표시됩니다. 이 텍스트는 필요하며 삭제하면 안 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 워크시트 셀에서 컨트롤 크기 조정](../vsto/how-to-resize-controls-within-worksheet-cells.md)   
 [방법: 인쇄할 때 워크시트에서 컨트롤 숨기기](../vsto/how-to-hide-controls-on-worksheets-when-printing.md)   
 [연습: CheckBox 컨트롤을 사용 하 여 워크시트 서식 변경](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md)   
 [연습: 단추를 사용 하 여 워크시트에 텍스트 상자에 텍스트 표시](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md)   
 [연습: 워크시트에서 라디오 단추를 사용하여 차트 업데이트](../vsto/walkthrough-updating-a-chart-in-a-worksheet-using-radio-buttons.md)  
  
  