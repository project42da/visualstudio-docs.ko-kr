---
title: "방법: 콘텐츠 컨트롤을 사용하여 문서 부분 보호"
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
  - "콘텐츠 컨트롤[Visual Studio에서 Office 개발], 문서 보호"
  - "문서 보호[Visual Studio에서 Office 개발]"
  - "GroupContentControl"
  - "부분 문서 보호[Visual Studio에서 Office 개발]"
  - "제한된 권한[Visual Studio에서 Office 개발]"
  - "Word[Visual Studio에서 Office 개발], 부분 문서 보호"
  - "Word[Visual Studio에서 Office 개발], 제한된 권한"
ms.assetid: 50d7286a-7746-446f-8eef-06ceeadc94d0
caps.latest.revision: 28
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 27
---
# 방법: 콘텐츠 컨트롤을 사용하여 문서 부분 보호
  문서의 일부를 보호하는 경우 사용자가 문서의 해당 부분에서 내용을 변경하거나 삭제할 수 없습니다.  콘텐츠 컨트롤을 사용하여 Microsoft Office Word 문서 부분을 보호할 수 있는 여러 가지 방법이 있습니다.  
  
-   콘텐츠 컨트롤을 보호할 수 있습니다.  
  
-   콘텐츠 컨트롤에 없는 문서 부분을 보호할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
##  <a name="EditDeleteControl"></a> 콘텐츠 컨트롤 보호  
 디자인 타임 또는 런타임에 문서 수준 프로젝트에서 컨트롤의 속성을 설정하여 사용자가 콘텐츠 컨트롤을 편집하거나 삭제하는 것을 방지할 수 있습니다.  
  
 VSTO 추가 기능 프로젝트를 사용하여 런타임에 문서에 추가하는 콘텐츠 컨트롤을 보호할 수도 있습니다.  자세한 내용은 [방법: Word 문서에 콘텐츠 컨트롤 추가](../vsto/how-to-add-content-controls-to-word-documents.md)를 참조하세요.  
  
#### 디자인 타임에 콘텐츠 컨트롤을 보호하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디자이너에 호스트된 문서에서 보호하려는 콘텐츠 컨트롤을 선택합니다.  
  
2.  **속성** 창에서 다음 속성 중 하나 또는 둘 다를 설정합니다.  
  
    -   사용자가 컨트롤을 편집하지 못하도록 차단하려면 **LockContents**를 **True**로 설정합니다.  
  
    -   사용자가 컨트롤을 삭제하지 못하도록 차단하려면 **LockContentControl**을 **True**로 설정합니다.  
  
3.  **확인**을 클릭합니다.  
  
#### 런타임에 콘텐츠 컨트롤을 보호하려면  
  
