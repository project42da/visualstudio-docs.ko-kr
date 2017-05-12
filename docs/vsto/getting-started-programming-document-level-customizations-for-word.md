---
title: "Word용 문서 수준 사용자 지정 프로그래밍 시작"
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
  - "Word 프로젝트[Visual Studio에서 Office 개발], 시작"
  - "Visual Studio의 Word 솔루션"
ms.assetid: 30593c47-1658-4fca-b9a9-36fbdf73c901
caps.latest.revision: 44
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 43
---
# Word용 문서 수준 사용자 지정 프로그래밍 시작
  하면 바로 Visual Studio 사용 하 여 Microsoft Office Word 용 문서 수준 사용자 지정을 만들기 시작 하는 경우 알고 있어야 합니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
## Word 작업을 위한 문서 수준 사용자 지정 방법 이해  
 만드는 각 Word 사용자 지정은 단일 문서를 기반으로 합니다.  사용자 지정을 사용하려면 최종 사용자가 문서를 열거나 Word 서식 파일로 문서를 만들어야 합니다.  문서에서 커서를 특정 영역으로 옮기거나 단추 및 메뉴 항목을 클릭하는 등의 이벤트가 발생하면 어셈블리에서 이벤트 처리 메서드가 호출됩니다.  문서를 닫으면 사용자 지정에서 제공하는 기능을 더 이상 Word에서 사용할 수 없습니다.  
  
 자세한 내용은 [문서 수준 사용자 지정 아키텍처](../vsto/architecture-of-document-level-customizations.md)을 참조하십시오.  
  
## Word용 문서 수준 프로젝트 만들기  
 Word용 문서 수준 사용자 지정을 만들려면 **새 프로젝트** 대화 상자에서 Word 문서 또는 Word 서식 파일 프로젝트 템플릿을 사용합니다.  이러한 템플릿에는 필수 어셈블리 참조 및 프로젝트 파일이 포함되어 있습니다.  
  
 Word용 문서 수준 프로젝트를 만드는 방법에 대한 자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)를 참조하십시오.  프로젝트 템플릿에 대한 자세한 내용은 [Office 프로젝트 템플릿 개요](../vsto/office-project-templates-overview.md)를 참조하십시오.  
  
## 호스트 항목 및 호스트 컨트롤을 사용하여 Word 문서 프로그래밍  
 *호스트 항목*과 *호스트 컨트롤*은 문서 수준 사용자 지정의 프로그래밍 모델을 제공하는 클래스입니다.  
  
 호스트 항목, 코드의 진입점을 제공 하며 호스트 컨트롤 및 Windows Forms 컨트롤의 컨테이너로 작동할 수 있습니다.  Word용 문서 수준 프로젝트에서 호스트 항목은 `ThisDocument` 클래스로 표현됩니다.  
  
 호스트 컨트롤은 콘텐츠 컨트롤, 책갈피, XML 노드 등의 네이티브 Word 개체를 기반으로 합니다.  호스트 컨트롤은 네이티브 Word 개체와 비슷한 기능을 제공하지만 호스트 컨트롤에는 새로운 이벤트, 디자이너 지원 및 데이터 바인딩 기능도 있습니다.  호스트 컨트롤은 프로젝트 코드와 IntelliSense에서 기본 개체로 나타나므로 Word 개체 모델을 탐색할 필요 없이 코드에서 직접 특정 개체를 쉽게 참조할 수 있습니다.  
  
 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [문서 수준 사용자 지정 프로그래밍](../vsto/programming-document-level-customizations.md)  
  
-   [확장된 개체를 사용하여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)  
  
-   [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)  
  
## Word의 사용자 인터페이스 사용자 지정  
 대부분의 Microsoft Office 솔루션에서는 사용자가 솔루션과 상호 작용할 수 있도록 Office 응용 프로그램의 UI\(사용자 인터페이스\)를 수정합니다.  문서 수준 사용자 지정을 사용하여 여러 가지 방법으로 Word의 UI를 수정할 수 있습니다.  예를 들어 리본 메뉴에 컨트롤을 추가할 수 있습니다 및 작업 창을 표시할 수 있습니다.  자세한 내용은 [Office UI 사용자 지정](../vsto/office-ui-customization.md)을 참조하십시오.  
  
 Visual Studio에서 프로젝트와 연결된 문서를 직접 열 수도 있습니다.  Visual Studio에서 문서를 연 경우 Word 사용자 인터페이스를 사용하여 문서를 수정할 수 있습니다.  문서는 컨트롤을 끌어 놓을 수 있는 디자인 화면으로도 사용할 수 있습니다.  자세한 내용은 [Visual Studio 환경의 Office 프로젝트](../vsto/office-projects-in-the-visual-studio-environment.md)을 참조하십시오.  
  
## 데이터에 컨트롤 바인딩  
 콘텐츠 컨트롤 및 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤은 **데이터 소스** 창에서 끌어 올 수 있는 컨트롤 목록에 포함되어 있습니다.  이러한 방식으로 콘텐츠 컨트롤 및 책갈피를 추가하면 창에서 설정한 데이터 소스에 콘텐츠 컨트롤 및 책갈피가 자동으로 바인딩되므로  코드를 작성하지 않고도 데이터베이스, 서비스 및 비즈니스 개체의 데이터를 표시할 수 있습니다.  자세한 내용은 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)을 참조하십시오.  
  
## 다음 단계  
 Word용 문서 수준 사용자 지정을 만드는 방법에 대한 자세한 내용은 [연습: Word용 첫 문서 수준 사용자 지정 만들기](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)를 참조하십시오.  이 연습에서는 Visual Studio의 Office 개발 도구와 Word 문서 수준 사용자 지정용 프로그래밍 모델에 대해 설명합니다.  
  
 몇 가지 일반적인 Word 프로젝트 작업을 다루는 항목의 목록을 보려면 [Office 프로그래밍의 일반적인 작업](../vsto/common-tasks-in-office-programming.md)을 참조하십시오.  
  
## 참고 항목  
 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [문서 수준 사용자 지정 프로그래밍](../vsto/programming-document-level-customizations.md)   
 [Word 솔루션](../vsto/word-solutions.md)   
 [연습: Word용 첫 문서 수준 사용자 지정 만들기](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)   
 [Word를 사용한 연습](../vsto/walkthroughs-using-word.md)   
 [Word 개체 모델 개요](../vsto/word-object-model-overview.md)   
 [Office 솔루션에서 코드 작성](../vsto/writing-code-in-office-solutions.md)  
  
  