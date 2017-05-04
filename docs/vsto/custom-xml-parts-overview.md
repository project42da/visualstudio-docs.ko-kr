---
title: "사용자 지정 XML 부분 개요 | Microsoft Docs"
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
  - "사용자 지정 XML 부분[Visual Studio에서 Office 개발]"
  - "사용자 지정 XML 부분[Visual Studio에서 Office 개발], 정보"
  - "데이터[Visual Studio에서 Office 개발], 사용자 지정 XML 부분"
  - "문서[Visual Studio에서 Office 개발], 사용자 지정 XML 부분"
  - "문서에 XML 데이터 포함[Visual Studio에서 Office 개발]"
  - "Excel[Visual Studio에서 Office 개발], 사용자 지정 XML 부분"
  - "Office 문서[Visual Studio에서 Office 개발], 사용자 지정 XML 부분"
  - "Office Open XML 형식[Visual Studio에서 Office 개발]"
  - "Word[Visual Studio에서 Office 개발], 사용자 지정 XML 부분"
  - "XML[Visual Studio에서 Office 개발], 사용자 지정 XML 부분"
  - "XML 파일 형식[Visual Studio에서 Office 개발]"
  - "XML 부분[Visual Studio에서 Office 개발]"
ms.assetid: a14119dc-59e8-4614-94f1-08c92bdf7300
caps.latest.revision: 33
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 32
---
# 사용자 지정 XML 부분 개요
  일부 Microsoft Office 응용 프로그램에 대한 문서에 XML 데이터를 포함할 수 있습니다.  문서에 XML 데이터를 포함하는 경우 해당 데이터에 *사용자 지정 XML 부분*이라는 이름이 지정됩니다.  
  
 Visual Studio에서 VSTO 추가 기능 또는 문서 수준 솔루션을 사용하여 문서에 사용자 지정 XML 부분을 만들고 수정할 수 있습니다.  사용자 지정 XML 부분을 만들고 수정하기 위해 Microsoft Office 응용 프로그램을 시작할 필요는 없습니다.  
  
 **적용 대상:** 이 항목의 정보는 Excel, PowerPoint 및 Word의 문서 수준 프로젝트 및 VSTO 추가 기능 프로젝트에 적용됩니다.  자세한 내용은 [Office 응용 프로그램 및 프로젝트 형식에 따라 사용 가능한 기능](../vsto/features-available-by-office-application-and-project-type.md)을 참조하세요.  
  
> [!NOTE]  
>  또한 visual Studio를 사용하여 문서 수준 사용자 지정에 데이터 개체를 캐시할 수 있습니다.  몇 가지 유사점은 있지만 이 기능은 사용자 지정 XML 부분과 다릅니다.  자세한 내용은 [문서 수준 사용자 지정의 캐시된 데이터](../vsto/cached-data-in-document-level-customizations.md)을 참조하세요.  
  
## 사용자 지정 XML 부분 이해  
 사용자 지정 XML 부분은 Open XML 형식과 함께 2007 Microsoft Office System에서 도입되었습니다.  이러한 형식에는 Excel, PowerPoint 및 Word에 대한 새 XML 기반 파일 형식\(예: .xlsx, .pptx 및 .docx\)이 포함됩니다.  이러한 형식의 문서는 ZIP 보관 파일의 폴더에 구성된 XML 파일\(*XML 부분*이라고도 함\)로 이루어져 있습니다.  대다수의 XML 부분은 문서의 구조 및 상태를 정의하는 데 도움이 되는 기본 제공 부분입니다.  그러나 문서에는 임의의 XML 데이터를 문서에 저장하는 데 사용할 수 있는 사용자 지정 XML 부분도 포함될 수 있습니다.  
  
 XML 파일 형식을 사용하면 응용 프로그램이 이전 이진 파일 형식\(예: .xls, .ppt 및 .doc\)에서 사용할 수 없는 방식으로 문서 작업을 수행할 수 있습니다.  ZIP 보관 파일을 읽을 수 있는 응용 프로그램은 Microsoft Office가 설치되어 있지 않아도 문서의 내용을 검사하고 수정할 수 있습니다.  
  
 Open XML 및 사용자 지정 XML 부분의 구조에 대한 자세한 내용은 다음 문서를 참조하세요.  
  
