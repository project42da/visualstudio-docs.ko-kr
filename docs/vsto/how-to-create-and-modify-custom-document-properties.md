---
title: "방법: 사용자 지정 문서 속성 만들기 및 수정"
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
  - "사용자 지정 문서 속성"
  - "문서[Visual Studio에서 Office 개발], 속성"
  - "문서 속성[Visual Studio에서 Office 개발]"
ms.assetid: 99d9dfaf-891f-4f3b-a580-67362afdaf34
caps.latest.revision: 47
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 46
---
# 방법: 사용자 지정 문서 속성 만들기 및 수정
  위에 나열된 Microsoft Office 응용 프로그램은 문서와 함께 저장되는 기본 제공 속성을 제공합니다. 문서와 함께 저장하려는 추가 정보가 있는 경우 사용자 지정 문서 속성을 만들고 수정할 수 있습니다.  
  
 [!INCLUDE[appliesto_docprops](../vsto/includes/appliesto-docprops-md.md)]  
  
 문서의 CustomDocumentProperties 속성을 통해 사용자 지정 속성을 사용합니다. 예를 들어 Microsoft Office Excel용 문서 수준 프로젝트에서는 `ThisWorkbook` 클래스의 <xref:Microsoft.Office.Tools.Excel.Workbook.CustomDocumentProperties%2A> 속성을 사용합니다. Excel용 VSTO 추가 기능 프로젝트에서는 <xref:Microsoft.Office.Interop.Excel.Workbook> 개체의 <xref:Microsoft.Office.Interop.Excel._Workbook.CustomDocumentProperties%2A> 속성을 사용합니다. 이러한 속성은 <xref:Microsoft.Office.Core.DocumentProperty> 개체 컬렉션인 <xref:Microsoft.Office.Core.DocumentProperties> 개체를 반환합니다. 컬렉션의 `Item` 속성을 사용하여 이름 또는 컬렉션 내의 인덱스로 특정 속성을 검색할 수 있습니다.  
  
 다음 예제에서는 Excel용 문서 수준 사용자 지정에서 사용자 지정 속성을 추가하고 값을 할당하는 방법을 보여 줍니다.  
  
 ![비디오에 링크](../vsto/media/playvideo.png "비디오에 링크") 관련 동영상 데모는 [어떻게 할까요?: Microsoft Word에서 사용자 지정 문서 속성 액세스 및 조작](http://go.microsoft.com/fwlink/?LinkId=136772)을 참조하세요.  
  
## 예제  
 [!code-csharp[Trin_VstcoreProgramming#6](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgramming/CS/ThisWorkbook.cs#6)]
 [!code-vb[Trin_VstcoreProgramming#6](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgramming/VB/ThisWorkbook.vb#6)]  
  
## 강력한 프로그래밍  
 정의되지 않은 속성에 대한 `Value` 속성에 액세스하는 동안 예외가 발생합니다.  
  
## 참고 항목  
 [VSTO 추가 기능 프로그래밍](../vsto/programming-vsto-add-ins.md)   
 [문서 수준 사용자 지정 프로그래밍](../vsto/programming-document-level-customizations.md)   
 [방법: 문서 속성에서 읽기 및 문서 속성에 쓰기](../vsto/how-to-read-from-and-write-to-document-properties.md)  
  
  