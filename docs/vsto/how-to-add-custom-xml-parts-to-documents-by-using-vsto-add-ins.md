---
title: "방법: VSTO 추가 기능을 사용 하 여 문서에 사용자 지정 XML 부분 추가 | Microsoft Docs"
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
- add-ins [Office development in Visual Studio], custom XML parts
- Office documents [Office development in Visual Studio, custom XML parts
- Word [Office development in Visual Studio], custom XML parts
- PowerPoint [Office development in Visual Studio], custom XML parts
- Excel [Office development in Visual Studio], custom XML parts
- custom XML parts [Office development in Visual Studio], adding
- documents [Office development in Visual Studio], custom XML parts
- application-level add-ins [Office development in Visual Studio], custom XML parts
ms.assetid: 872d2beb-193b-49f9-9a7b-dcebab91a73b
caps.latest.revision: "27"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e851c0dcdbb3ed86dcf4a303cc1ad26b65035bc8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins"></a>방법: VSTO 추가 기능을 사용하여 문서에 사용자 지정 XML 부분 추가
  VSTO 추가 기능에서 사용자 지정 XML 부분을 만들어 다음과 같은 형식의 문서에 XML 데이터를 저장할 수 있습니다.  
  
-   Microsoft Office Excel 통합 문서  
  
-   Microsoft Office Word 문서  
  
-   Microsoft Office PowerPoint 프레젠테이션  
  
 자세한 내용은 [Custom XML Parts Overview](../vsto/custom-xml-parts-overview.md)을 참조하세요.  
  
 **적용 대상:** 이 항목의 정보는 Excel, PowerPoint 및 Word의 응용 프로그램 수준 프로젝트에 적용됩니다. 자세한 내용은 [Features Available by Office Application and Project Type](../vsto/features-available-by-office-application-and-project-type.md)을 참조하세요.  
  
### <a name="to-add-a-custom-xml-part-to-an-excel-workbook"></a>Excel 통합 문서에 사용자 지정 XML 부분을 추가하려면  
  
1.  통합 문서의 <xref:Microsoft.Office.Core.CustomXMLPart> 컬렉션에 새 <xref:Microsoft.Office.Interop.Excel._Workbook.CustomXMLParts%2A> 개체를 추가합니다. <xref:Microsoft.Office.Core.CustomXMLPart> 에는 통합 문서에 저장하려는 XML 문자열이 들어 있습니다.  
  
     다음 코드 예제에서는 지정된 통합 문서에 사용자 지정 XML 부분을 추가합니다.  
  
     [!code-vb[Trin_AddCustomXmlPartExcelAppLevel#1](../vsto/codesnippet/VisualBasic/trin_addcustomxmlpartexcelapplevel/ThisAddIn.vb#1)]
     [!code-csharp[Trin_AddCustomXmlPartExcelAppLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartExcelAppLevel/ThisAddIn.cs#1)]  
  
2.  `AddCustomXmlPartToWorkbook` 메서드를 Excel용 VSTO 추가 기능 프로젝트의 `ThisAddIn` 클래스에 추가합니다.  
  
3.  프로젝트의 다른 코드에서 메서드를 호출합니다. 예를 들어 사용자가 통합 문서를 열 때 사용자 지정 XML 부분을 만들려면 <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookOpen> 이벤트에 대한 이벤트 처리기에서 메서드를 호출합니다.  
  
### <a name="to-add-a-custom-xml-part-to-a-word-document"></a>Word 문서에 사용자 지정 XML 부분을 추가하려면  
  
1.  문서의 <xref:Microsoft.Office.Core.CustomXMLPart> 컬렉션에 새 <xref:Microsoft.Office.Interop.Word._Document.CustomXMLParts%2A> 개체를 추가합니다. <xref:Microsoft.Office.Core.CustomXMLPart> 에는 문서에 저장하려는 XML 문자열이 들어 있습니다.  
  
     다음 코드 예제에서는 지정된 문서에 사용자 지정 XML 부분을 추가합니다.  
  
     [!code-vb[Trin_AddCustomXmlPartWordAppLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartWordAppLevel/ThisAddIn.vb#1)]
     [!code-csharp[Trin_AddCustomXmlPartWordAppLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartWordAppLevel/ThisAddIn.cs#1)]  
  
2.  `AddCustomXmlPartToDocument` 메서드를 Word용 VSTO 추가 기능 프로젝트의 `ThisAddIn` 클래스에 추가합니다.  
  
3.  프로젝트의 다른 코드에서 메서드를 호출합니다. 예를 들어 사용자가 문서를 열 때 사용자 지정 XML 부분을 만들려면 <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen> 이벤트에 대한 이벤트 처리기에서 메서드를 호출합니다.  
  
### <a name="to-add-a-custom-xml-part-to-a-powerpoint-presentation"></a>PowerPoint 프레젠테이션에 사용자 지정 XML 부분을 추가하려면  
  
1.  프레젠테이션의 <xref:Microsoft.Office.Core.CustomXMLPart> 컬렉션에 새 <xref:Microsoft.Office.Interop.PowerPoint._Presentation.CustomXMLParts%2A> 개체를 추가합니다. <xref:Microsoft.Office.Core.CustomXMLPart> 에는 프레젠테이션에 저장하려는 XML 문자열이 들어 있습니다.  
  
     다음 코드 예제에서는 지정된 프레젠테이션에 사용자 지정 XML 부분을 추가합니다.  
  
     [!code-csharp[Trin_AddCustomXmlPartPowerPointAppLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartPowerPointAppLevel/ThisAddIn.cs#1)]
     [!code-vb[Trin_AddCustomXmlPartPowerPointAppLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartPowerPointAppLevel/ThisAddIn.vb#1)]  
  
2.  PowerPoint용 VSTO 추가 기능의 `AddCustomXmlPartToPresentation` 클래스에 `ThisAddIn` 메서드를 추가합니다.  
  
3.  프로젝트의 다른 코드에서 메서드를 호출합니다. 예를 들어 사용자가 프레젠테이션을 열 때 사용자 지정 XML 부분을 만들려면 <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.AfterPresentationOpen> 이벤트에 대한 이벤트 처리기에서 메서드를 호출합니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 간단한 설명을 위해 이 예제에서는 메서드에서 지역 변수로 정의된 XML 문자열을 사용합니다. 일반적으로 파일 또는 데이터베이스와 같은 외부 원본에서 XML을 가져와야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Custom XML Parts Overview](../vsto/custom-xml-parts-overview.md)   
 [방법: 문서 수준 사용자 지정에 사용자 지정 XML 부분 추가](../vsto/how-to-add-custom-xml-parts-to-document-level-customizations.md)  
  
  