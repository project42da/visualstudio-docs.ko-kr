---
title: "연습: 콘텐츠 컨트롤을 사용하여 서식 파일 만들기"
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
  - "문서 블록[Visual Studio에서 Office 개발]"
  - "콘텐츠 컨트롤[Visual Studio에서 Office 개발], 문서에 추가"
  - "Word[Visual Studio에서 Office 개발], 문서 만들기"
ms.assetid: 88fb9a60-dcc3-4a5f-a8c9-7aff01ca4b4b
caps.latest.revision: 46
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 42
---
# 연습: 콘텐츠 컨트롤을 사용하여 서식 파일 만들기
  이 연습에서는 콘텐츠 컨트롤을 사용하여 Microsoft Office Word 서식 파일에서 구조화되고 재사용 가능한 콘텐츠를 만드는 문서 수준 사용자 지정을 만드는 방법을 보여 줍니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Word에서 *문서 블록*이라는 재사용 가능한 문서 부분의 컬렉션을 만들 수 있습니다.  이 연습에서는 문서 블록으로 두 개의 표를 만드는 방법을 보여 줍니다.  각 표에는 일반 텍스트 또는 날짜와 같은 서로 다른 형식의 콘텐츠를 보유할 수 있는 여러 콘텐츠 컨트롤이 포함됩니다.  표 중 하나에는 직원에 대한 정보가 포함되고 다른 표에는 고객 의견이 포함됩니다.  
  
 서식 파일에서 문서를 만든 후 서식 파일에서 사용 가능한 문서 블록을 표시하는 여러 <xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl> 개체를 사용하여 문서에 표 중 하나를 추가할 수 있습니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   디자인 타임에 Word 서식 파일에서 콘텐츠 컨트롤이 포함된 표 만들기  
  
-   프로그래밍 방식으로 콤보 상자 콘텐츠 컨트롤 및 드롭다운 목록 콘텐츠 컨트롤 채우기  
  
-   사용자가 지정된 표를 편집할 수 없도록 차단  
  
-   서식 파일의 문서 블록 컬렉션에 표 추가  
  
-   서식 파일에서 사용 가능한 문서 블록을 표시하는 콘텐츠 컨트롤 만들기  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## 새 Word 서식 파일 프로젝트 만들기  
 사용자가 고유한 복사본을 쉽게 만들 수 있도록 Word 서식 파일을 만듭니다.  
  
#### 새 Word 서식 파일 프로젝트를 만들려면  
  
1.  이름이 MyBuildingBlockTemplate인 Word 서식 파일 프로젝트를 만듭니다.  마법사에서 솔루션에 새 문서를 만듭니다.  자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)를 참조하세요.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]의 디자이너에서 새 Word 서식 파일이 열리고 **MyBuildingBlockTemplate** 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
## Employee 표 만들기  
 사용자가 직원에 대한 정보를 입력할 수 있는 네 가지 형식의 콘텐츠 컨트롤을 포함하는 표를 만듭니다.  
  
#### Employee 표를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디자이너에 호스트된 Word 서식 파일의 리본 메뉴에서 **삽입** 탭을 클릭합니다.  
  
2.  **표** 그룹에서 **표**를 클릭하고 2열, 4행의 표를 삽입합니다.  
  
3.  다음 열과 비슷하도록 첫 번째 열에 텍스트를 입력합니다.  
  
    ||  
    |-|  
    |Employee Name|  
    |Hire Date|  
    |제목|  
    |Picture|  
  
4.  두 번째 열의 첫 번째 셀을 클릭합니다\(**Employee Name** 옆\).  
  
5.  리본에서 **개발자** 탭을 클릭합니다.  
  
    > [!NOTE]  
    >  **개발자** 탭이 표시되지 않는 경우 먼저 개발자 탭을 표시해야 합니다.  자세한 내용은 [방법: 리본 메뉴에 개발 도구 탭 표시](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)를 참조하세요.  
  
6.  **컨트롤** 그룹에서 **텍스트** 단추 ![PlainTextContentControl](../vsto/media/plaintextcontrol.png "PlainTextContentControl")를 클릭하여 첫 번째 셀에 <xref:Microsoft.Office.Tools.Word.PlainTextContentControl>을 추가합니다.  
  
7.  두 번째 열의 두 번째 셀을 클릭합니다\(**Hire Date** 옆\).  
  
8.  **컨트롤** 그룹에서 **날짜 선택** 단추 ![DatePickerContentControl](../vsto/media/datepicker.png "DatePickerContentControl")를 클릭하여 두 번째 셀에 <xref:Microsoft.Office.Tools.Word.DatePickerContentControl>을 추가합니다.  
  
