---
title: '방법: 문서 수준 사용자 지정에 사용자 지정 XML 부분 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- document-level customizations [Office development in Visual Studio], custom XML parts
- Office documents [Office development in Visual Studio, custom XML parts
- Word [Office development in Visual Studio], custom XML parts
- Excel [Office development in Visual Studio], custom XML parts
- custom XML parts [Office development in Visual Studio], adding
- documents [Office development in Visual Studio], custom XML parts
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a5126e5ca6eb83df70ed03a7491fdd5d2a98912e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-custom-xml-parts-to-document-level-customizations"></a>방법: 문서 수준 사용자 지정에 사용자 지정 XML 부분 추가
  문서 수준 사용자 지정에서 사용자 지정 XML 부분을 만들어 Microsoft Office Excel 통합 문서 또는 Microsoft Office Word 문서에 XML 데이터를 저장할 수 있습니다. 자세한 내용은 [Custom XML Parts Overview](../vsto/custom-xml-parts-overview.md)을 참조하세요.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
> [!NOTE]  
>  Visual Studio는 Microsoft Office PowerPoint에 대해 문서 수준 프로젝트를 제공하지 않습니다. VSTO 추가 기능을 사용 하 여 PowerPoint 프레젠테이션에 사용자 지정 XML 부분을 추가 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 문서에서 사용 하 여 VSTO 추가 기능에 사용자 지정 XML 부분 추가](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md)합니다.  
  
### <a name="to-add-a-custom-xml-part-to-an-excel-workbook"></a>Excel 통합 문서에 사용자 지정 XML 부분을 추가하려면  
  
1.  통합 문서의 <xref:Microsoft.Office.Core.CustomXMLPart> 컬렉션에 새 <xref:Microsoft.Office.Core.CustomXMLParts> 개체를 추가합니다. <xref:Microsoft.Office.Core.CustomXMLPart> 에는 통합 문서에 저장하려는 XML 문자열이 들어 있습니다.  
  
     [!code-csharp[Trin_AddCustomXmlPartExcelDocLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartExcelDocLevel/ThisWorkbook.cs#1)]
     [!code-vb[Trin_AddCustomXmlPartExcelDocLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartExcelDocLevel/ThisWorkbook.vb#1)]  
  
2.  Excel용 문서 수준 프로젝트의 `AddCustomXmlPartToWorkbook` 클래스에 `ThisWorkbook` 메서드를 추가합니다.  
  
3.  프로젝트의 다른 코드에서 메서드를 호출합니다. 예를 들어 사용자가 통합 문서를 열 때 사용자 지정 XML 부분을 만들려면 `ThisWorkbook_Startup` 이벤트 처리기에서 메서드를 호출합니다.  
  
### <a name="to-add-a-custom-xml-part-to-a-word-document"></a>Word 문서에 사용자 지정 XML 부분을 추가하려면  
  
1.  문서의 <xref:Microsoft.Office.Core.CustomXMLPart> 컬렉션에 새 <xref:Microsoft.Office.Core.CustomXMLParts> 개체를 추가합니다. <xref:Microsoft.Office.Core.CustomXMLPart> 에는 문서에 저장하려는 XML 문자열이 들어 있습니다.  
  
     [!code-vb[Trin_AddCustomXmlPartWordDocLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartWordDocLevel/ThisDocument.vb#1)]
     [!code-csharp[Trin_AddCustomXmlPartWordDocLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartWordDocLevel/ThisDocument.cs#1)]  
  
2.  Word용 문서 수준 프로젝트의 `AddCustomXmlPartToDocument` 클래스에 `ThisDocument` 메서드를 추가합니다.  
  
3.  프로젝트의 다른 코드에서 메서드를 호출합니다. 예를 들어 사용자가 문서를 열 때 사용자 지정 XML 부분을 만들려면 `ThisDocument_Startup` 이벤트 처리기에서 메서드를 호출합니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 간단한 설명을 위해 이 예제에서는 메서드에서 지역 변수로 정의된 XML 문자열을 사용합니다. 일반적으로 파일 또는 데이터베이스와 같은 외부 원본에서 XML을 가져와야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Custom XML Parts Overview](../vsto/custom-xml-parts-overview.md)   
 [방법: VSTO 추가 기능을 사용하여 문서에 사용자 지정 XML 부분 추가](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md)  
  
  