---
title: "연습: 리본 XML을 사용 하 여 사용자 지정 탭 만들기 | Microsoft Docs"
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
- Ribbon [Office development in Visual Studio], tabs
- customizing the Ribbon, tabscustom Ribbon, tabs
- Ribbon [Office development in Visual Studio], XML
- XML [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], customizing
- Custom tab [Office development in Visual Studio]
ms.assetid: f6391a01-df1a-4a0f-bfbb-a9526c73b2b3
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 8933345017cef96c17ed69a42dc3e095fcf7c7ae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-custom-tab-by-using-ribbon-xml"></a>Walkthrough: Creating a Custom Tab by Using Ribbon XML
  이 연습에서는를 사용 하 여 사용자 지정 리본 탭을 만드는 방법을 보여 줍니다.는 **리본 (XML)** 항목입니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   에 단추 추가 **Add-ins** 탭 합니다. **Add-ins** 탭은 리본 XML 파일에 정의 된 기본 탭 합니다.  
  
-   에 있는 단추를 사용 하 여 Microsoft Office Word를 자동화는 **Add-ins** 탭 합니다.  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계는 Word VSTO 추가 기능 프로젝트를 만드는 것입니다. 에 나중에 사용자 지정의 **추가 기능** 이 문서의 탭 합니다.  
  
#### <a name="to-create-a-new-project"></a>새 프로젝트를 만들려면  
  
1.  만들기는 **Word 추가 기능에** 이름의 프로젝트가 **MyRibbonAddIn**합니다.  
  
     자세한 내용은 [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하세요.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]열립니다는 **ThisAddIn.cs** 또는 **ThisAddIn.vb** 코드 파일을 추가 하는 **MyRibbonAddIn** 프로젝트를 **솔루션 탐색기**합니다.  
  
## <a name="creating-the-vsto-add-ins-tab"></a>VSTO 추가 기능 탭 만들기  
 만들려는 **추가 기능** 탭에서 추가 **리본 (XML)** 항목을 프로젝트입니다. 이 연습의 뒷부분에서는 이 탭에 일부 단추를 추가합니다.  
  
#### <a name="to-create-the-add-ins-tab"></a>추가 기능 탭을 만들려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
2.  에 **새 항목 추가** 대화 상자에서 **리본 (XML)**합니다.  
  
3.  새 리본 메뉴의 이름을 **MyRibbon**으로 변경하고 **추가**를 클릭합니다.  
  
     **MyRibbon.cs** 또는 **MyRibbon.vb** 파일이 디자이너에서 열립니다. 명명 된 XML 파일로 **MyRibbon.xml** 프로젝트에도 추가 됩니다.  
  
4.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **ThisAddin.cs** 또는 **ThisAddin.vb**, 클릭 하 고 **코드 보기**합니다.  
  
