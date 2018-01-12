---
title: "방법: 프로그래밍 방식으로 Excel 범위에 색 적용 | Microsoft Docs"
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
- formatting [Office development in Visual Studio]
- color, Excel ranges
- ranges, applying color
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 5e9b5f6bc38cdcb4b4ee11543ea70e3b137a937f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-apply-color-to-excel-ranges"></a>방법: 프로그래밍 방식으로 Excel 범위에 색 적용
  셀의 범위 내의 텍스트 색을 적용 하려면 사용을 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤 또는 네이티브 Excel 범위 개체입니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-a-namedrange-control"></a>NamedRange 컨트롤을 사용 하 여  
 이 예제는 문서 수준 사용자 지정 합니다.  
  
#### <a name="to-apply-color-to-a-namedrange-control"></a>NamedRange 컨트롤에 색을 적용 하려면  
  
1.  만들기는 <xref:Microsoft.Office.Tools.Excel.NamedRange> A1 셀에서 제어 합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#65](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#65)]
     [!code-vb[Trin_VstcoreExcelAutomation#65](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#65)]  
  
2.  에 있는 텍스트의 색 설정의 <xref:Microsoft.Office.Tools.Excel.NamedRange> 제어 합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#66](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#66)]
     [!code-vb[Trin_VstcoreExcelAutomation#66](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#66)]  
  
## <a name="using-native-excel-ranges"></a>네이티브 Excel 범위를 사용 하 여  
  
#### <a name="to-apply-color-to-a-native-excel-range-object"></a>네이티브 Excel 범위 개체에 색을 적용 하려면  
  
1.  A1 셀에 범위를 만들고 텍스트의 색을 설정 합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#67](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#67)]
     [!code-vb[Trin_VstcoreExcelAutomation#67](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#67)]  
  
## <a name="see-also"></a>참고 항목  
 [범위 작업](../vsto/working-with-ranges.md)   
 [NamedRange 컨트롤](../vsto/namedrange-control.md)   
 [방법: 프로그래밍 방식으로 통합 문서에서 범위에 스타일을 적용](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [방법: 프로그래밍 방식으로 코드에서 워크시트 범위 참조](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [확장 된 개체를 사용 하 여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  