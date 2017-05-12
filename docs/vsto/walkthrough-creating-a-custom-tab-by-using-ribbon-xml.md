---
title: "연습: 리본 XML을 사용하여 사용자 지정 탭 만들기"
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
  - "사용자 지정 탭[Visual Studio에서 Office 개발]"
  - "리본 메뉴 사용자 지정, tabscustom 리본, 탭"
  - "리본[Visual Studio에서 Office 개발], 사용자 지정"
  - "리본[Visual Studio에서 Office 개발], 탭"
  - "리본[Visual Studio에서 Office 개발], XML"
  - "XML[Visual Studio에서 Office 개발], 리본 메뉴"
ms.assetid: f6391a01-df1a-4a0f-bfbb-a9526c73b2b3
caps.latest.revision: 35
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 34
---
# 연습: 리본 XML을 사용하여 사용자 지정 탭 만들기
  이 연습에서는 **리본\(XML\)** 항목을 사용하여 사용자 지정 리본 탭을 만드는 방법을 보여 줍니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   **추가 기능** 탭에 단추 추가  **추가 기능** 탭은 리본 XML 파일에 정의된 기본 탭입니다.  
  
-   **추가 기능** 탭의 단추를 사용하여 Microsoft Office Word 자동화  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## 프로젝트 만들기  
 첫 번째 단계는 Word VSTO 추가 기능 프로젝트를 만드는 것입니다.  나중에 이 문서의 **추가 기능** 탭을 사용자 지정합니다.  
  
#### 새 프로젝트를 만들려면  
  
1.  이름이 MyRibbonAddIn인 **Word 추가 기능** 프로젝트를 만듭니다.  
  
     자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)를 참조하세요.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 **ThisAddIn.cs** 또는 **ThisAddIn.vb** 코드 파일을 열고 **MyRibbonAddIn** 프로젝트를 **솔루션 탐색기**에 추가합니다.  
  
## VSTO 추가 기능 탭 만들기  
 **추가 기능** 탭을 만들려면 프로젝트에 **리본\(XML\)** 항목을 추가합니다.  이 연습의 뒷부분에서는 이 탭에 일부 단추를 추가합니다.  
  
#### 추가 기능 탭을 만들려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
2.  **새 항목 추가** 대화 상자에서 **리본\(XML\)**을 선택합니다.  
  
3.  새 리본 메뉴의 이름을 **MyRibbon**으로 변경하고 **추가**를 클릭합니다.  
  
     **MyRibbon.cs** 또는 **MyRibbon.vb** 파일이 디자이너에서 열립니다.  **MyRibbon.xml**이라는 XML 파일도 프로젝트에 추가됩니다.  
  
4.  **솔루션 탐색기**에서 **ThisAddin.cs** 또는 **ThisAddin.vb**를 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 클릭합니다.  
  
