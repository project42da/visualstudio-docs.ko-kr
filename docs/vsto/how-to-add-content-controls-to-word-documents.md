---
title: "방법: Word 문서에 콘텐츠 컨트롤 추가"
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
  - "제한된 권한[Visual Studio에서 Office 개발]"
  - "DropDownListContentControl, 문서에 추가"
  - "BuildingBlockGalleryContentControl, 문서에 추가"
  - "부분 문서 보호[Visual Studio에서 Office 개발]"
  - "RichTextContentControl, 문서에 추가"
  - "Word[Visual Studio에서 Office 개발], 부분 문서 보호"
  - "콘텐츠 컨트롤[Visual Studio에서 Office 개발], 보호"
  - "PictureContentControl, 문서에 추가"
  - "GroupContentControl, 문서에 추가"
  - "문서 보호[Visual Studio에서 Office 개발]"
  - "PlainTextContentControl, 문서에 추가"
  - "콘텐츠 컨트롤[Visual Studio에서 Office 개발], 추가"
  - "ComboBoxContentControl, 문서에 추가"
  - "DatePickerContentControl, 문서에 추가"
  - "Word[Visual Studio에서 Office 개발], 제한된 권한"
ms.assetid: 68ddb24e-71c6-46f7-8e11-c9899d7814df
caps.latest.revision: 51
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 50
---
# 방법: Word 문서에 콘텐츠 컨트롤 추가
  문서 수준 Word 프로젝트에서는 디자인 타임 또는 런타임에 프로젝트의 문서에 콘텐츠 컨트롤을 추가할 수 있습니다. Word VSTO 추가 기능 프로젝트에서는 런타임에 열려 있는 임의 문서에 콘텐츠 컨트롤을 추가할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 이 항목에서는 다음 작업에 대해 설명합니다.  
  
