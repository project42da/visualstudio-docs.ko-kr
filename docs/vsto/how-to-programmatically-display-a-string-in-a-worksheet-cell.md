---
title: "방법: 프로그래밍 방식으로 워크시트 셀에 문자열을 표시 | Microsoft Docs"
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
- text [Office development in Visual Studio], adding to worksheets
- worksheets, displaying text in cells
ms.assetid: b19870ad-e132-49fd-994e-0a91710fa4c9
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3e297a2f6c1752053557dd7bcea5adab1c2184aa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-display-a-string-in-a-worksheet-cell"></a>방법: 프로그래밍 방식으로 워크시트 셀에 문자열 표시
  이 예제에서는 프로그래밍 방식으로 셀에 텍스트를 표시 하는 방법을 보여 줍니다. 셀에 텍스트를 표시 하려면 하나를 사용는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤 또는 네이티브 Excel 범위 개체입니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-a-namedrange-control"></a>NamedRange 컨트롤을 사용 하 여  
 사용 하 여이 예제는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 라는 컨트롤 `message`합니다. 디자인 타임에 문서 수준 사용자 지정에 컨트롤을 추가 해야 합니다. 다음 코드에 없는 시트 클래스에 배치 되어야 합니다는 `ThisWorkbook` 클래스입니다.  
  
#### <a name="to-display-text-in-a-namedrange-control"></a>NamedRange 컨트롤의 텍스트를 표시 하려면  
  
1.  값을 설정할는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 **Hello World**합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#68](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#68)]
     [!code-vb[Trin_VstcoreExcelAutomation#68](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#68)]  
  
## <a name="using-a-native-excel-range"></a>네이티브 Excel 범위를 사용 하 여  
 다음 코드는 새 범위를 프로그래밍 방식으로 만들고 값을 할당 합니다.  
  
#### <a name="to-display-text-in-an-excel-range"></a>Excel 범위에 텍스트를 표시 하려면  
  
1.  셀에서 범위 검색 **A1** 에 `Sheet1` 값을 설정 하 고 **Hello World**합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#69](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#69)]
     [!code-vb[Trin_VstcoreExcelAutomation#69](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#69)]  
  
## <a name="see-also"></a>참고 항목  
 [연습: Windows Form을 사용 하 여 데이터 수집](../vsto/walkthrough-collecting-data-using-a-windows-form.md)   
 [Office 솔루션 문제 해결](../vsto/troubleshooting-office-solutions.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  