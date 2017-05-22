---
title: "리본 개요"
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
  - "사용자 지정 리본, 여러 가지 리본 메뉴"
  - "리본 메뉴 사용자 지정, 여러 가지 리본 메뉴"
  - "리본[Visual Studio에서 Office 개발]"
  - "리본[Visual Studio에서 Office 개발], 리본 메뉴 정보"
  - "리본[Visual Studio에서 Office 개발], 여러 가지 리본 메뉴"
  - "도구 모음[Visual Studio에서 Office 개발]"
  - "도구 모음[Visual Studio에서 Office 개발], 리본 메뉴"
ms.assetid: 2bdef092-190d-47e3-9440-e862b95dacaa
caps.latest.revision: 64
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 62
---
# 리본 개요
  리본은 쉽게 찾을 수 있도록 관련된 명령을 구성하는 방법입니다.  명령은 리본 메뉴에 컨트롤로 표시됩니다.  컨트롤은 응용 프로그램 창의 위쪽 가장자리에 있는 가로 스트립을 따라 *그룹*으로 구성됩니다.  관련 그룹은 탭에서 구성됩니다.  
  
 이전 버전의 Microsoft Office 시스템에서 메뉴와 도구 모음을 사용하여 액세스한 대부분의 기능을 이제 리본 메뉴에서 액세스할 수 있습니다.  자세한 내용은 기술 문서 [2007 Microsoft Office 시스템의 사용자 인터페이스 개발자 개요](http://go.microsoft.com/fwlink/?LinkID=70860)를 참조하세요.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
## Microsoft Office 리본 사용자 지정  
 리본을 사용자 지정하려면 다음 리본 항목 중 하나를 Office 프로젝트에 추가합니다.  
  
-   **리본\(비주얼 디자이너\)**  
  
-   **리본\(XML\)**  
  
 예를 들어 Excel 리본을 사용자 지정하려면 Excel VSTO 추가 기능 프로젝트에 리본 항목을 추가합니다.  
  
### 리본\(비주얼 디자이너\) 항목  
 **리본\(비주얼 디자이너\)** 항목은 쉽게 사용자 지정 리본을 디자인하고 개발할 수 있게 해주는 고급 도구를 제공합니다.  **리본\(비주얼 디자이너\)** 항목을 사용하여 다음과 같은 방법으로 리본을 사용자 지정합니다.  
  
-   리본에 사용자 지정 또는 기본 제공 탭을 추가합니다.  
  
-   사용자 지정 또는 기본 제공 탭에 사용자 지정 그룹을 추가합니다.  
  
    > [!NOTE]  
    >  기본 제공 탭 또는 그룹은 Microsoft Office 응용 프로그램의 리본에 이미 있는 항목입니다.  예를 들어 **데이터** 탭은 Excel의 기본 제공 탭입니다.  **연결** 그룹은 **데이터** 탭의 기본 제공 그룹입니다.  
  
-   사용자 지정 그룹에 사용자 지정 컨트롤을 추가합니다.  
  
-   Backstage 보기에 사용자 지정 컨트롤을 추가합니다.  
  
 **리본\(비주얼 디자이너\)** 항목을 사용하여 리본을 사용자 지정하는 방법에 대한 자세한 내용은 [리본 디자이너](../vsto/ribbon-designer.md)를 참조하세요.  
  
### 리본\(XML\) 항목  
 **리본\(비주얼 디자이너\)** 항목에서 지원하지 않는 방법으로 리본을 사용자 지정하려는 경우 **리본\(XML\)** 항목을 사용합니다.  **리본\(XML\)** 항목을 사용하여 다음과 같은 방법으로 리본을 사용자 지정합니다.  
  
-   사용자 지정 탭 또는 기본 제공 탭에 *기본 제공* 그룹을 추가합니다.  
  
-   사용자 지정 그룹에 기본 제공 컨트롤을 추가합니다.  
  
-   사용자 지정 코드를 추가하여 기본 제공 컨트롤의 이벤트 처리기를 재정의합니다.  
  
-   빠른 실행 도구 모음 사용자 지정  
  
-   정규화된 ID를 사용하여 VSTO 추가 기능 간에 리본 사용자 지정을 공유합니다.  
  
 **리본\(XML\)** 항목을 사용하여 리본을 사용자 지정하는 방법에 대한 자세한 내용은 [리본 XML](../vsto/ribbon-xml.md)을 참조하세요.  
  
## 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기  
 리본 디자이너를 사용하여 리본을 만든 다음 **리본\(비주얼 디자이너\)** 항목이 지원하지 않는 방법으로 리본을 사용자 지정하려는 경우 리본 메뉴를 XML로 내보낼 수 있습니다.  
  
 Visual Studio에서 자동으로 **리본\(XML\)** 항목을 만들고 리본 메뉴에 있는 각 컨트롤에 대한 요소와 특성으로 리본 XML 파일을 채웁니다.  
  
 리본 디자이너의 **속성** 창에 있는 속성 중 일부는 리본 XML 파일로 전송됩니다.  예를 들어 Visual Studio는 **이미지** 또는 **텍스트** 속성의 값을 내보내지 않습니다.  이는 이미지를 할당하거나 컨트롤의 텍스트를 설정하려면 내보낸 프로젝트의 리본 코드 파일에서 콜백 메서드를 만들어야 하기 때문입니다.  Visual Studio는 내보내기 프로세스의 일부로 콜백 메서드를 자동으로 생성하지 않습니다.  
  
 또한 변경되지 않은 기본 속성 값은 결과 리본 XML 파일에 표시되지 않습니다.  
  
 리본 메뉴를 XML로 내보내는 방법에 대한 자세한 내용은 [방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)를 참조하세요.  
  
### 코드 업데이트  
 새 리본 코드 파일이 **솔루션 탐색기**에 추가됩니다.  이 파일에는 리본 XML 클래스가 포함되어 있습니다.  단추 클릭과 같은 사용자 동작을 처리하려면 이 클래스의 `Ribbon Callbacks` 영역에 콜백 메서드를 만들어야 합니다.  이벤트 처리기의 코드를 이러한 콜백 메서드로 이동하고 리본 확장성\(RibbonX\) 프로그래밍 모델을 사용하도록 코드를 수정합니다.  자세한 내용은 [리본 XML](../vsto/ribbon-xml.md)을 참조하세요.  
  
 또한 CreateRibbonExtensibilityObject 메서드를 재정의하고 Office 응용 프로그램에 리본 XML 클래스를 반환하는 코드를 `ThisAddIn`, `ThisWorkbook` 또는 `ThisDocument` 클래스에 추가해야 합니다.  
  
 자세한 내용은 [리본 XML](../vsto/ribbon-xml.md)를 참조하세요.  
  
## 프로젝트에 여러 리본 항목 추가  
 단일 프로젝트에 둘 이상의 리본 항목을 추가할 수 있습니다.  이 기능은 다음 두 작업 중 하나를 수행하려는 경우에 유용합니다.  
  
-   Outlook *검사기*에 대한 리본을 만듭니다.  자세한 내용은 [Outlook에 대해 리본 메뉴 사용자 지정](../vsto/customizing-a-ribbon-for-outlook.md)을 참조하세요.  
  
    > [!NOTE]  
    >  검사기는 사용자가 메일 메시지 만들기와 같은 특정 작업을 수행할 때 열리는 창입니다.  
  
-   런타임에 표시할 리본을 선택합니다.  
  
### 런타임에 표시할 리본 선택  
 프로젝트에 둘 이상의 리본이 포함될 수 있으므로 런타임에 표시할 리본을 선택할 수 있습니다.  
  
 런타임에 표시할 리본을 선택하려면 프로젝트의 `ThisAddin`, `ThisWorkbook` 또는 `ThisDocument` 클래스에서 CreateRibbonExtensibilityObject 메서드를 재정의하고 표시할 리본을 반환합니다.  다음 예제에서는 `myCondition`이라는 필드의 값을 검사하고 적절한 리본을 반환합니다.  
  
> [!NOTE]  
>  이 예제에서 사용된 구문은 **리본\(비주얼 디자이너\)** 항목을 사용하여 만든 리본을 반환합니다.  **리본\(XML\)** 항목을 사용하여 만든 리본을 반환하는 구문은 약간 다릅니다.  **리본\(XML\)** 항목을 반환하는 방법에 대한 자세한 내용은 [리본 XML](../vsto/ribbon-xml.md)을 참조하세요.  
  
 다음 코드를 추가합니다.  
  
 [!code-csharp[Trin_Ribbon_Choose_Ribbon#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Ribbon_Choose_Ribbon/CS/ThisWorkbook.cs#1)]
 [!code-vb[Trin_Ribbon_Choose_Ribbon#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Ribbon_Choose_Ribbon/VB/ThisWorkbook.vb#1)]  
  
### 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)|Microsoft Office 응용 프로그램의 리본을 사용자 지정하고, **리본\(비주얼 디자이너\)** 또는 **리본\(XML\)** 항목을 Office 프로젝트에 추가하는 방법을 보여 줍니다.|  
|[리본 디자이너](../vsto/ribbon-designer.md)|리본 디자이너를 사용하여 Microsoft Office 응용 프로그램의 리본에 사용자 지정 탭, 그룹 및 컨트롤을 추가하는 방법을 설명합니다.|  
|[연습: 리본 디자이너를 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)|리본 디자이너를 사용하여 사용자 지정 리본 탭을 만드는 방법을 보여 줍니다.  리본 디자이너를 사용하여 사용자 지정 탭에 컨트롤을 추가하고 배치할 수 있습니다.|  
|[리본 개체 모델 개요](../vsto/ribbon-object-model-overview.md)|런타임에 리본 컨트롤의 속성을 가져오고 설정하는 데 사용할 수 있는 강력한 형식의 개체 모델에 대해 설명합니다.|  
|[연습: 런타임에 리본 메뉴의 컨트롤 업데이트](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)|리본이 Office 응용 프로그램에 로드된 후 리본 개체 모델을 사용하여 리본 메뉴의 컨트롤을 업데이트하는 방법을 보여 줍니다.|  
|[Outlook에 대해 리본 메뉴 사용자 지정](../vsto/customizing-a-ribbon-for-outlook.md)|Microsoft Office Outlook에서 리본을 사용자 지정하는 방법에 대한 지침을 제공합니다.|  
|[InfoPath에 대해 리본 메뉴 사용자 지정](../vsto/customizing-a-ribbon-for-infopath.md)|Microsoft Office InfoPath에서 리본을 사용자 지정하는 방법에 대한 지침을 제공합니다.|  
|[런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)|리본을 표시, 숨기기 및 수정하고, 사용자가 사용자 지정 작업창, 작업 창 또는 Outlook 양식 영역의 컨트롤에서 코드를 실행할 수 있도록 하는 방법을 보여 줍니다.|  
|[방법: 리본의 탭 위치 변경](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)|리본 메뉴의 탭 순서를 변경하는 방법을 보여 줍니다.|  
|[방법: 기본 제공 탭 사용자 지정](../vsto/how-to-customize-a-built-in-tab.md)|기본 제공 탭에 그룹 및 컨트롤을 추가하는 방법을 보여 줍니다.|  
|[방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)|**파일**을 클릭할 때 열리는 메뉴에 컨트롤을 추가하는 방법을 보여 줍니다.|  
|[방법: 리본 그룹에 대화 상자 시작 관리자 추가](../vsto/how-to-add-a-dialog-box-launcher-to-a-ribbon-group.md)|리본 메뉴의 임의 그룹에 대화 상자 표시 아이콘을 추가하는 방법을 보여 줍니다.|  
|[방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)|디자이너에서 리본 XML로 리본 메뉴를 내보내 고급 방식으로 리본을 사용자 지정하는 방법을 보여 줍니다.|  
|[리본 XML](../vsto/ribbon-xml.md)|리본 XML을 사용하여 리본을 사용자 지정하는 방법을 설명합니다.|  
|[연습: 리본 디자이너를 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)|**본\(XML\)** 항목을 사용하여 사용자 지정 리본 탭을 만드는 방법을 보여 줍니다.|  
  
  