-   [디자인 타임에 콘텐츠 컨트롤 추가](#designtime)  
  
-   [런타임에 문서 수준 프로젝트에서 콘텐츠 컨트롤 추가](#runtimedoclevel)  
  
-   [런타임에 VSTO 추가 기능 프로젝트에서 콘텐츠 컨트롤 추가](#runtimeaddin)  
  
 콘텐츠 컨트롤에 대한 자세한 내용은 [콘텐츠 컨트롤](../vsto/content-controls.md)을 참조하세요.  
  
##  <a name="designtime"></a> 디자인 타임에 콘텐츠 컨트롤 추가  
 디자인 타임에 문서 수준 프로젝트의 문서에 콘텐츠 컨트롤을 추가하는 여러 가지 방법이 있습니다.  
  
-   **도구 상자**의 **Word 컨트롤** 탭에서 콘텐츠 컨트롤을 추가합니다.  
  
-   Word에서 네이티브 콘텐츠 컨트롤을 추가하는 것과 동일한 방식으로 문서에 콘텐츠 컨트롤을 추가합니다.  
  
-   **데이터 소스** 창에서 콘텐츠 컨트롤을 문서로 끌어옵니다. 이 기능은 컨트롤을 만들 때 컨트롤을 데이터에 바인딩하려는 경우에 유용합니다. 자세한 내용은 [방법: 개체의 데이터로 문서 채우기](../vsto/how-to-populate-documents-with-data-from-objects.md) 및 [방법: 데이터베이스의 데이터로 문서 채우기](../vsto/how-to-populate-documents-with-data-from-a-database.md)를 참조하세요.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
#### 도구 상자를 사용하여 문서에 콘텐츠 컨트롤을 추가하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디자이너에 호스트된 문서에서 콘텐츠 컨트롤을 추가하려는 위치에 커서를 놓거나 콘텐츠 컨트롤로 바꾸려는 텍스트를 선택합니다.  
  
2.  **도구 상자**를 열고 **Word 컨트롤** 탭을 클릭합니다.  
  
3.  다음 방법 중 하나로 컨트롤을 추가합니다.  
  
    -   **도구 상자**에서 콘텐츠 컨트롤을 두 번 클릭합니다.  
  
         또는  
  
    -   **도구 상자**에서 콘텐츠 컨트롤을 클릭하고 Enter 키를 누릅니다.  
  
         또는  
  
    -   **도구 상자**에서 문서로 콘텐츠 컨트롤을 끌어옵니다. 콘텐츠 컨트롤이 마우스 포인터 위치가 아니라 문서의 현재 선택 영역에 추가됩니다.  
  
> [!NOTE]  
>  **도구 상자**를 사용하여 <xref:Microsoft.Office.Tools.Word.GroupContentControl>을 추가할 수 없습니다. Word에서나 런타임에만 <xref:Microsoft.Office.Tools.Word.GroupContentControl>을 추가할 수 있습니다.  
  
> [!NOTE]  
>  Visual Studio는 도구 상자에 확인란 콘텐츠 컨트롤을 제공하지 않습니다. 문서에 확인란 콘텐츠 컨트롤을 추가하려면 프로그래밍 방식으로 <xref:Microsoft.Office.Tools.Word.ContentControl> 개체를 만들어야 합니다. 자세한 내용은 [콘텐츠 컨트롤](../vsto/content-controls.md)을 참조하세요.  
  
#### Word에서 문서에 콘텐츠 컨트롤을 추가하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디자이너에 호스트된 문서에서 콘텐츠 컨트롤을 추가하려는 위치에 커서를 놓거나 콘텐츠 컨트롤로 바꾸려는 텍스트를 선택합니다.  
  
2.  리본에서 **개발자** 탭을 클릭합니다.  
  
    > [!NOTE]  
    >  **개발자** 탭이 표시되지 않는 경우 먼저 개발자 탭을 표시해야 합니다. 자세한 내용은 [방법: 리본 메뉴에 개발 도구 탭 표시](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)을 참조하십시오.  
  
3.  **컨트롤** 그룹에서 추가하려는 콘텐츠 컨트롤의 아이콘을 클릭합니다.  
  
##  <a name="runtimedoclevel"></a> 런타임에 문서 수준 프로젝트에서 콘텐츠 컨트롤 추가  
 프로젝트에서 `ThisDocument` 클래스의 <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> 속성 메서드를 사용하여 프로그래밍 방식으로 런타임에 문서에 콘텐츠 컨트롤을 추가할 수 있습니다. 각 메서드에 다음과 같은 방법으로 콘텐츠 컨트롤을 추가하는 데 사용할 수 있는 세 개의 오버로드가 있습니다.  
  
-   현재 선택 영역에 컨트롤을 추가합니다.  
  
-   지정된 범위에 컨트롤을 추가합니다.  
  
-   문서의 네이티브 콘텐츠 컨트롤을 기반으로 하는 컨트롤을 추가합니다.  
  
 동적으로 생성된 콘텐츠 컨트롤은 문서를 닫을 때 문서에 유지되지 않습니다. 그러나 네이티브 콘텐츠 컨트롤은 문서에 남아 있습니다. 다음에 문서를 열 때 네이티브 콘텐츠 컨트롤을 기반으로 하는 콘텐츠 컨트롤을 다시 만들 수 있습니다. 자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)을 참조하세요.  
  
> [!NOTE]  
>  Word 2010 프로젝트에서 문서에 확인란 콘텐츠 컨트롤을 추가하려면 <xref:Microsoft.Office.Tools.Word.ContentControl> 개체를 만들어야 합니다. 자세한 내용은 [콘텐츠 컨트롤](../vsto/content-controls.md)을 참조하십시오.  
  
#### 현재 선택 영역에 콘텐츠 컨트롤을 추가하려면  
  
1.  이름이 `Add`\<*컨트롤 클래스*\>이고 새 컨트롤의 이름을 나타내는 단일 매개 변수가 있는 <xref:Microsoft.Office.Tools.Word.ControlCollection> 메서드를 사용합니다. 여기서 *컨트롤 클래스*는 추가할 콘텐츠 컨트롤의 클래스 이름\(예: <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>\)입니다.  
  
     다음 코드 예제에서는 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> 메서드를 사용하여 문서의 시작 부분에 새 <xref:Microsoft.Office.Tools.Word.RichTextContentControl>을 추가합니다. 이 코드를 실행하려면 프로젝트의 `ThisDocument` 클래스에 코드를 추가하고 `ThisDocument_Startup` 이벤트 처리기에서 `AddRichTextControlAtSelection` 메서드를 호출합니다.  
  
     [!code-csharp[Trin_ContentControlReference#700](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlReference/CS/RichText.cs#700)]
     [!code-vb[Trin_ContentControlReference#700](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlReference/VB/RichText.vb#700)]  
  
#### 지정된 범위에 콘텐츠 컨트롤을 추가하려면  
  
1.  이름이 `Add`\<*컨트롤 클래스*\>이고 <xref:Microsoft.Office.Interop.Word.Range> 매개 변수가 있는 <xref:Microsoft.Office.Tools.Word.ControlCollection> 메서드를 사용합니다. 여기서 *컨트롤 클래스*는 추가할 콘텐츠 컨트롤 클래스의 이름\(예: <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>\)입니다.  
  
     다음 코드 예제에서는 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> 메서드를 사용하여 문서의 시작 부분에 새 <xref:Microsoft.Office.Tools.Word.RichTextContentControl>을 추가합니다. 이 코드를 실행하려면 프로젝트의 `ThisDocument` 클래스에 코드를 추가하고 `ThisDocument_Startup` 이벤트 처리기에서 `AddRichTextControlAtRange` 메서드를 호출합니다.  
  
     [!code-csharp[Trin_ContentControlReference#701](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlReference/CS/RichText.cs#701)]
     [!code-vb[Trin_ContentControlReference#701](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlReference/VB/RichText.vb#701)]  
  
#### 네이티브 콘텐츠 컨트롤을 기반으로 하는 콘텐츠 컨트롤을 추가하려면  
  
1.  이름이 `Add`\<*컨트롤 클래스*\>이고 Microsoft.Office.Interop.Word.ContentControl 매개 변수가 있는 <xref:Microsoft.Office.Tools.Word.ControlCollection> 메서드를 사용합니다. 여기서 *컨트롤 클래스*는 추가할 콘텐츠 컨트롤 클래스의 이름\(예: <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>\)입니다.  
  
     다음 코드 예제에서는 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> 메서드를 사용하여 문서에 있는 각 네이티브 서식 있는 텍스트 컨트롤에 대한 새 <xref:Microsoft.Office.Tools.Word.RichTextContentControl>을 만듭니다. 이 코드를 실행하려면 프로젝트의 `ThisDocument` 클래스에 코드를 추가하고 `ThisDocument_Startup` 이벤트 처리기에서 `CreateRichTextControlsFromNativeControls` 메서드를 호출합니다.  
  
     [!code-csharp[Trin_ContentControlReference#702](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlReference/CS/RichText.cs#702)]
     [!code-vb[Trin_ContentControlReference#702](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlReference/VB/RichText.vb#702)]  
  
##  <a name="runtimeaddin"></a> 런타임에 VSTO 추가 기능 프로젝트에서 콘텐츠 컨트롤 추가  
 VSTO 추가 기능을 사용하여 프로그래밍 방식으로 런타임에 열려 있는 문서에 콘텐츠 컨트롤을 추가할 수 있습니다. 이렇게 하려면 열려 있는 문서를 기반으로 하는 <xref:Microsoft.Office.Tools.Word.Document> 호스트 항목을 생성한 다음 이 호스트 항목의 <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> 속성 메서드를 사용합니다. 각 메서드에 다음과 같은 방법으로 콘텐츠 컨트롤을 추가하는 데 사용할 수 있는 세 개의 오버로드가 있습니다.  
  
-   현재 선택 영역에 컨트롤을 추가합니다.  
  
-   지정된 범위에 컨트롤을 추가합니다.  
  
-   문서의 네이티브 콘텐츠 컨트롤을 기반으로 하는 컨트롤을 추가합니다.  
  
 동적으로 생성된 콘텐츠 컨트롤은 문서를 닫을 때 문서에 유지되지 않습니다. 그러나 네이티브 콘텐츠 컨트롤은 문서에 남아 있습니다. 다음에 문서를 열 때 네이티브 콘텐츠 컨트롤을 기반으로 하는 콘텐츠 컨트롤을 다시 만들 수 있습니다. 자세한 내용은 [Office 문서에서 동적 컨트롤 유지](../vsto/persisting-dynamic-controls-in-office-documents.md)을 참조하세요.  
  
 VSTO 추가 기능 프로젝트에서 호스트 항목을 생성하는 방법에 대한 자세한 내용은 [런타임에 VSTO 추가 기능에서 Word 문서 및 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)을 참조하세요.  
  
> [!NOTE]  
>  문서에 확인란 콘텐츠 컨트롤을 추가하려면 <xref:Microsoft.Office.Tools.Word.ContentControl> 개체를 만들어야 합니다. 자세한 내용은 [콘텐츠 컨트롤](../vsto/content-controls.md)을 참조하세요.  
  
#### 현재 선택 영역에 콘텐츠 컨트롤을 추가하려면  
  
1.  이름이 `Add`\<*컨트롤 클래스*\>이고 새 컨트롤의 이름을 나타내는 단일 매개 변수가 있는 <xref:Microsoft.Office.Tools.Word.ControlCollection> 메서드를 사용합니다. 여기서 *컨트롤 클래스*는 추가할 콘텐츠 컨트롤의 클래스 이름\(예: <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>\)입니다.  
  
     다음 코드 예제에서는 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> 메서드를 사용하여 활성 문서의 시작 부분에 새 <xref:Microsoft.Office.Tools.Word.RichTextContentControl>을 추가합니다. 이 코드를 실행하려면 프로젝트의 `ThisAddIn` 클래스에 코드를 추가하고 `ThisAddIn_Startup` 이벤트 처리기에서 `AddRichTextControlAtSelection` 메서드를 호출합니다.  
  
     [!code-csharp[Trin_WordAddInDynamicControls#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/CS/ThisAddIn.cs#1)]
     [!code-vb[Trin_WordAddInDynamicControls#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/VB/ThisAddIn.vb#1)]  
  
#### 지정된 범위에 콘텐츠 컨트롤을 추가하려면  
  
1.  이름이 `Add`\<*컨트롤 클래스*\>이고 <xref:Microsoft.Office.Interop.Word.Range> 매개 변수가 있는 <xref:Microsoft.Office.Tools.Word.ControlCollection> 메서드를 사용합니다. 여기서 *컨트롤 클래스*는 추가할 콘텐츠 컨트롤 클래스의 이름\(예: <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>\)입니다.  
  
     다음 코드 예제에서는 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> 메서드를 사용하여 활성 문서의 시작 부분에 새 <xref:Microsoft.Office.Tools.Word.RichTextContentControl>을 추가합니다. 이 코드를 실행하려면 프로젝트의 `ThisAddIn` 클래스에 코드를 추가하고 `ThisAddIn_Startup` 이벤트 처리기에서 `AddRichTextControlAtRange` 메서드를 호출합니다.  
  
     [!code-csharp[Trin_WordAddInDynamicControls#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/CS/ThisAddIn.cs#2)]
     [!code-vb[Trin_WordAddInDynamicControls#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/VB/ThisAddIn.vb#2)]  
  
#### 네이티브 콘텐츠 컨트롤을 기반으로 하는 콘텐츠 컨트롤을 추가하려면  
  
1.  이름이 `Add`\<*컨트롤 클래스*\>이고 Microsoft.Office.Interop.Word.ContentControl 매개 변수가 있는 <xref:Microsoft.Office.Tools.Word.ControlCollection> 메서드를 사용합니다. 여기서 *컨트롤 클래스*는 추가할 콘텐츠 컨트롤 클래스의 이름\(예: <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>\)입니다.  
  
     다음 코드 예제에서는 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> 메서드를 사용하여 문서가 열린 후 문서에 있는 각 네이티브 서식 있는 텍스트 컨트롤에 대한 새 <xref:Microsoft.Office.Tools.Word.RichTextContentControl>을 만듭니다. 이 코드를 실행하려면 프로젝트의 `ThisAddIn` 클래스에 코드를 추가합니다.  
  
     [!code-csharp[Trin_WordAddInDynamicControls#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/CS/ThisAddIn.cs#3)]
     [!code-vb[Trin_WordAddInDynamicControls#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/VB/ThisAddIn.vb#3)]  
  
     C\#의 경우 `Application_DocumentOpen` 이벤트 처리기도 <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen> 이벤트에 연결해야 합니다.  
  
     [!code-csharp[Trin_WordAddInDynamicControls#6](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/CS/ThisAddIn.cs#6)]  
  
## 참고 항목  
 [확장된 개체를 사용하여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [VSTO 추가 기능 프로그래밍](../vsto/programming-vsto-add-ins.md)   
 [문서 수준 사용자 지정 프로그래밍](../vsto/programming-document-level-customizations.md)  
  
  