5.  **ThisAddin** 클래스에 다음 코드를 추가합니다.  이 코드는 CreateRibbonExtensibilityObject 메서드를 재정의하고 Office 응용 프로그램에 리본 XML 클래스를 반환합니다.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab_XML#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Ribbon_Custom_Tab_XML/CS/ThisAddIn.cs#1)]
     [!code-vb[Trin_Ribbon_Custom_Tab_XML#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Ribbon_Custom_Tab_XML/VB/ThisAddIn.vb#1)]  
  
6.  **솔루션 탐색기**에서 **MyRibbonAddIn** 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **빌드**를 클릭합니다.  프로젝트가 오류 없이 빌드되는지 확인합니다.  
  
## 추가 기능 탭에 단추 추가  
 이 VSTO 추가 기능은 활성 문서에 상용구 텍스트 및 특정 표를 추가하는 방법을 사용자에게 제공하기 위한 것입니다.  사용자 인터페이스를 제공하기 위해 리본 XML 파일을 수정하여 **추가 기능** 탭에 두 단추를 추가합니다.  이 연습의 뒷부분에서 단추에 대한 콜백 메서드를 정의합니다.  리본 XML 파일에 대한 자세한 내용은 [리본 XML](../vsto/ribbon-xml.md)을 참조하세요.  
  
#### 추가 기능 탭에 단추를 추가하려면  
  
1.  **솔루션 탐색기**에서 **MyRibbon.xml**을 마우스 오른쪽 단추로 클릭하고 **열기**를 클릭합니다.  
  
2.  **tab** 요소의 내용을 다음 XML로 바꿉니다.  이 XML은 기본 컨트롤 그룹의 레이블을 **Content**로 변경하고 레이블이 각각 **Insert Text** 및 **Insert Table**인 두 단추를 새로 추가합니다.  
  
    ```  
    <tab idMso="TabAddIns">  
        <group id="ContentGroup" label="Content">  
            <button id="textButton" label="Insert Text"  
                 screentip="Text" onAction="OnTextButton"  
                 supertip="Inserts text at the cursor location."/>  
            <button id="tableButton" label="Insert Table"  
                 screentip="Table" onAction="OnTableButton"  
                 supertip="Inserts a table at the cursor location."/>  
        </group>  
    </tab>  
    ```  
  
## 단추를 사용하여 문서 자동화  
 사용자가 단추를 클릭할 때 작업을 수행하려면 **Insert Text** 및 **Insert Table** 단추에 대한 `onAction` 콜백 메서드를 추가해야 합니다.  리본 컨트롤의 콜백 메서드에 대한 자세한 내용은 [리본 XML](../vsto/ribbon-xml.md)을 참조하세요.  
  
#### 단추에 대한 콜백 메서드를 추가하려면  
  
1.  **솔루션 탐색기**에서 **MyRibbon.cs** 또는 **MyRibbon.vb**를 마우스 오른쪽 단추로 클릭하고 **열기**를 클릭합니다.  
  
2.  **MyRibbon.cs** 또는 **MyRibbon.vb** 파일의 맨 위에 다음 코드를 추가합니다.  이 코드는 <xref:Microsoft.Office.Interop.Word> 네임스페이스에 대한 별칭을 만듭니다.  
  
     [!code-csharp[Trin_RibbonButtons#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_RibbonButtons/CS/MyRibbon.cs#1)]
     [!code-vb[Trin_RibbonButtons#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_RibbonButtons/VB/MyRibbon.vb#1)]  
  
3.  다음 메서드를 `MyRibbon` 클래스에 추가합니다.  이는 활성 문서에서 커서의 현재 위치에 문자열을 추가하는 **Insert Text** 단추에 대한 콜백 메서드입니다.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab_XML#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Ribbon_Custom_Tab_XML/CS/MyRibbon.cs#2)]
     [!code-vb[Trin_Ribbon_Custom_Tab_XML#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Ribbon_Custom_Tab_XML/VB/MyRibbon.vb#2)]  
  
4.  다음 메서드를 `MyRibbon` 클래스에 추가합니다.  이는 활성 문서에서 커서의 현재 위치에 표를 추가하는 **Insert Table** 단추에 대한 콜백 메서드입니다.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab_XML#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Ribbon_Custom_Tab_XML/CS/MyRibbon.cs#3)]
     [!code-vb[Trin_Ribbon_Custom_Tab_XML#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Ribbon_Custom_Tab_XML/VB/MyRibbon.vb#3)]  
  
## VSTO 추가 기능 테스트  
 프로젝트를 실행하면 Word가 열리고 **추가 기능**이라는 탭이 리본 메뉴에 나타납니다.  **추가 기능** 탭에서 **Insert Text** 및 **Insert Table** 단추를 클릭하여 코드를 테스트합니다.  
  
#### VSTO 추가 기능을 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  **추가 기능** 탭이 리본 메뉴에 표시되는지 확인합니다.  
  
3.  **추가 기능** 탭을 클릭합니다.  
  
4.  **콘텐츠** 그룹이 리본 메뉴에 표시되는지 확인합니다.  
  
5.  **콘텐츠** 그룹에서 **Insert Text** 단추를 클릭합니다.  
  
     문서에서 커서의 현재 위치에 문자열이 추가됩니다.  
  
6.  **콘텐츠** 그룹에서 **Insert Table** 단추를 클릭합니다.  
  
     문서에서 커서의 현재 위치에 표가 추가됩니다.  
  
## 다음 단계  
 다음 항목에서는 Office UI를 사용자 지정하는 방법에 대해 더 자세히 설명합니다.  
  
-   다른 Office 응용 프로그램의 리본 메뉴를 사용자 지정합니다.  리본 메뉴 사용자 지정을 지원하는 응용 프로그램에 대한 자세한 내용은 [리본 개요](../vsto/ribbon-overview.md)을 참조하세요.  
  
-   리본 디자이너를 사용하여 Office 응용 프로그램의 리본 메뉴를 사용자 지정합니다.  자세한 내용은 [리본 디자이너](../vsto/ribbon-designer.md)를 참조하세요.  
  
-   사용자 지정 작업 창을 만듭니다.  자세한 내용은 [작업 창 개요](../vsto/actions-pane-overview.md)를 참조하세요.  
  
-   Outlook 양식 영역을 사용하여 Microsoft Office Outlook의 UI를 사용자 지정합니다.  자세한 내용은 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)를 참조하세요.  
  
## 참고 항목  
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 XML](../vsto/ribbon-xml.md)   
 [연습: 리본 디자이너를 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)  
  
  