-   [Office\(2007\) Open XML 파일 형식 소개](http://msdn.microsoft.com/ko-kr/96018532-f62c-4da7-bbff-16b96a483fbf)  
  
-   [방법: Open XML 형식의 문서 조작](http://msdn.microsoft.com/ko-kr/c989d4e2-053d-4e1f-83be-257c608b343f)  
  
-   [연습: Word 2007 XML 형식](http://msdn.microsoft.com/ko-kr/fc1afcb2-27fb-4608-9f29-11b7bd23ea4a)  
  
-   [Open XML 형식을 사용하여 Word 2007 문서 작성](http://msdn.microsoft.com/ko-kr/59a46f4e-5a5a-4dac-86e5-7dfd43330766)  
  
> [!NOTE]  
>  Excel, Word 및 PowerPoint를 통해 이진 파일 형식으로 저장된 문서에서 사용자 지정 XML 부분을 사용할 수 있습니다.  그러나 문서가 이진 형식으로 저장된 경우 Microsoft Office 응용 프로그램을 시작하지 않고 사용자 지정 XML 부분을 추가하거나 수정할 수 없습니다.  
  
## 사용자 지정 XML 부분 만들기 및 수정  
 문서가 Office 응용 프로그램에서 열려 있거나 문서가 닫혀 있는 경우 Microsoft Office가 설치되어 있지 않아도 사용자 지정 XML 부분을 만들거나 수정할 수 있습니다.  
  
### Office 응용 프로그램이 실행되는 동안 XML 부분 수정  
 문서 수준 사용자 지정 또는 VSTO 추가 기능을 사용하여 사용자 지정 XML 부분으로 작업할 수 있습니다.  문서 수준 사용자 지정을 사용하는 경우 일반적으로 사용자 지정 문서에 있는 사용자 지정 XML 부분으로 작업합니다.  VSTO 추가 기능을 사용하는 경우 응용 프로그램에서 열려 있는 문서에서 사용자 지정 XML 부분을 만들거나 수정할 수 있습니다.  
  
 Visual Studio를 사용하여 사용자 지정 XML 부분을 만들려면 문서의 <xref:Microsoft.Office.Core.CustomXMLParts> 컬렉션에 새로운 <xref:Microsoft.Office.Core.CustomXMLPart>를 추가합니다.  자세한 내용은 다음 항목을 참조하세요.  
  
-   [방법: 문서 수준 사용자 지정에 사용자 지정 XML 부분 추가](../vsto/how-to-add-custom-xml-parts-to-document-level-customizations.md)  
  
-   [방법: VSTO 추가 기능을 사용하여 문서에 사용자 지정 XML 부분 추가](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md)  
  
### Office 응용 프로그램을 시작하지 않고 XML 부분 수정  
 Excel, PowerPoint 또는 Word를 시작하지 않고 사용자 지정 XML 부분을 추가하거나 수정할 수 있습니다.  서버와 같이 Microsoft Office 응용 프로그램이 설치되어 있지 않은 컴퓨터에서 문서의 XML 데이터로 작업하려는 경우에 유용합니다.  
  
 Microsoft Office를 시작하지 않고 사용자 지정 XML 부분을 추가하려면 Open XML SDK의 클래스를 사용합니다.  이러한 클래스는 Office 문서와 관련된 Open XML 콘텐츠에 대한 액세스를 제공하도록 설계되었습니다.  예를 들어 Excel 통합 문서에 사용자 지정 XML 부분을 추가하려면 [WorkbookPart](http://msdn.microsoft.com/ko-kr/d011e6f4-77dd-d02d-66ef-dc4a9e7b26f2) 개체의 [AddNewPart\<T\>](http://msdn.microsoft.com/ko-kr/47c348c0-77ab-a504-5097-bcd6a213921a) 메서드를 사용합니다.  자세한 내용은 [Open XML SDK 2.0](http://msdn.microsoft.com/ko-kr/f6a9ae68-7989-4208-97f5-3c945137a0ab)을 참조하세요.  
  
## Word 콘텐츠 컨트롤에 사용자 지정 XML 부분 바인딩  
 사용자 지정 XML 부분의 요소에 Word 솔루션의 콘텐츠 컨트롤을 바인딩할 수 있습니다.  콘텐츠 컨트롤이 사용자 지정 XML 부분에 바인딩된 경우 사용자 지정 XML 부분의 데이터가 콘텐츠 컨트롤의 UI\(사용자 인터페이스\)에 표시됩니다.  사용자가 컨트롤의 텍스트를 편집하는 경우 해당 XML 요소가 자동으로 업데이트됩니다.  마찬가지로, 사용자 지정 XML 부분의 요소 값이 변경되는 경우 XML 요소에 바인딩된 콘텐츠 컨트롤에 새 데이터가 표시됩니다.  자세한 내용은 [콘텐츠 컨트롤](../vsto/content-controls.md)을 참조하세요.  
  
## 참고 항목  
 [문서 수준 사용자 지정의 XML 스키마 및 데이터](../vsto/xml-schemas-and-data-in-document-level-customizations.md)   
 [방법: 문서 수준 사용자 지정에 사용자 지정 XML 부분 추가](../vsto/how-to-add-custom-xml-parts-to-document-level-customizations.md)   
 [방법: VSTO 추가 기능을 사용하여 문서에 사용자 지정 XML 부분 추가](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md)   
 [콘텐츠 컨트롤](../vsto/content-controls.md)   
 [연습: 콘텐츠 컨트롤을 사용자 지정 XML 부분에 바인딩](../vsto/walkthrough-binding-content-controls-to-custom-xml-parts.md)  
  
  