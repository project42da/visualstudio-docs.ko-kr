---
title: "연습: VSTO의 서비스에서 데이터 바인딩 추가 기능에서 프로젝트 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- databases [Office development in Visual Studio], scrolling records
- records [Office development in Visual Studio], scrolling
- data [Office development in Visual Studio], scrolling database records
ms.assetid: 9b008be4-06a3-4ffc-9f02-79dd6cfe00ab
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 035b74048aca3b91449bc857a36594bc280065c4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-binding-to-data-from-a-service-in-a-vsto-add-in-project"></a>연습: VSTO 추가 기능 프로젝트의 서비스에서 데이터 바인딩
  VSTO 추가 기능 프로젝트에서 호스트 컨트롤에 데이터를 바인딩할 수 있습니다. 이 연습에서는 Microsoft Office Word 문서에 컨트롤을 추가하고, MSDN 콘텐츠 서비스에서 검색된 데이터에 컨트롤을 바인딩하고, 런타임에 이벤트에 응답하는 방법을 보여 줍니다.  
  
 **적용 대상:** 이 항목의 정보는 Word 2010의 응용 프로그램 수준 프로젝트에 적용됩니다. 자세한 내용은 [Features Available by Office Application and Project Type](../vsto/features-available-by-office-application-and-project-type.md)을 참조하세요.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   런타임에 문서에 <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 컨트롤 추가  
  
-   <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 컨트롤을 웹 서비스의 데이터에 바인딩  
  
-   <xref:Microsoft.Office.Tools.Word.ContentControlBase.Entering> 컨트롤의 <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 이벤트에 응답  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] 또는 [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]  
  
## <a name="creating-a-new-project"></a>새 프로젝트 만들기  
 첫 번째 단계는 Word VSTO 추가 기능 프로젝트를 만드는 것입니다.  
  
#### <a name="to-create-a-new-project"></a>새 프로젝트를 만들려면  
  
1.  Visual Basic 또는 C#을 사용하여 이름이 **MTPS 콘텐츠 서비스**인 Word VSTO 추가 기능 프로젝트를 만듭니다.  
  
     자세한 내용은 [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하세요.  
  
     Visual Studio에 `ThisAddIn.vb` 또는 `ThisAddIn.cs` 파일이 열리고 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
## <a name="adding-a-web-service"></a>웹 서비스 추가  
 이 연습에서는 MTPS 콘텐츠 서비스라는 웹 서비스를 사용합니다. 이 웹 서비스는 지정된 MSDN 문서의 정보를 XML 문자열 또는 일반 텍스트 형식으로 반환합니다. 이후 단계에서는 반환된 정보를 콘텐츠 컨트롤에 표시하는 방법을 보여 줍니다.  
  
#### <a name="to-add-the-mtps-content-service-to-the-project"></a>MTPS 콘텐츠 서비스를 프로젝트에 추가하려면  
  
1.  **데이터** 메뉴에서 **새 데이터 소스 추가**를 클릭합니다.  
  
2.  **데이터 소스 구성 마법사**에서 **서비스**를 클릭하고 **다음**을 클릭합니다.  
  
3.  **주소** 필드에 다음 URL을 입력합니다.  
  
     **http://services.msdn.microsoft.com/ContentServices/ContentService.asmx**  
  
4.  **찾기**를 클릭합니다.  
  
5.  **네임스페이스** 필드에 **ContentService**를 입력하고 **확인**을 클릭합니다.  
  
6.  **참조 추가 마법사** 대화 상자에서 **마침**을 클릭합니다.  
  
## <a name="adding-a-content-control-and-binding-to-data-at-run-time"></a>런타임에 콘텐츠 컨트롤 추가 및 데이터 바인딩  
 VSTO 추가 기능 프로젝트에서 런타임에 컨트롤을 추가 및 바인딩할 수 있습니다. 이 연습에서는 사용자가 컨트롤 내부를 클릭할 때 웹 서비스에서 데이터를 가져오도록 콘텐츠 컨트롤을 구성합니다.  
  
#### <a name="to-add-a-content-control-and-bind-to-data"></a>콘텐츠 컨트롤을 추가하고 데이터에 바인딩하려면  
  
1.  `ThisAddIn` 클래스에서 MTPS 콘텐츠 서비스, 콘텐츠 컨트롤 및 데이터 바인딩에 대한 변수를 선언합니다.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#2](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#2)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#2](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#2)]  
  
2.  다음 메서드를 `ThisAddIn` 클래스에 추가합니다. 이 메서드는 활성 문서 시작 부분에 콘텐츠 컨트롤을 만듭니다.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#4](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#4)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#4](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#4)]  
  
3.  다음 메서드를 `ThisAddIn` 클래스에 추가합니다. 이 메서드는 요청을 만들어 웹 서비스로 보내는 데 필요한 개체를 초기화합니다.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#6](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#6)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#6](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#6)]  
  
4.  사용자가 콘텐츠 컨트롤 내부를 클릭할 때 콘텐츠 컨트롤에 대한 MSDN 라이브러리 문서를 검색하고 데이터를 콘텐츠 컨트롤에 바인딩하는 이벤트 처리기를 만듭니다.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#5](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#5)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#5](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#5)]  
  
5.  `AddRichTextControlAtRange` 메서드에서 `InitializeServiceObjects` 및 `ThisAddIn_Startup` 메서드를 호출합니다. C# 프로그래머의 경우 이벤트 처리기를 추가합니다.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#3](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#3)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#3](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#3)]  
  
## <a name="testing-the-add-in"></a>추가 기능 테스트  
 Word를 열면 <xref:Microsoft.Office.Tools.Word.RichTextContentControl> 컨트롤이 나타납니다. 컨트롤 내부를 클릭하면 컨트롤의 텍스트가 변경됩니다.  
  
#### <a name="to-test-the-vsto-add-in"></a>VSTO 추가 기능을 테스트하려면  
  
1.  **F5**키를 누릅니다.  
  
2.  콘텐츠 컨트롤의 내부를 클릭합니다.  
  
     MTPS 콘텐츠 서비스에서 정보가 다운로드되어 콘텐츠 컨트롤 내부에 표시됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  