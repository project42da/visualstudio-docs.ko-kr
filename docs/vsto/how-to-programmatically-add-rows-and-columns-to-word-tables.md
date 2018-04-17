---
title: '방법: 프로그래밍 방식으로 Word 표에 행과 열을 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- rows [Office development in Visual Studio], adding to Word tables
- tables [Office development in Visual Studio], adding rows and columns
- columns [Office development in Visual Studio], adding to Word tables
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 5058665c0c6d882e41d534d51a398ae90e0e03e6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-add-rows-and-columns-to-word-tables"></a>방법: 프로그래밍 방식으로 Word 표에 행 및 열 추가
  Microsoft Office Word 표에서 셀은 행과 열로 구성됩니다. <xref:Microsoft.Office.Interop.Word.Rows> 개체의 <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> 메서드를 사용하여 표에 행을 추가하고, <xref:Microsoft.Office.Interop.Word.Columns> 개체의 <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> 메서드를 사용하여 열을 추가할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="document-level-customization-examples"></a>문서 수준 사용자 지정 예제  
 다음 코드 예제는 문서 수준 사용자 지정에서 사용할 수 있습니다. 이러한 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다. 이 예제에서는 사용자 지정과 연결된 문서에 하나 이상의 표가 이미 있다고 가정합니다.  
  
> [!IMPORTANT]  
>  이 코드는 다음 프로젝트 템플릿 중 하나를 사용하여 만든 프로젝트에서만 실행됩니다.  
>   
>  -   Word 2013 문서  
> -   Word 2013 서식 파일  
> -   Word 2010 문서  
> -   Word 2010 서식 파일  
>   
>  에 대 한 참조를 추가 해야 다른 형식의 프로젝트에서이 작업을 수행 하려는 경우는 **Microsoft.Office.Interop.Word** 어셈블리 및 다음 테이블에 행과 열을 추가 하려면 해당 어셈블리의에서 클래스를 사용 해야 합니다. 자세한 내용은 참조 [하는 방법: Office 응용 프로그램을 통해 주 Interop 어셈블리 대상](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) 및 [Word 2010 주 Interop 어셈블리 참조](http://go.microsoft.com/fwlink/?LinkId=189588)합니다.  
  
#### <a name="to-add-a-row-to-a-table"></a>표에 행을 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> 메서드를 사용하여 표에 행을 추가합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#95](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#95)]
     [!code-csharp[Trin_VstcoreWordAutomation#95](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#95)]  
  
#### <a name="to-add-a-column-to-a-table"></a>표에 열을 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> 메서드를 사용한 다음 <xref:Microsoft.Office.Interop.Word.Columns.DistributeWidth%2A> 메서드를 사용하여 모든 열 너비를 동일하게 만듭니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#96](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#96)]
     [!code-csharp[Trin_VstcoreWordAutomation#96](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#96)]  
  
## <a name="vsto-add-in-examples"></a>VSTO 추가 기능 예제  
 다음 코드 예제는 VSTO 추가 기능에서 사용할 수 있습니다. 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다. 이 예제에서는 활성 문서에 하나 이상의 표가 이미 있다고 가정합니다.  
  
> [!IMPORTANT]  
>  이 코드는 Word VSTO 추가 기능 템플릿을 사용하여 만든 프로젝트에서만 실행됩니다.  
>   
>  에 대 한 참조를 추가 해야 다른 형식의 프로젝트에서이 작업을 수행 하려는 경우는 **Microsoft.Office.Interop.Word** 어셈블리 및 다음 테이블에 행과 열을 추가 하려면 해당 어셈블리의에서 클래스를 사용 해야 합니다. 자세한 내용은 참조 [하는 방법: Office 응용 프로그램을 통해 주 Interop 어셈블리 대상](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) 및 [Word 2010 주 Interop 어셈블리 참조](http://go.microsoft.com/fwlink/?LinkId=189588)합니다.  
  
#### <a name="to-add-a-row-to-a-table"></a>표에 행을 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> 메서드를 사용하여 표에 행을 추가합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#95](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#95)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#95](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#95)]  
  
#### <a name="to-add-a-column-to-a-table"></a>표에 열을 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> 메서드를 사용한 다음 <xref:Microsoft.Office.Interop.Word.Columns.DistributeWidth%2A> 메서드를 사용하여 모든 열 너비를 동일하게 만듭니다.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#96](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#96)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#96](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#96)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로그래밍 방식으로 Word 표 만들기](../vsto/how-to-programmatically-create-word-tables.md)   
 [방법: 프로그래밍 방식으로 Word 표 셀에 텍스트 및 서식 추가](../vsto/how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables.md)   
 [방법: 프로그래밍 방식으로 문서 속성을 사용하여 Word 표 채우기](../vsto/how-to-programmatically-populate-word-tables-with-document-properties.md)  
  
  