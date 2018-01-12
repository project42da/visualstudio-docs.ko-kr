---
title: "방법: 프로그래밍 방식으로 문서 속성으로 Word 표 채우기 | Microsoft Docs"
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
- document properties, inserting in Word tables
- documents [Office development in Visual Studio], document properties
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: b305196b9dd05ebf411c4c68e869f5c9c5cbffc5
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-populate-word-tables-with-document-properties"></a>방법: 프로그래밍 방식으로 문서 속성을 사용하여 Word 표 채우기
  다음 예제에서는 문서의 맨 위에 Microsoft Office Word 표를 만들고 호스트 문서의 속성으로 채웁니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="populating-tables-in-a-document-level-customization"></a>문서 수준 사용자 지정에서 표 채우기  
  
#### <a name="to-create-a-table-and-populate-it-with-document-properties"></a>표를 만들고 문서 속성으로 채우려면  
  
1.  범위를 문서의 맨 위로 설정합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#90](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#90)]
     [!code-csharp[Trin_VstcoreWordAutomation#90](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#90)]  
  
2.  표의 제목을 삽입하고 단락 표시를 포함합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#91](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#91)]
     [!code-csharp[Trin_VstcoreWordAutomation#91](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#91)]  
  
3.  문서의 범위에 표를 추가합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#92](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#92)]
     [!code-csharp[Trin_VstcoreWordAutomation#92](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#92)]  
  
4.  표의 서식을 지정하고 스타일을 적용합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#93](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#93)]
     [!code-csharp[Trin_VstcoreWordAutomation#93](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#93)]  
  
5.  셀에 문서 속성을 삽입합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#94](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#94)]
     [!code-csharp[Trin_VstcoreWordAutomation#94](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#94)]  
  
 다음 예제에서는 전체 절차를 보여 줍니다. 이 코드를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
 [!code-vb[Trin_VstcoreWordAutomation#89](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#89)]
 [!code-csharp[Trin_VstcoreWordAutomation#89](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#89)]  
  
## <a name="populating-tables-in-a-vsto-add-in"></a>VSTO 추가 기능에서 표 채우기  
  
#### <a name="to-create-a-table-and-populate-it-with-document-properties"></a>표를 만들고 문서 속성으로 채우려면  
  
1.  범위를 문서의 맨 위로 설정합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#90](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#90)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#90](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#90)]  
  
2.  표의 제목을 삽입하고 단락 표시를 포함합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#91](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#91)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#91](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#91)]  
  
3.  문서의 범위에 표를 추가합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#92](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#92)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#92](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#92)]  
  
4.  표의 서식을 지정하고 스타일을 적용합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#93](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#93)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#93](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#93)]  
  
5.  셀에 문서 속성을 삽입합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#94](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#94)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#94](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#94)]  
  
 다음 예제에서는 전체 절차를 보여 줍니다. 이 코드를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
 [!code-vb[Trin_VstcoreWordAutomationAddIn#89](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#89)]
 [!code-csharp[Trin_VstcoreWordAutomationAddIn#89](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#89)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로그래밍 방식으로 Word 표 만들기](../vsto/how-to-programmatically-create-word-tables.md)   
 [방법: 프로그래밍 방식으로 Word 표 셀에 텍스트 및 서식 추가](../vsto/how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables.md)   
 [방법: 프로그래밍 방식으로 Word 표에 행과 열 추가](../vsto/how-to-programmatically-add-rows-and-columns-to-word-tables.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  