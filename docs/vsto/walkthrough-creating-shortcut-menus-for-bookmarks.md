---
title: "연습: 책갈피에 대한 바로 가기 메뉴 만들기"
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
  - "Bookmark 컨트롤, 이벤트"
  - "상황에 맞는 메뉴, Word"
  - "메뉴, Office 응용 프로그램에서 만들기"
  - "바로 가기 메뉴, Word"
ms.assetid: 86dbf3ff-ba75-42f9-8df6-abfc19b3cf6b
caps.latest.revision: 57
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 53
---
# 연습: 책갈피에 대한 바로 가기 메뉴 만들기
  이 연습에서는 Word용 문서 수준 사용자 지정에서 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤에 대한 바로 가기 메뉴를 만드는 방법을 보여 줍니다.  사용자가 책갈피의 텍스트를 마우스 오른쪽 단추로 클릭하면 바로 가기 메뉴가 나타나고 텍스트 서식을 지정하기 위한 옵션이 제공됩니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   [프로젝트 만들기](#BKMK_CreateProject).  
  
-   [문서에 텍스트 및 책갈피 추가](#BKMK_addtextandbookmarks).  
  
-   [바로 가기 메뉴에 명령 추가](#BKMK_AddCmndsShortMenu).  
  
-   [책갈피의 텍스트 서식 지정](#BKMK_formattextbkmk).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] 또는 [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]  
  
##  <a name="BKMK_CreateProject"></a> 프로젝트 만들기  
 첫 번째 단계에서는 Visual Studio에서 Word 문서 프로젝트를 만듭니다.  
  
#### 새 프로젝트를 만들려면  
  
-   이름이 My Bookmark Shortcut Menu인 Word 문서 프로젝트를 만듭니다.  마법사에서 **새 문서 만들기**를 선택합니다.  자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하십시오.  
  
     Visual Studio의 디자이너에 새 Word 문서가 열리고 **My Bookmark Shortcut Menu** 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
##  <a name="BKMK_addtextandbookmarks"></a> 문서에 텍스트 및 책갈피 추가  
 문서에 텍스트를 추가하고 두 개의 겹치는 책갈피를 추가합니다.  
  
#### 문서에 텍스트를 추가하려면  
  
-   프로젝트 디자이너에 표시 된 문서에 다음 텍스트를 입력 합니다.  
  
     이 예제에서는 책갈피의 텍스트를 마우스 오른쪽 단추로 클릭할 때 나타나는 바로 가기 메뉴를 만듭니다.  
  
#### 문서에 Bookmark 컨트롤을 추가하려면  
  
1.  에  **도구**에서  **Word 컨트롤** 탭을 드래그는 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 문서에.  
  
     **Bookmark 컨트롤 추가** 대화 상자가 나타납니다.  
  
2.  "텍스트를 마우스 오른쪽 단추로 누르면 바로 가기 메뉴 만들기" 단어 선택, 다음을 클릭 하 고  **확인**.  
  
     `bookmark1`이 문서에 추가됩니다.  
  
3.  다른 추가 <xref:Microsoft.Office.Tools.Word.Bookmark> "책갈피의 텍스트를 마우스 오른쪽 단추로 클릭" 단어를 제어 합니다.  
  
     `bookmark2`가 문서에 추가됩니다.  
  
    > [!NOTE]  
    >  모두에 "텍스트를 마우스 오른쪽 단추로" 단어 `bookmark1` 및 `bookmark2`.  
  
 디자인 타임에 문서에 책갈피를 추가하면 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤이 만들어집니다.  책갈피의 여러 이벤트에 대해 프로그래밍 작업을 할 수 있습니다.  사용자가 책갈피의 텍스트를 마우스 오른쪽 단추로 클릭하면 바로 가기 메뉴가 나타나도록 책갈피의 <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeRightClick> 이벤트에 코드를 작성할 수 있습니다.  
  
##  <a name="BKMK_AddCmndsShortMenu"></a> 바로 가기 메뉴에 명령 추가  
 문서를 마우스 오른쪽 단추로 클릭할 때 나타나는 바로 가기 메뉴 단추를 추가 합니다.  
  
#### 바로 가기 메뉴에 명령을 추가 하려면  
  
1.  추가 된  **리본 XML** 프로젝트 항목입니다.  자세한 내용은 [방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)을 참조하십시오.  
  
2.  **솔루션 탐색기**에서  **ThisDocument.cs** 또는  **ThisDocument.vb**.  
  
3.  선택 메뉴 모음에서  **보기**,  **코드**.  
  
     **ThisDocument** 클래스 파일이 코드 편집기에서 열립니다.  
  
4.  다음 코드를 추가 하는  **ThisDocument** 클래스입니다.  이 코드는 CreateRibbonExtensibilityObject 메서드를 재정의하고 Office 응용 프로그램에 리본 XML 클래스를 반환합니다.  
  
     [!code-csharp[Trin_Word_Document_Menus#1](../snippets/csharp/VS_Snippets_OfficeSP/trin_word_document_menus/cs/thisdocument.cs#1)]
     [!code-vb[Trin_Word_Document_Menus#1](../snippets/visualbasic/VS_Snippets_OfficeSP/trin_word_document_menus/vb/thisdocument.vb#1)]  
  
5.  **솔루션 탐색기**, 리본 XML 파일을 선택 합니다.  기본적으로 리본 XML 파일에 Ribbon1.xml 라고 합니다.  
  
6.  선택 메뉴 모음에서  **보기**,  **코드**.  
  
     리본 xml 파일에는 코드 편집기에서 열립니다.  
  
7.  코드 편집기에서 리본 XML 파일의 내용을 다음 코드로 바꿉니다.  
  
    ```  
  
    <customUI xmlns="http://schemas.microsoft.com/office/2009/07/customui" onLoad="Ribbon_Load">  
      <contextMenus>  
        <contextMenu idMso="ContextMenuText">  
          <button id="BoldButton" label="Bold" onAction="ButtonClick"          
               getVisible="GetVisible" />  
          <button id="ItalicButton" label="Italic" onAction="ButtonClick"   
              getVisible="GetVisible"/>  
        </contextMenu>  
      </contextMenus>  
    </customUI>  
    ```  
  
     이 코드는 문서를 마우스 오른쪽 단추로 클릭 하면 나타나는 바로 가기 메뉴에 두 개의 단추를 추가 합니다.  
  
8.  **솔루션 탐색기**에서 `ThisDocument`를 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 클릭합니다.  
  
9. 다음 변수 및 클래스 수준에서 책갈피 변수를 선언 합니다.  
  
     [!code-csharp[Trin_Word_Document_Menus#2](../snippets/csharp/VS_Snippets_OfficeSP/trin_word_document_menus/cs/thisdocument.cs#2)]
     [!code-vb[Trin_Word_Document_Menus#2](../snippets/visualbasic/VS_Snippets_OfficeSP/trin_word_document_menus/vb/thisdocument.vb#2)]  
  
10. **솔루션 탐색기**, 리본 코드 파일을 선택 합니다.  기본적으로 리본 코드 파일의 이름은  **Ribbon1.cs** 또는  **Ribbon1.vb**.  
  
11. 선택 메뉴 모음에서  **보기**,  **코드**.  
  
     코드 편집기에서 리본 코드 파일이 열립니다.  
  
12. 리본 코드 파일에 다음 메서드를 추가 합니다.  문서의 바로 가기 메뉴에 추가 된 두 개의 단추에 대 한 콜백 메서드입니다.  이 메서드는 이러한 단추 바로 가기 메뉴에 표시 되는지 여부를 결정 합니다.  굵게 및 기울임꼴 단추 책갈피 내의 텍스트를 마우스 오른쪽 단추로 클릭 하는 경우에 표시 됩니다.  
  
     [!code-csharp[Trin_Word_Document_Menus#5](../snippets/csharp/VS_Snippets_OfficeSP/trin_word_document_menus/cs/ribbon1.cs#5)]
     [!code-vb[Trin_Word_Document_Menus#5](../snippets/visualbasic/VS_Snippets_OfficeSP/trin_word_document_menus/vb/ribbon1.vb#5)]  
  
##  <a name="BKMK_formattextbkmk"></a> 책갈피의 텍스트 서식 지정  
  
#### 책갈피의 텍스트를 서식 지정하려면  
  
1.  리본 코드 파일에 추가 된 `ButtonClick` 책갈피에 서식을 적용 하는 이벤트 처리기입니다.  
  
     [!code-csharp[Trin_Word_Document_Menus#6](../snippets/csharp/VS_Snippets_OfficeSP/trin_word_document_menus/cs/ribbon1.cs#6)]
     [!code-vb[Trin_Word_Document_Menus#6](../snippets/visualbasic/VS_Snippets_OfficeSP/trin_word_document_menus/vb/ribbon1.vb#6)]  
  
2.  **솔루션 탐색기**에서  **ThisDocument.cs** 또는  **ThisDocument.vb**.  
  
3.  선택 메뉴 모음에서  **보기**,  **코드**.  
  
     **ThisDocument** 클래스 파일이 코드 편집기에서 열립니다.  
  
4.  다음 코드를 추가 하는  **ThisDocument** 클래스입니다.  
  
     [!code-csharp[Trin_Word_Document_Menus#3](../snippets/csharp/VS_Snippets_OfficeSP/trin_word_document_menus/cs/thisdocument.cs#3)]
     [!code-vb[Trin_Word_Document_Menus#3](../snippets/visualbasic/VS_Snippets_OfficeSP/trin_word_document_menus/vb/thisdocument.vb#3)]  
  
    > [!NOTE]  
    >  책갈피가 겹치는 경우 이를 처리하기 위한 코드를 작성해야 합니다.  그렇지 않으면 기본적으로 선택 영역의 모든 책갈피에 대한 코드가 호출됩니다.  
  
5.  C\#의 경우 <xref:Microsoft.Office.Tools.Word.Document.Startup> 이벤트에 Bookmark 컨트롤에 대한 이벤트 처리기를 추가해야 합니다.  이벤트 처리기를 만드는 방법에 대한 자세한 내용은 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)를 참조하십시오.  
  
     [!code-csharp[Trin_Word_Document_Menus#4](../snippets/csharp/VS_Snippets_OfficeSP/trin_word_document_menus/cs/thisdocument.cs#4)]  
  
## 응용 프로그램 테스트  
 테스트 하 고 텍스트가 올바르게 서식 지정 하 고 책갈피의에서 텍스트를 마우스 오른쪽 단추로 클릭할 때 굵게 및 기울임꼴 메뉴 항목이 바로 가기 메뉴에 나타나는지 확인 하 여 문서.  
  
#### 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  첫 번째 책갈피를 마우스 오른쪽 단추로 클릭하고 **굵게**를 클릭합니다.  
  
3.  `bookmark1`의 텍스트가 모두 굵게 서식 지정되는지 확인합니다.  
  
4.  책갈피가 겹치는 위치의 텍스트를 마우스 오른쪽 단추로 클릭하고 **기울임꼴**을 클릭합니다.  
  
5.  `bookmark2`의 모든 텍스트가 기울임꼴이며 `bookmark2`와 겹치는 `bookmark1`의 텍스트 부분만 기울임꼴인지 확인합니다.  
  
## 다음 단계  
 다음에 수행할 수 있는 작업은 다음과 같습니다.  
  
-   Excel에서 호스트 컨트롤의 이벤트에 응답하는 코드를 작성합니다.  자세한 내용은 [연습: NamedRange 컨트롤의 이벤트 프로그래밍](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)을 참조하십시오.  
  
-   확인란을 사용하여 책갈피의 서식을 변경합니다.  자세한 내용은 [연습: CheckBox 컨트롤을 사용하여 문서 서식 변경](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md)을 참조하십시오.  
  
## 참고 항목  
 [Word를 사용한 연습](../vsto/walkthroughs-using-word.md)   
 [Office UI 사용자 지정](../vsto/office-ui-customization.md)   
 [확장된 개체를 사용하여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [책갈피 컨트롤](../vsto/bookmark-control.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  