1.  사용자가 컨트롤을 편집하지 못하도록 차단하려면 콘텐츠 컨트롤의 `LockContents` 속성을 **true**로 설정하고, 사용자가 컨트롤을 삭제하지 못하도록 차단하려면 `LockContentControl` 속성을 **true**로 설정합니다.  
  
     다음 코드 예제에서는 문서 수준 프로젝트에서 두 가지 <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 개체의 <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContents%2A> 및 <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContentControl%2A> 속성을 사용하는 방법을 보여 줍니다.  이 코드를 실행하려면 프로젝트의 `ThisDocument` 클래스에 코드를 추가하고 `ThisDocument_Startup` 이벤트 처리기에서 `AddProtectedContentControls` 메서드를 호출합니다.  
  
     [!code-csharp[Trin_ContentControlHowToProtect#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlHowToProtect/CS/ThisDocument.cs#2)]
     [!code-vb[Trin_ContentControlHowToProtect#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlHowToProtect/VB/ThisDocument.vb#2)]  
  
     다음 코드 예제에서는 VSTO 추가 기능 프로젝트에서 두 가지 <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 개체의 <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContents%2A> 및 <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContentControl%2A> 속성을 사용하는 방법을 보여 줍니다.  이 코드를 실행하려면 프로젝트의 `ThisAddIn` 클래스에 코드를 추가하고 `ThisAddIn_Startup` 이벤트 처리기에서 `AddProtectedContentControls` 메서드를 호출합니다.  
  
     [!code-csharp[Trin_WordAddInDynamicControls#14](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/CS/ThisAddIn.cs#14)]
     [!code-vb[Trin_WordAddInDynamicControls#14](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/VB/ThisAddIn.vb#14)]  
  
## 콘텐츠 컨트롤에 없는 문서 부분 보호  
 <xref:Microsoft.Office.Tools.Word.GroupContentControl>에 영역을 배치하여 사용자가 문서 영역을 변경하는 것을 방지할 수 있습니다.  이는 다음과 같은 시나리오에서 유용합니다.  
  
-   콘텐츠 컨트롤을 포함하지 않는 영역을 보호하려고 합니다.  
  
-   이미 콘텐츠 컨트롤을 포함하는 영역을 보호하려고 하지만 텍스트 또는 보호하려는 기타 항목이 콘텐츠 컨트롤에 없습니다.  
  
> [!NOTE]  
>  포함된 콘텐츠 컨트롤을 포함하는 <xref:Microsoft.Office.Tools.Word.GroupContentControl>을 만드는 경우 포함된 콘텐츠 컨트롤은 자동으로 보호되지 않습니다.  사용자가 포함된 콘텐츠 컨트롤을 편집하지 못하도록 차단하려면 컨트롤의 **LockContents** 속성을 사용합니다.  
  
#### 디자인 타임에 문서 영역을 보호하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디자이너에 호스트된 문서에서 보호하려는 영역을 선택합니다.  
  
2.  리본에서 **개발자** 탭을 클릭합니다.  
  
    > [!NOTE]  
    >  **개발자** 탭이 표시되지 않는 경우 먼저 개발자 탭을 표시해야 합니다.  자세한 내용은 [방법: 리본 메뉴에 개발 도구 탭 표시](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)를 참조하세요.  
  
3.  **컨트롤** 그룹에서 **그룹** 드롭다운 단추를 클릭한 다음 **그룹**을 클릭합니다.  
  
     보호된 영역을 포함하는 <xref:Microsoft.Office.Tools.Word.GroupContentControl>이 프로젝트의 `ThisDocument` 클래스에 자동으로 생성됩니다.  그룹 컨트롤을 나타내는 테두리는 디자인 타임에만 표시되고 런타임에는 표시되는 테두리가 없습니다.  
  
#### 런타임에 문서 영역을 보호하려면  
  
1.  보호하려는 영역을 프로그래밍 방식으로 선택하고 <xref:Microsoft.Office.Tools.Word.ControlCollection.AddGroupContentControl%2A> 메서드를 호출하여 <xref:Microsoft.Office.Tools.Word.GroupContentControl>을 만듭니다.  
  
     문서 수준 프로젝트에 대한 다음 코드 예제에서는 문서의 첫 단락에 텍스트를 추가하고, 첫 단락을 선택한 다음 <xref:Microsoft.Office.Tools.Word.GroupContentControl>을 인스턴스화합니다.  이 코드를 실행하려면 프로젝트의 `ThisDocument` 클래스에 코드를 추가하고 `ThisDocument_Startup` 이벤트 처리기에서 `ProtectFirstParagraph` 메서드를 호출합니다.  
  
     [!code-csharp[Trin_ContentControlHowToProtect#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlHowToProtect/CS/ThisDocument.cs#1)]
     [!code-vb[Trin_ContentControlHowToProtect#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlHowToProtect/VB/ThisDocument.vb#1)]  
  
     VSTO 추가 기능 프로젝트에 대한 다음 코드 예제에서는 활성 문서의 첫 단락에 텍스트를 추가하고, 첫 단락을 선택한 다음 <xref:Microsoft.Office.Tools.Word.GroupContentControl>을 인스턴스화합니다.  이 코드를 실행하려면 프로젝트의 `ThisAddIn` 클래스에 코드를 추가하고 `ThisAddIn_Startup` 이벤트 처리기에서 `ProtectFirstParagraph` 메서드를 호출합니다.  
  
     [!code-csharp[Trin_WordAddInDynamicControls#15](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/CS/ThisAddIn.cs#15)]
     [!code-vb[Trin_WordAddInDynamicControls#15](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/VB/ThisAddIn.vb#15)]  
  
## 참고 항목  
 [확장된 개체를 사용하여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [콘텐츠 컨트롤](../vsto/content-controls.md)   
 [방법: Word 문서에 콘텐츠 컨트롤 추가](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  