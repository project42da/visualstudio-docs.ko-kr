---
title: "방법: 문서 속성에서 읽기 및 문서 속성에 쓰기"
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
  - "Word[Visual Studio에서 Office 개발], 문서 속성"
  - "문서[Visual Studio에서 Office 개발], 속성"
  - "문서 속성[Visual Studio에서 Office 개발]"
  - "Excel[Visual Studio에서 Office 개발], 문서 속성"
ms.assetid: e9ef9fa3-36b9-48fb-8148-f5152463c03c
caps.latest.revision: 54
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 53
---
# 방법: 문서 속성에서 읽기 및 문서 속성에 쓰기
  문서와 함께 문서 속성을 저장할 수 있습니다. Office 응용 프로그램은 작성자, 제목 및 주제와 같은 다양한 기본 제공 속성을 제공합니다. 이 항목에서는 Microsoft Office Excel 및 Microsoft Office Word에서 문서 속성을 설정하는 방법을 보여 줍니다.  
  
 ![비디오에 링크](~/docs/data-tools/media/playvideo.gif "비디오에 링크") 관련 동영상 데모는 [어떻게 할까요?: Microsoft Word에서 사용자 지정 문서 속성 액세스 및 조작](http://go.microsoft.com/fwlink/?LinkId=136772)을 참조하세요.  
  
 [!INCLUDE[appliesto_docprops](../vsto/includes/appliesto-docprops-md.md)]  
  
## Excel에서 문서 속성 설정  
 Excel에서 기본 제공 속성으로 작업하려면 다음 속성을 사용합니다.  
  
-   문서 수준 프로젝트에서는 `ThisWorkbook` 클래스의 <xref:Microsoft.Office.Tools.Excel.Workbook.BuiltinDocumentProperties%2A> 속성을 사용합니다.  
  
-   VSTO 추가 기능 프로젝트에서는 <xref:Microsoft.Office.Interop.Excel.Workbook> 개체의 <xref:Microsoft.Office.Interop.Excel._Workbook.BuiltinDocumentProperties%2A> 속성을 사용합니다.  
  
 이러한 속성은 <xref:Microsoft.Office.Core.DocumentProperty> 개체 컬렉션인 <xref:Microsoft.Office.Core.DocumentProperties> 개체를 반환합니다. 컬렉션의 `Item` 속성을 사용하여 이름 또는 컬렉션 내의 인덱스로 특정 속성을 검색할 수 있습니다.  
  
 다음 코드 예제에서는 문서 수준 프로젝트에서 기본 제공 **Revision Number** 속성을 변경하는 방법을 보여 줍니다.  
  
#### Excel에서 수정 번호 속성을 변경하려면  
  
1.  기본 제공 문서 속성을 변수에 할당합니다.  
  
     [!code-csharp[Trin_VstcoreProgramming#7](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgramming/CS/ThisWorkbook.cs#7)]
     [!code-vb[Trin_VstcoreProgramming#7](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgramming/VB/ThisWorkbook.vb#7)]  
  
2.  `Revision Number` 속성을 1씩 증가시킵니다.  
  
     [!code-csharp[Trin_VstcoreProgramming#8](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgramming/CS/ThisWorkbook.cs#8)]
     [!code-vb[Trin_VstcoreProgramming#8](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgramming/VB/ThisWorkbook.vb#8)]  
  
## Word에서 문서 속성 설정  
 Word에서 기본 제공 속성으로 작업하려면 다음 속성을 사용합니다.  
  
-   문서 수준 프로젝트에서는 `ThisDocument` 클래스의 <xref:Microsoft.Office.Tools.Word.Document.BuiltInDocumentProperties%2A> 속성을 사용합니다.  
  
-   VSTO 추가 기능 프로젝트에서는 <xref:Microsoft.Office.Interop.Word.Document> 개체의 <xref:Microsoft.Office.Interop.Word._Document.BuiltInDocumentProperties%2A> 속성을 사용합니다.  
  
 이러한 속성은 <xref:Microsoft.Office.Core.DocumentProperty> 개체 컬렉션인 <xref:Microsoft.Office.Core.DocumentProperties> 개체를 반환합니다. 컬렉션의 `Item` 속성을 사용하여 이름 또는 컬렉션 내의 인덱스로 특정 속성을 검색할 수 있습니다.  
  
 다음 코드 예제에서는 문서 수준 프로젝트에서 기본 제공 **Subject** 속성을 변경하는 방법을 보여 줍니다.  
  
#### Subject 속성을 변경하려면  
  
1.  기본 제공 문서 속성을 변수에 할당합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingWord#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingWord/CS/ThisDocument.cs#1)]
     [!code-vb[Trin_VstcoreProgrammingWord#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingWord/VB/ThisDocument.vb#1)]  
  
2.  `Subject` 속성을 "Whitepaper"로 변경합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingWord#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingWord/CS/ThisDocument.cs#2)]
     [!code-vb[Trin_VstcoreProgrammingWord#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingWord/VB/ThisDocument.vb#2)]  
  
## 강력한 프로그래밍  
 예제에서는 Excel용 문서 수준 프로젝트의 `ThisWorkbook` 클래스 및 Word용 문서 수준 프로젝트의 `ThisDocument` 클래스에서 코드를 작성했다고 가정합니다.  
  
 Word 및 Excel과 해당 개체로 작업 중이지만 Microsoft Office에서 사용 가능한 기본 제공 문서 속성 목록을 제공합니다. 정의되지 않은 속성에 액세스하려고 하면 예외가 발생합니다.  
  
## 참고 항목  
 [VSTO 추가 기능 프로그래밍](../vsto/programming-vsto-add-ins.md)   
 [문서 수준 사용자 지정 프로그래밍](../vsto/programming-document-level-customizations.md)   
 [방법: 사용자 지정 문서 속성 만들기 및 수정](../vsto/how-to-create-and-modify-custom-document-properties.md)  
  
  