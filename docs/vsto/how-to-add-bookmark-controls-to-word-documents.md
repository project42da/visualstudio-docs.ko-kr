---
title: "방법: Word 문서에 책갈피 컨트롤 추가"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VST.Bookmark.Dialog"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "책갈피 컨트롤, 문서에 추가"
  - "책갈피 컨트롤 만들기 대화 상자"
  - "컨트롤[Visual Studio에서 Office 개발], 문서에 추가"
ms.assetid: 2940704e-31f5-4486-854e-76298a9e2ee4
caps.latest.revision: 52
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 51
---
# 방법: Word 문서에 책갈피 컨트롤 추가
  문서 수준 프로젝트에서 디자인 타임 또는 런타임에 프로젝트의 문서에 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 추가할 수 있습니다. VSTO 추가 기능 프로젝트에서는 런타임에 열려 있는 임의 문서에 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 추가할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 이 항목에서는 다음 작업에 대해 설명합니다.  
  
-   [디자인 타임에 책갈피 컨트롤 추가](#designtime)  
  
-   [런타임에 문서 수준 프로젝트에 책갈피 컨트롤 추가](#runtimedoclevel)  
  
-   [런타임에 VSTO 추가 기능 프로젝트에서 책갈피 컨트롤 추가](#runtimeaddin)  
  
 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤에 대한 자세한 내용은 [책갈피 컨트롤](../vsto/bookmark-control.md)을 참조하세요.  
  
##  <a name="designtime"></a> 디자인 타임에 책갈피 컨트롤 추가  
 디자인 타임에 문서 수준 프로젝트의 문서에 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 추가하는 여러 가지 방법이 있습니다.  
  
-   Visual Studio **도구 상자**에서.  
  
     **도구 상자**에서 문서로 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 끌어올 수 있습니다. 이미 **도구 상자**를 사용하여 Windows Forms 컨트롤을 문서에 추가 중인 경우 이 방법을 선택하는 것이 좋습니다.  
  
-   Word 내에서.  
  
     네이티브 책갈피를 추가하는 것과 동일한 방식으로 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 문서에 추가할 수 있습니다. 이런 방식으로 추가하는 경우 컨트롤을 만들 때 이름을 지정할 수 있다는 이점이 있습니다.  
  
-   **데이터 소스** 창에서.  
  
     **데이터 소스** 창에서 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 문서로 끌어올 수 있습니다. 이 기능은 동시에 컨트롤을 데이터에 바인딩하려는 경우에 유용합니다.**데이터 소스** 창에서 Windows Form 컨트롤을 추가하는 것과 동일한 방법으로 호스트 컨트롤을 추가할 수 있습니다. 자세한 내용은 [데이터 바인딩 및 Windows Forms](http://msdn.microsoft.com/library/419aac5e-819b-4aad-88b0-73a2f8c0bd27)을 참조하십시오.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
#### 도구 상자에서 문서에 책갈피 컨트롤을 추가하려면  
  
1.  **도구 상자**를 열고 **Word 컨트롤** 탭을 클릭합니다.  
  
2.  <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 문서로 끌어옵니다.  
  
     **책갈피 추가** 대화 상자가 나타납니다.  
  
3.  책갈피에 포함하려는 텍스트 또는 기타 항목을 선택합니다.  
  
4.  **확인**을 클릭합니다.  
  
     기본 책갈피 이름을 유지하지 않으려면 **속성** 창에서 이름을 변경할 수 있습니다.  
  
#### Word에서 문서에 책갈피 컨트롤을 추가하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디자이너에 호스트된 문서에서 책갈피를 추가하려는 위치에 커서를 놓거나 책갈피로 묶으려는 텍스트를 선택합니다.  
  
2.  리본 메뉴의 **삽입** 탭에 있는 **링크** 그룹에서 **책갈피** 단추를 클릭합니다.  
  
3.  **책갈피** 대화 상자에서 새 책갈피의 이름을 입력하고 **추가**를 클릭합니다.  
  
##  <a name="runtimedoclevel"></a> 런타임에 문서 수준 프로젝트에 책갈피 컨트롤 추가  
 프로젝트에서 <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> 클래스의 `ThisDocument` 속성 메서드를 사용하여 프로그래밍 방식으로 런타임에 문서에 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 추가할 수 있습니다. 다음과 같은 방법으로 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 추가하는 데 사용할 수 있는 두 개의 메서드 오버로드가 있습니다.  
  
-   지정된 범위에 <xref:Microsoft.Office.Tools.Word.Bookmark>를 추가합니다.  
  
-   문서의 네이티브 책갈피\(즉, <xref:Microsoft.Office.Interop.Word.Bookmark>\)를 기반으로 하는 <xref:Microsoft.Office.Tools.Word.Bookmark>를 추가합니다.  
  
 동적으로 생성된 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤은 문서를 닫을 때 문서에 유지되지 않습니다. 그러나 네이티브 <xref:Microsoft.Office.Interop.Word.Bookmark>는 문서에 남아 있습니다. 다음에 문서를 열 때 네이티브 책갈피를 기반으로 하는 <xref:Microsoft.Office.Tools.Word.Bookmark>를 다시 만들 수 있습니다. 자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)을 참조하십시오.  
  
#### 프로그래밍 방식으로 문서에 책갈피 컨트롤을 추가하려면  
  
1.  프로젝트의 `ThisDocument_Startup` 이벤트 처리기에서 다음 코드를 삽입하여 문서의 첫 번째 단락에 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 추가합니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsWord#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsWord/CS/ThisDocument.cs#1)]
     [!code-vb[Trin_VstcoreHostControlsWord#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsWord/VB/ThisDocument.vb#1)]  
  
    > [!NOTE]  
    >  기존 <xref:Microsoft.Office.Interop.Word.Bookmark>에서 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 만들려는 경우 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddBookmark%2A> 메서드를 사용하고 기존 <xref:Microsoft.Office.Interop.Word.Bookmark>를 전달합니다.  
  
##  <a name="runtimeaddin"></a> 런타임에 VSTO 추가 기능 프로젝트에서 책갈피 컨트롤 추가  
 VSTO 추가 기능을 사용하여 프로그래밍 방식으로 런타임에 열려 있는 문서에 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 추가할 수 있습니다. 이렇게 하려면 열려 있는 문서를 기반으로 하는 <xref:Microsoft.Office.Tools.Word.Document> 호스트 항목을 생성한 다음 이 호스트 항목의 <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> 속성 메서드를 사용합니다. 다음과 같은 방법으로 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 추가하는 데 사용할 수 있는 두 개의 메서드 오버로드가 있습니다.  
  
-   지정된 범위에 <xref:Microsoft.Office.Tools.Word.Bookmark>를 추가합니다.  
  
-   문서의 네이티브 책갈피\(즉, <xref:Microsoft.Office.Interop.Word.Bookmark>\)를 기반으로 하는 <xref:Microsoft.Office.Tools.Word.Bookmark>를 추가합니다.  
  
 동적으로 생성된 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤은 문서를 닫을 때 문서에 유지되지 않습니다. 그러나 네이티브 <xref:Microsoft.Office.Interop.Word.Bookmark>는 문서에 남아 있습니다. 다음에 문서를 열 때 네이티브 책갈피를 기반으로 하는 <xref:Microsoft.Office.Tools.Word.Bookmark>를 다시 만들 수 있습니다. 자세한 내용은 [Office 문서에서 동적 컨트롤 유지](../vsto/persisting-dynamic-controls-in-office-documents.md)을 참조하세요.  
  
 VSTO 추가 기능 프로젝트에서 호스트 항목을 생성하는 방법에 대한 자세한 내용은 [런타임에 VSTO 추가 기능에서 Word 문서 및 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)을 참조하세요.  
  
#### 지정된 범위에 책갈피 컨트롤을 추가하려면  
  
1.  <xref:Microsoft.Office.Tools.Word.ControlCollection.AddBookmark%2A> 메서드를 사용하고 <xref:Microsoft.Office.Tools.Word.Bookmark>를 추가하려는 <xref:Microsoft.Office.Interop.Word.Range>를 전달합니다.  
  
     다음 코드 예제에서는 활성 문서의 시작 부분에 새 <xref:Microsoft.Office.Tools.Word.Bookmark>를 추가합니다. 이 예제를 사용하려면 Word VSTO 추가 기능 프로젝트의 `ThisAddIn_Startup` 이벤트 처리기에서 코드를 실행합니다.  
  
     [!code-csharp[Trin_WordAddInDynamicControls#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/CS/ThisAddIn.cs#4)]
     [!code-vb[Trin_WordAddInDynamicControls#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/VB/ThisAddIn.vb#4)]  
  
#### 네이티브 책갈피 컨트롤을 기반으로 하는 책갈피 컨트롤을 추가하려면  
  
1.  <xref:Microsoft.Office.Tools.Word.ControlCollection.AddBookmark%2A> 메서드를 사용하고 새 <xref:Microsoft.Office.Tools.Word.Bookmark>의 기초로 사용할 기존 <xref:Microsoft.Office.Interop.Word.Bookmark>를 전달합니다.  
  
     다음 코드 예제에서는 활성 문서의 첫 번째 <xref:Microsoft.Office.Interop.Word.Bookmark>를 기반으로 하는 새 <xref:Microsoft.Office.Tools.Word.Bookmark>를 만듭니다. 이 예제를 사용하려면 Word VSTO 추가 기능 프로젝트의 `ThisAddIn_Startup` 이벤트 처리기에서 코드를 실행합니다.  
  
     [!code-csharp[Trin_WordAddInDynamicControls#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/CS/ThisAddIn.cs#5)]
     [!code-vb[Trin_WordAddInDynamicControls#5](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/VB/ThisAddIn.vb#5)]  
  
## 참고 항목  
 [확장된 개체를 사용하여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [VSTO 추가 기능 프로그래밍](../vsto/programming-vsto-add-ins.md)   
 [문서 수준 사용자 지정 프로그래밍](../vsto/programming-document-level-customizations.md)   
 [방법: 책갈피 컨트롤 크기 조정](../vsto/how-to-resize-bookmark-controls.md)  
  
  