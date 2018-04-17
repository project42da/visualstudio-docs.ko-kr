---
title: '방법: 프로그래밍 방식으로 최근에 사용한 파일 목록에서 통합 문서 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, listing recently used
- RecentFiles property
- Excel [Office development in Visual Studio], recently used files listing
- recent file list, Excel
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c2d9c333b6d96329abec3fd52ecaa5da1cf97c74
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-list-recently-used-workbook-files"></a>방법: 프로그래밍 방식으로 최근에 사용한 통합 문서 파일 나열
  <xref:Microsoft.Office.Interop.Excel._Application.RecentFiles%2A> 속성이 최근에 사용한 파일의 Microsoft Office Excel 목록에 표시 되는 모든 파일의 이름이 포함 된 컬렉션을 반환 합니다. 목록의 길이 유지 하려면 사용자가 선택한 파일의 수에 따라 달라 집니다. 범위에서 결과 표시할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-list-recently-used-workbooks-in-a-range-object"></a>Range 개체의 목록 최근에 사용한 통합 문서에  
  
1.  최근에 사용한 파일 목록을 통해 반복 하 고 이름을 기준으로 셀에 표시 된 <xref:Microsoft.Office.Interop.Excel.Range> 개체입니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#9](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#9](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#9)]  
  
## <a name="see-also"></a>참고 항목  
 [통합 문서 사용](../vsto/working-with-workbooks.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  