9. 두 번째 열의 세 번째 셀을 클릭합니다\(**Title** 옆\).  
  
10. **컨트롤** 그룹에서 **콤보 상자** 단추 ![ComboBoxContentControl](../vsto/media/combobox.png "ComboBoxContentControl")를 클릭하여 세 번째 셀에 <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl>을 추가합니다.  
  
11. 두 번째 열의 마지막 셀을 클릭합니다\(**Picture** 옆\).  
  
12. **컨트롤** 그룹에서 **그림 콘텐츠 컨트롤** 단추 ![PictureContentControl](../vsto/media/pictcontentcontrol.png "PictureContentControl")를 클릭하여 마지막 셀에 <xref:Microsoft.Office.Tools.Word.PictureContentControl>을 추가합니다.  
  
## 사용자 의견 표 만들기  
 사용자가 의견 정보를 입력할 수 있는 세 가지 형식의 콘텐츠 컨트롤을 포함하는 표를 만듭니다.  
  
#### 사용자 의견 표를 만들려면  
  
1.  Word 서식 파일에서 이전에 추가한 Employee 표 뒤의 줄을 클릭하고 Enter 키를 눌러 새 단락을 추가합니다.  
  
2.  리본 메뉴에서 **삽입** 탭을 클릭합니다.  
  
3.  **표** 그룹에서 **표**를 클릭하고 2열, 3행의 표를 삽입합니다.  
  
4.  다음 열과 비슷하도록 첫 번째 열에 텍스트를 입력합니다.  
  
    ||  
    |-|  
    |Customer Name|  
    |Satisfaction Rating|  
    |메모|  
  
5.  두 번째 열의 첫 번째 셀을 클릭합니다\(**Customer Name** 옆\).  
  
6.  리본에서 **개발자** 탭을 클릭합니다.  
  
7.  **컨트롤** 그룹에서 **텍스트** 단추 ![PlainTextContentControl](../vsto/media/plaintextcontrol.png "PlainTextContentControl")를 클릭하여 첫 번째 셀에 <xref:Microsoft.Office.Tools.Word.PlainTextContentControl>을 추가합니다.  
  
8.  두 번째 열의 두 번째 셀을 클릭합니다\(**Satisfaction Rating** 옆\).  
  
9. **컨트롤** 그룹에서 **드롭다운 목록** 단추 ![DropDownListContentControl](../vsto/media/dropdownlist.png "DropDownListContentControl")를 클릭하여 두 번째 셀에 <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>을 추가합니다.  
  
10. 두 번째 열의 마지막 셀을 클릭합니다\(**Comments** 옆\).  
  
11. **컨트롤** 그룹에서 **서식 있는 텍스트** 단추 ![RichTextContentControl](../vsto/media/richtextcontrol.png "RichTextContentControl")를 클릭하여 마지막 셀에 <xref:Microsoft.Office.Tools.Word.RichTextContentControl>을 추가합니다.  
  
## 프로그래밍 방식으로 콤보 상자 및 드롭다운 목록 채우기  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]의 **속성** 창을 사용하여 디자인 타임에 콘텐츠 컨트롤을 초기화할 수 있습니다.  런타임에 초기화할 수도 있으며, 이 경우 초기 상태를 동적으로 설정할 수 있습니다.  이 연습에서는 이러한 개체의 작동 방식을 확인할 수 있도록 코드를 사용하여 런타임에 <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> 및 <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>의 항목을 채웁니다.  
  
#### 프로그래밍 방식으로 콘텐츠 컨트롤의 UI를 수정하려면  
  
1.  **솔루션 탐색기**에서 **ThisDocument.cs** 또는 **ThisDocument.vb**를 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 클릭합니다.  
  
