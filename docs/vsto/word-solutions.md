---
title: Word 솔루션 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], Word
- Office projects [Office development in Visual Studio], Word
- application-level add-ins [Office development in Visual Studio], Word
- Word [Office development in Visual Studio]
- projects [Office development in Visual Studio], Word
- Word [Office development in Visual Studio], about Word solutions
- Office solutions [Office development in Visual Studio], Word
- Word [Office development in Visual Studio], application-level add-ins
- documents [Office development in Visual Studio], Word
- Office development in Visual Studio, Word solutions
- add-ins [Office development in Visual Studio], Word
- Word [Office development in Visual Studio], document-level customizations
- user interfaces [Office development in Visual Studio], Word
- Office documents [Office development in Visual Studio, Word
- document-level customizations [Office development in Visual Studio], Word
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 44cd5633d7cc03fb78c6508c24a117a0500fa142
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="word-solutions"></a>Word 솔루션
  Visual Studio에서는 Microsoft Office Word용 VSTO 추가 기능 및 문서 수준 사용자 지정을 만드는 데 사용할 수 있는 프로젝트 템플릿을 제공합니다. 이러한 솔루션을 사용하여 Word를 자동화하고, Word 기능을 확장한 다음 Word UI(사용자 인터페이스)를 사용자 지정할 수 있습니다. 문서 수준 사용자 지정과 VSTO 추가 기능 간의 차이점에 대 한 자세한 내용은 참조 [Office 솔루션 개발 개요 &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)합니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
> [!NOTE]  
>  Office 환경을 확장 하는 솔루션을 개발에 관심이 [여러 플랫폼](https://dev.office.com/add-in-availability)? 체크 아웃 새 [Office 추가 기능 모델](https://dev.office.com/docs/add-ins/overview/office-add-ins)합니다. Office 추가 기능에서 VSTO 추가 기능 및 솔루션에 비해 적을 있고 거의 모든 웹 프로그래밍 HTML5, JavaScript, CSS3 및 XML 등의 기술을 사용 하 여 빌드할 수 있습니다.  
  
 이 항목에서는 다음 내용에 대해 설명합니다.  
  
-   [Word 자동화](#automating)  
  
-   [Word용 문서 수준 사용자 지정 개발](#doclevel)  
  
-   [Word용 VSTO 추가 기능 개발](#applevel)  
  
-   [Word의 사용자 인터페이스 사용자 지정](#UI)  
  
##  <a name="automating"></a> Word 자동화  
 Word 개체 모델은 Word 자동화에 사용할 수 있는 다양한 형식을 노출합니다. 예를 들어 프로그래밍 방식으로 표를 만들고, 문서의 서식을 지정하고, 범위 및 단락의 텍스트를 설정할 수 있습니다. 자세한 내용은 [Word Object Model Overview](../vsto/word-object-model-overview.md)을 참조하세요.  
  
 Visual Studio에서 Word 솔루션을 개발하는 경우 솔루션에서 *호스트 항목* 및 *호스트 컨트롤* 을 사용할 수도 있습니다. Word 개체 모델에서 일반적으로 사용되는 특정 개체(예: <xref:Microsoft.Office.Interop.Word.Document> 및 <xref:Microsoft.Office.Interop.Word.ContentControl> )를 확장하는 개체입니다. 확장된 개체는 기반이 되는 Word 개체처럼 동작하지만 개체에 이벤트 및 데이터 바인딩 기능을 더 추가합니다. 자세한 내용은 [Automating Word by Using Extended Objects](../vsto/automating-word-by-using-extended-objects.md)을 참조하세요.  
  
##  <a name="doclevel"></a> Developing Document-Level Customizations for Word  
 Microsoft Office Word용 문서 수준 사용자 지정은 특정 문서와 연결된 어셈블리로 구성됩니다. 어셈블리는 일반적으로 UI를 사용자 지정하고 Word를 자동화하여 문서를 확장합니다. Word 자체와 연결된 VSTO 추가 기능과 달리 사용자 지정에 구현하는 기능은 연결된 문서가 Word에서 열려 있는 경우에만 사용할 수 있습니다.  
  
 Word용 문서 수준 사용자 지정 프로젝트를 만들려면 Visual Studio의 **새 프로젝트** 대화 상자에서 Word 문서 또는 Word 서식 파일 프로젝트 템플릿을 사용합니다. 자세한 내용은 [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하세요.  
  
 문서 수준 사용자 지정이 작동하는 방법에 대한 자세한 내용은 [Architecture of Document-Level Customizations](../vsto/architecture-of-document-level-customizations.md)를 참조하세요.  
  
### <a name="word-customization-programming-model"></a>Word 사용자 지정 프로그래밍 모델  
 Word용 문서 수준 프로젝트를 만드는 경우 Visual Studio는 솔루션의 기초가 되는 `ThisDocument`라는 클래스를 생성합니다. 이 클래스는 솔루션과 연결된 문서를 나타내고 코드를 작성하기 위한 시작점을 제공합니다.  
  
 에 대 한 자세한 내용은 `ThisDocument` 클래스 및 문서 수준 프로젝트에서 사용할 수 있는 기타 기능 참조 [문서 수준 사용자 지정 프로그래밍](../vsto/programming-document-level-customizations.md)합니다.  
  
##  <a name="applevel"></a> Word용 VSTO 추가 기능 개발  
 Microsoft Office Word용 VSTO 추가 기능은 Word에서 로드되는 어셈블리로 구성됩니다. 어셈블리는 일반적으로 UI를 사용자 지정하고 Word를 자동화하여 Word를 확장합니다. 특정 문서와 연결된 문서 수준 사용자 지정과 달리 VSTO 추가 기능에서 구현하는 기능은 단일 문서로 제한되지 않습니다.  
  
 Word용 VSTO 추가 기능 프로젝트를 만들려면 Visual Studio의 **새 프로젝트** 대화 상자에서 Word 추가 기능 프로젝트 템플릿을 사용합니다. 자세한 내용은 [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하세요.  
  
 VSTO 추가 기능이 작동하는 방법에 대한 일반적인 내용은 [Architecture of VSTO Add-ins](../vsto/architecture-of-vsto-add-ins.md)를 참조하세요.  
  
### <a name="word-add-in-programming-model"></a>Word 추가 기능 프로그래밍 모델  
 Word VSTO 추가 기능 프로젝트를 만드는 경우 Visual Studio는 솔루션의 기초가 되는 `ThisAddIn`이라는 클래스를 생성합니다. 이 클래스는 코드를 작성하기 위한 시작점을 제공하고 VSTO 추가 기능에 Word의 개체 모델도 노출합니다.  
  
 에 대 한 자세한 내용은 `ThisAddIn` 클래스와는 VSTO 추가 기능에서 사용할 수 있는 기타 기능 참조 [VSTO 추가 기능 프로그래밍](../vsto/programming-vsto-add-ins.md)합니다.  
  
##  <a name="UI"></a> Customizing the User Interface of Word  
 Word의 사용자 인터페이스를 사용자 지정하는 여러 가지 방법이 있습니다. 모든 프로젝트 형식에서 사용할 수 있는 옵션도 있고, VSTO 추가 기능 또는 문서 수준 사용자 지정에만 사용할 수 있는 옵션도 있습니다.  
  
### <a name="options-for-all-project-types"></a>모든 프로젝트 형식에 대한 옵션  
 다음 표에서는 문서 수준 사용자 지정과 VSTO 추가 기능에서 모두 사용할 수 있는 사용자 지정 옵션을 보여 줍니다.  
  
|작업|추가 정보|  
|----------|--------------------------|  
|리본 메뉴 사용자 지정|[리본 개요](../vsto/ribbon-overview.md)|  
|문서 수준 사용자 지정에 대한 사용자 지정 문서 또는 VSTO 추가 기능에 대한 열려 있는 문서에 Windows Forms 컨트롤 또는 확장된 Word 컨트롤 추가|[방법: Office 문서에 Windows Forms 컨트롤 추가](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)<br /><br /> [방법: Word 문서에 Content 컨트롤 추가](../vsto/how-to-add-content-controls-to-word-documents.md).<br /><br /> [방법: Word 문서에 Bookmark 컨트롤 추가](../vsto/how-to-add-bookmark-controls-to-word-documents.md)|  
  
### <a name="options-for-document-level-customizations"></a>문서 수준 사용자 지정에 대한 옵션  
 다음 표에서는 문서 수준 사용자 지정에만 사용할 수 있는 사용자 지정 옵션을 보여 줍니다.  
  
|작업|추가 정보|  
|----------|--------------------------|  
|문서에 작업 창 추가|[작업창 개요](../vsto/actions-pane-overview.md)<br /><br /> [방법: Word 문서 또는 Excel 통합 문서에 작업창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)|  
|확장된 XMLNode 및 XMLNodes 컨트롤을 문서 화면에 추가합니다.|[방법: Word 문서에 XMLNode 컨트롤 추가](../vsto/how-to-add-xmlnode-controls-to-word-documents.md).<br /><br /> [방법: Word 문서에 XMLNodes 컨트롤 추가](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md)|  
  
### <a name="options-for-vsto-add-ins"></a>VSTO 추가 기능에 대한 옵션  
 다음 표에서는 VSTO 추가 기능에만 사용할 수 있는 사용자 지정 옵션을 보여 줍니다.  
  
|작업|추가 정보|  
|----------|--------------------------|  
|사용자 지정 작업창을 만듭니다.|[사용자 지정 작업창](../vsto/custom-task-panes.md)|  
  
### <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[Word Object Model Overview](../vsto/word-object-model-overview.md)|Word 개체 모델에서 제공하는 주요 형식에 대해 설명합니다.|  
|[Automating Word by Using Extended Objects](../vsto/automating-word-by-using-extended-objects.md)|Word 솔루션에서 사용할 수 있는 확장된 개체( [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서 제공)에 대한 정보를 제공합니다.|  
|[Office 문서의 Windows Forms 컨트롤 개요](../vsto/windows-forms-controls-on-office-documents-overview.md)|Word 문서에 Windows Forms 컨트롤을 추가할 수 있는 방법을 설명합니다.|  
|[연습: Word용 첫 문서 수준 사용자 지정 만들기](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)|Word용 기본 문서 수준 사용자 지정을 만드는 방법을 보여 줍니다.|  
|[연습: Word용 첫 VSTO 추가 기능 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)|Word용 기본 VSTO 추가 기능을 만드는 방법을 보여 줍니다.|  
|[연습: 런타임에 VSTO 추가 기능의 문서에 컨트롤 추가](../vsto/walkthrough-adding-controls-to-a-document-at-run-time-in-a-vsto-add-in.md)|VSTO 추가 기능을 사용하여 런타임에 Windows Forms 단추 및 <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 을 문서에 추가하는 방법을 설명합니다.|  
|[Office 개발의 Word 2010](http://go.microsoft.com/fwlink/?LinkId=199020)|Visual Studio를 사용한 Office 개발에 국한되지 않고 Word 솔루션을 개발하는 방법에 대한 문서와 참조 설명서에 대한 링크를 제공합니다.|  
  
  