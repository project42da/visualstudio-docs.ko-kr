---
title: '방법: 사용자 지정 문서 속성 만들기 및 수정 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom document properties
- documents [Office development in Visual Studio], properties
- document properties [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8c997fbe764ba355d16def278c9beda8c177faed
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-and-modify-custom-document-properties"></a>방법: 사용자 지정 문서 속성 만들기 및 수정
  위에 나열된 Microsoft Office 응용 프로그램은 문서와 함께 저장되는 기본 제공 속성을 제공합니다. 문서와 함께 저장하려는 추가 정보가 있는 경우 사용자 지정 문서 속성을 만들고 수정할 수 있습니다.  
  
 [!INCLUDE[appliesto_docprops](../vsto/includes/appliesto-docprops-md.md)]  
  
 사용자 지정 속성을 사용 하려면 문서를 사용 합니다. 예를 들어 Microsoft Office Excel용 문서 수준 프로젝트에서는 <xref:Microsoft.Office.Tools.Excel.Workbook.CustomDocumentProperties%2A> 클래스의 `ThisWorkbook` 속성을 사용합니다. Excel용 VSTO 추가 기능 프로젝트에서는 <xref:Microsoft.Office.Interop.Excel._Workbook.CustomDocumentProperties%2A> 개체의 <xref:Microsoft.Office.Interop.Excel.Workbook> 속성을 사용합니다. 이러한 속성은 <xref:Microsoft.Office.Core.DocumentProperties> 개체 컬렉션인 <xref:Microsoft.Office.Core.DocumentProperty> 개체를 반환합니다. 컬렉션의 `Item` 속성을 사용하여 이름 또는 컬렉션 내의 인덱스로 특정 속성을 검색할 수 있습니다.  
  
 다음 예제에서는 Excel용 문서 수준 사용자 지정에서 사용자 지정 속성을 추가하고 값을 할당하는 방법을 보여 줍니다.  
  
 ![비디오에 링크](../vsto/media/playvideo.gif "비디오에 링크") 관련된 동영상 데모를 참조 하십시오. [어떻게 수행 할까요 속성 액세스 및 조작 사용자 지정 문서 Microsoft Word에서?](http://go.microsoft.com/fwlink/?LinkId=136772)합니다.  
  
## <a name="example"></a>예제  
 [!code-vb[Trin_VstcoreProgramming#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/ThisWorkbook.vb#6)]
 [!code-csharp[Trin_VstcoreProgramming#6](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/ThisWorkbook.cs#6)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 정의되지 않은 속성에 대한 `Value` 속성에 액세스하는 동안 예외가 발생합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)   
 [문서 수준 사용자 지정 프로그래밍](../vsto/programming-document-level-customizations.md)   
 [방법: 문서 속성에서 읽기 및 문서 속성에 쓰기](../vsto/how-to-read-from-and-write-to-document-properties.md)  
  
  