5.  **ThisAddin** 클래스에 다음 코드를 추가합니다. 이 코드 프로젝트 메서드를 재정의 하 고 Office 응용 프로그램에 리본 XML 클래스를 반환 합니다.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.cs#1)]
     [!code-vb[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.vb#1)]  
  
6.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **MyRibbonAddIn** 프로젝트를 마우스 클릭 **빌드**합니다. 프로젝트가 오류 없이 빌드되는지 확인합니다.  
  
## <a name="adding-buttons-to-the-add-ins-tab"></a>추가 기능 탭에 단추 추가  
 이 VSTO 추가 기능은 활성 문서에 상용구 텍스트 및 특정 표를 추가하는 방법을 사용자에게 제공하기 위한 것입니다. 사용자 인터페이스를 제공 하려면 두 단추를 추가 **Add-ins** 리본 XML 파일을 수정 하 여 탭 합니다. 이 연습의 뒷부분에서 단추에 대한 콜백 메서드를 정의합니다. 리본 XML 파일에 대 한 자세한 내용은 참조 [리본 XML](../vsto/ribbon-xml.md)합니다.  
  
#### <a name="to-add-buttons-to-the-add-ins-tab"></a>추가 기능 탭에 단추를 추가하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **MyRibbon.xml** 클릭 하 고 **열려**합니다.  
  
2.  내용을 대체는 **탭** 다음 xml 요소입니다. 이 XML에 기본 컨트롤 그룹의 레이블을 변경 **콘텐츠**는 레이블이 있는 두 개의 새 단추가 추가 **텍스트 삽입** 및 **표 삽입**합니다.  
  
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
  
## <a name="automating-the-document-by-using-the-buttons"></a>단추를 사용하여 문서 자동화  
 추가 해야 `onAction` 에 대 한 콜백 메서드는 **텍스트 삽입** 및 **표 삽입** 단추를 클릭 하는 경우 작업을 수행 합니다. 리본 컨트롤에 대 한 콜백 메서드에 대 한 자세한 내용은 참조 [리본 XML](../vsto/ribbon-xml.md)합니다.  
  
#### <a name="to-add-callback-methods-for-the-buttons"></a>단추에 대한 콜백 메서드를 추가하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **MyRibbon.cs** 또는 **MyRibbon.vb**, 클릭 하 고 **열려**합니다.  
  
2.  맨 위에 다음 코드를 추가 **MyRibbon.cs** 또는 **MyRibbon.vb** 파일입니다. 이 코드는 <xref:Microsoft.Office.Interop.Word> 네임스페이스에 대한 별칭을 만듭니다.  
  
     [!code-csharp[Trin_RibbonButtons#1](../vsto/codesnippet/CSharp/Trin_RibbonButtons/MyRibbon.cs#1)]
     [!code-vb[Trin_RibbonButtons#1](../vsto/codesnippet/VisualBasic/Trin_RibbonButtons/MyRibbon.vb#1)]  
  
3.  다음 메서드를 `MyRibbon` 클래스에 추가합니다. 이에 대 한 콜백 메서드는 **텍스트 삽입** 활성 문서에서 커서의 현재 위치에 문자열을 추가 하는 단추입니다.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab_XML#2](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab_XML_O12/MyRibbon.cs#2)]
     [!code-vb[Trin_Ribbon_Custom_Tab_XML#2](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab_XML_O12/MyRibbon.vb#2)]  
  
4.  다음 메서드를 `MyRibbon` 클래스에 추가합니다. 이것은 대 한 콜백 메서드는 **표 삽입** 단추 커서의 현재 위치에서 현재 문서에 표를 추가 합니다.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab_XML#3](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab_XML_O12/MyRibbon.cs#3)]
     [!code-vb[Trin_Ribbon_Custom_Tab_XML#3](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab_XML_O12/MyRibbon.vb#3)]  
  
## <a name="testing-the-vsto-add-in"></a>VSTO 추가 기능 테스트  
 프로젝트, Word가 열리고 이라는 탭을 실행할 때 **추가 기능** 리본 메뉴에 나타납니다. 클릭는 **텍스트 삽입** 및 **표 삽입** 단추를 **추가 기능** 탭 하면 코드를 테스트 합니다.  
  
#### <a name="to-test-your-vsto-add-in"></a>VSTO 추가 기능을 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  확인 하는 **추가 기능** 탭이 리본 메뉴에 표시 됩니다.  
  
3.  **추가 기능** 탭을 클릭합니다.  
  
4.  확인 된 **콘텐츠** 그룹이 리본 메뉴에 표시 되는지 합니다.  
  
5.  클릭는 **텍스트 삽입** 단추는 **콘텐츠** 그룹입니다.  
  
     문서에서 커서의 현재 위치에 문자열이 추가됩니다.  
  
6.  클릭는 **표 삽입** 단추는 **콘텐츠** 그룹입니다.  
  
     문서에서 커서의 현재 위치에 표가 추가됩니다.  
  
## <a name="next-steps"></a>다음 단계  
 다음 항목에서는 Office UI를 사용자 지정하는 방법에 대해 더 자세히 설명합니다.  
  
-   다른 Office 응용 프로그램의 리본 메뉴를 사용자 지정합니다. 리본 메뉴 사용자 지정을 지원 되는 응용 프로그램에 대 한 자세한 내용은 참조 [리본 개요](../vsto/ribbon-overview.md)합니다.  
  
-   리본 디자이너를 사용하여 Office 응용 프로그램의 리본 메뉴를 사용자 지정합니다. 자세한 내용은 [Ribbon Designer](../vsto/ribbon-designer.md)을 참조하십시오.  
  
-   사용자 지정 작업 창을 만듭니다. 자세한 내용은 [Actions Pane Overview](../vsto/actions-pane-overview.md)을 참조하십시오.  
  
-   Outlook 양식 영역을 사용하여 Microsoft Office Outlook의 UI를 사용자 지정합니다. 자세한 내용은 참조 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 XML](../vsto/ribbon-xml.md)   
 [연습: 리본 디자이너를 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)  
  
  