2.  `ThisDocument` 클래스에 다음 코드를 추가합니다.  이 코드는 이 연습의 뒷부분에서 사용할 여러 개체를 선언합니다.  
  
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlTemplateWalkthrough/CS/ThisDocument.cs#1)]
     [!code-vb[Trin_ContentControlTemplateWalkthrough#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlTemplateWalkthrough/VB/ThisDocument.vb#1)]  
  
3.  `ThisDocument` 클래스의 `ThisDocument_Startup` 메서드에 다음 코드를 추가합니다.  이 코드는 표의 <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> 및 <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>에 항목을 추가하고 사용자가 편집하기 전에 이러한 각 컨트롤에 표시되는 자리 표시자 텍스트를 설정합니다.  
  
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlTemplateWalkthrough/CS/ThisDocument.cs#2)]
     [!code-vb[Trin_ContentControlTemplateWalkthrough#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlTemplateWalkthrough/VB/ThisDocument.vb#2)]  
  
## 사용자가 Employee 표를 편집할 수 없도록 차단  
 앞에서 선언한 <xref:Microsoft.Office.Tools.Word.GroupContentControl> 개체를 사용하여 Employee 표를 보호합니다.  표를 보호한 후에도 사용자는 표의 콘텐츠 컨트롤을 편집할 수 있습니다.  그러나 첫 번째 열의 텍스트를 편집하거나 행과 열 추가 또는 삭제와 같이 다른 방식으로 표를 수정할 수는 없습니다.  <xref:Microsoft.Office.Tools.Word.GroupContentControl>을 사용하여 문서의 일부를 보호하는 방법에 대한 자세한 내용은 [콘텐츠 컨트롤](../vsto/content-controls.md)을 참조하세요.  
  
#### 사용자가 Employee 표를 편집할 수 없도록 하려면  
  
1.  이전 단계에서 추가한 코드 뒤에 있는 `ThisDocument` 클래스의 `ThisDocument_Startup` 메서드에 다음 코드를 추가합니다.  이 코드는 앞에서 선언한 <xref:Microsoft.Office.Tools.Word.GroupContentControl> 개체 안에 표를 넣어 사용자가 Employee 표를 편집할 수 없도록 합니다.  
  
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlTemplateWalkthrough/CS/ThisDocument.cs#3)]
     [!code-vb[Trin_ContentControlTemplateWalkthrough#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlTemplateWalkthrough/VB/ThisDocument.vb#3)]  
  
## 문서 블록 컬렉션에 표 추가  
 사용자가 생성된 표를 문서에 삽입할 수 있도록 서식 파일의 문서 블록 컬렉션에 표를 추가합니다.  문서 블록에 대한 자세한 내용은 [콘텐츠 컨트롤](../vsto/content-controls.md)을 참조하세요.  
  
#### 서식 파일의 문서 블록에 표를 추가하려면  
  
1.  이전 단계에서 추가한 코드 뒤에 있는 `ThisDocument` 클래스의 `ThisDocument_Startup` 메서드에 다음 코드를 추가합니다.  이 코드는 서식 파일에서 재사용 가능한 문서 블록을 모두 포함하는 Microsoft.Office.Interop.Word.BuildingBlockEntries 컬렉션에 표를 포함하는 새 문서 블록을 추가합니다.  새 문서 블록은 **직원 및 고객 정보**라는 새 범주에 정의되고 문서 블록 형식 Microsoft.Office.Interop.Word.WdBuildingBlockTypes.wdTypeCustom1이 할당됩니다.  
  
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlTemplateWalkthrough/CS/ThisDocument.cs#4)]
     [!code-vb[Trin_ContentControlTemplateWalkthrough#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlTemplateWalkthrough/VB/ThisDocument.vb#4)]  
  
2.  이전 단계에서 추가한 코드 뒤에 있는 `ThisDocument` 클래스의 `ThisDocument_Startup` 메서드에 다음 코드를 추가합니다.  이 코드는 서식 파일에서 표를 삭제합니다.  서식 파일에서 재사용 가능한 문서 블록 갤러리에 추가했으므로 표는 더 이상 필요하지 않습니다.  코드에서 먼저 보호된 Employee 표를 삭제할 수 있도록 문서를 디자인 모드로 설정합니다.  
  
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlTemplateWalkthrough/CS/ThisDocument.cs#5)]
     [!code-vb[Trin_ContentControlTemplateWalkthrough#5](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlTemplateWalkthrough/VB/ThisDocument.vb#5)]  
  
## 문서 블록을 표시하는 콘텐츠 컨트롤 만들기  
 앞에서 만든 문서 블록\(표\)에 대한 액세스를 제공하는 콘텐츠 컨트롤을 만듭니다.  사용자는 이 컨트롤을 클릭하여 문서에 표를 추가할 수 있습니다.  
  
#### 문서 블록을 표시하는 콘텐츠 컨트롤을 만들려면  
  
1.  이전 단계에서 추가한 코드 뒤에 있는 `ThisDocument` 클래스의 `ThisDocument_Startup` 메서드에 다음 코드를 추가합니다.  이 코드는 앞에서 선언한 <xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl> 개체를 초기화합니다.  <xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl>은 **직원 및 고객 정보** 범주에 정의되고 문서 블록 형식이 Microsoft.Office.Interop.Word.WdBuildingBlockTypes.wdTypeCustom1인 모든 문서 블록을 표시합니다.  
  
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#6](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlTemplateWalkthrough/CS/ThisDocument.cs#6)]
     [!code-vb[Trin_ContentControlTemplateWalkthrough#6](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlTemplateWalkthrough/VB/ThisDocument.vb#6)]  
  
## 프로젝트 테스트  
 사용자는 문서에서 문서 블록 갤러리 컨트롤을 클릭하여 Employee 표 또는 사용자 의견 표를 삽입할 수 있습니다.  사용자는 두 표의 콘텐츠 컨트롤에서 모두 응답을 입력하거나 선택할 수 있습니다.  사용자는 사용자 의견 표의 다른 부분을 수정할 수 있지만 Employee 표의 다른 부분은 수정할 수 없어야 합니다.  
  
#### Employee 표를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  **첫 번째 문서 블록 선택**을 클릭하여 첫 번째 문서 블록 갤러리 콘텐츠 컨트롤을 표시합니다.  
  
3.  컨트롤에서 **사용자 지정 갤러리 1** 제목 옆에 있는 드롭다운 화살표를 클릭하고 **Employee 표**를 선택합니다.  
  
4.  Employee Name 셀의 오른쪽에 있는 셀을 클릭하고 이름을 입력합니다.  
  
     이 셀에는 텍스트만 추가할 수 있음을 확인합니다.  <xref:Microsoft.Office.Tools.Word.PlainTextContentControl>을 통해 사용자는 텍스트만 추가할 수 있고 아트 또는 표와 같은 다른 콘텐츠 형식은 추가할 수 없습니다.  
  
5.  Hire Date 셀의 오른쪽에 있는 셀을 클릭하고 날짜 선택에서 날짜를 선택합니다.  
  
6.  Title 셀의 오른쪽에 있는 셀을 클릭하고 콤보 상자에서 직위 중 하나를 선택합니다.  
  
     필요에 따라 목록에 없는 직위의 이름을 입력합니다.  이는 <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl>에서 사용자가 항목 목록에서 선택하거나 사용자 고유의 항목을 입력할 수 있기 때문에 가능합니다.  
  
7.  Picture 셀의 오른쪽에 있는 셀에서 아이콘을 클릭하고 이미지를 찾아서 표시합니다.  
  
8.  표에 행 또는 열을 추가하고 표에서 행과 열을 삭제하는 작업을 시도합니다.  표를 수정할 수 없음을 확인합니다.  <xref:Microsoft.Office.Tools.Word.GroupContentControl>에서 수정하지 못하도록 합니다.  
  
#### 사용자 의견 표를 테스트하려면  
  
1.  **두 번째 문서 블록 선택**을 클릭하여 두 번째 문서 블록 갤러리 콘텐츠 컨트롤을 표시합니다.  
  
2.  컨트롤에서 **사용자 지정 갤러리 1** 제목 옆에 있는 드롭다운 화살표를 클릭하고 **Customer 표**를 선택합니다.  
  
3.  Customer Name 셀의 오른쪽에 있는 셀을 클릭하고 이름을 입력합니다.  
  
4.  Satisfaction Rating 셀의 오른쪽에 있는 셀을 클릭하고 사용 가능한 옵션 중 하나를 선택합니다.  
  
     사용자 고유의 항목을 입력할 수 없음을 확인합니다.  <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>에서는 사용자가 항목 목록에서 선택할 수만 있습니다.  
  
5.  Comments 셀의 오른쪽에 있는 셀을 클릭하고 주석을 입력합니다.  
  
     필요에 따라 아트 또는 포함된 표와 같은 텍스트 이외의 일부 콘텐츠를 추가합니다.  이는 <xref:Microsoft.Office.Tools.Word.RichTextContentControl>에서 사용자가 텍스트 이외의 다른 콘텐츠를 추가할 수 있기 때문입니다.  
  
6.  표에 행 또는 열을 추가하고 표에서 행과 열을 삭제할 수 있음을 확인합니다.  이는 <xref:Microsoft.Office.Tools.Word.GroupContentControl> 안에 넣어 표를 보호하지 않았기 때문에 가능합니다.  
  
7.  서식 파일을 닫습니다.  
  
## 다음 단계  
 다음 항목에서 콘텐츠 컨트롤을 사용하는 방법에 대해 자세히 알아볼 수 있습니다.  
  
-   문서에 포함된 사용자 지정 XML 부분이라는 XML 부분에 콘텐츠 컨트롤을 바인딩합니다.  자세한 내용은 [연습: 콘텐츠 컨트롤을 사용자 지정 XML 부분에 바인딩](../vsto/walkthrough-binding-content-controls-to-custom-xml-parts.md)을 참조하세요.  
  
## 참고 항목  
 [확장된 개체를 사용하여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [콘텐츠 컨트롤](../vsto/content-controls.md)   
 [방법: Word 문서에 콘텐츠 컨트롤 추가](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [방법: 콘텐츠 컨트롤을 사용하여 문서 부분 보호](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  