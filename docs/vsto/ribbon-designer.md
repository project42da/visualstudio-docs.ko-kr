---
title: "리본 디자이너 | Microsoft Docs"
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
  - "Designer_Microsoft.VisualStudio.Tools.Office.Ribbon.Design.RibbonDesigner"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "컨트롤[Visual Studio에서 Office 개발], 리본 메뉴"
  - "사용자 지정 리본"
  - "사용자 지정 리본, 리본 디자이너 정보"
  - "리본 메뉴 사용자 지정"
  - "리본 메뉴 사용자 지정, 리본 디자이너 정보"
  - "디자이너[Visual Studio에서 Office 개발], 리본 메뉴"
  - "읽기 전용 속성"
  - "리본[Visual Studio에서 Office 개발], 일반 작업"
  - "리본[Visual Studio에서 Office 개발], 컨트롤"
  - "리본[Visual Studio에서 Office 개발], 사용자 지정"
  - "리본[Visual Studio에서 Office 개발], 바로 가기 키"
  - "리본[Visual Studio에서 Office 개발], 비주얼 디자이너"
  - "리본 디자이너[Visual Studio에서 Office 개발]"
ms.assetid: 26617206-f4da-416f-a18a-d817b2d4872d
caps.latest.revision: 79
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 78
---
# 리본 디자이너
  리본 디자이너는 비주얼 디자인 캔버스입니다.  리본 디자이너를 사용하여 Microsoft Office 응용 프로그램의 리본 메뉴에 사용자 지정 탭, 그룹 및 컨트롤을 추가할 수 있습니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
 리본 디자이너를 열려면 프로젝트에 **리본\(비주얼 디자이너\)** 항목을 추가합니다.  그러면 다음 작업에 디자인 도구를 사용할 수 있습니다.  
  
-   [리본 메뉴 레이아웃 디자인](#DesigningRibbonLayout)  
  
-   [이벤트 처리 및 컨트롤 속성 설정](#HandleEventsSetProperties)  
  
-   [Backstage 보기에 컨트롤을 추가합니다.](#CustomizingMicrosoftOfficeButton)  
  
> [!NOTE]  
>  리본 디자이너를 사용하여 수행할 수 없는 작업도 몇 가지 있습니다.  이러한 작업에 대한 자세한 내용과 이러한 작업을 수행하는 방법은 [리본 개요](../vsto/ribbon-overview.md)을 참조하십시오.  
  
 ![비디오에 링크](../vsto/media/playvideo.png "비디오에 링크") 관련 비디오 데모를 보려면 [How Do I: Use the Ribbon Designer to Customize the Ribbon in Outlook?](http://go.microsoft.com/fwlink/?LinkID=130312)을 참조하십시오.  
  
## 프로젝트에 리본\(비주얼 디자이너\) 항목 추가  
 리본 디자이너를 사용하려면 프로젝트에 새 **리본\(비주얼 디자이너\)** 항목을 추가합니다.  자세한 내용은 [방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)을 참조하십시오.  
  
 새 **리본\(비주얼 디자이너\)** 항목을 추가하는 경우 Visual Studio에서는 프로젝트에 다음 파일을 자동으로 추가합니다.  
  
-   리본 코드 파일.  이 파일에는 **새 항목 추가** 대화 상자에서 **리본\(비주얼 디자이너\)** 항목에 지정한 이름이 지정됩니다.  리본 이벤트를 처리하는 코드를 이 파일에 추가합니다.  
  
-   리본 디자이너 코드 파일.  이 파일에는 리본 디자이너에서 생성된 코드가 들어 있으며 이 파일을 직접 편집하면 안 됩니다.  
  
-   리소스 파일.  이 파일에는 리본 메뉴의 각 컨트롤에 대한 속성 값이 들어 있습니다.  
  
 다른 프로젝트의 **리본\(비주얼 디자이너\)** 항목이 이미 있는 경우 **기존 항목 추가** 대화 상자를 사용하여 현재 프로젝트에 해당 항목을 다시 사용할 수 있습니다.  
  
##  <a name="DesigningRibbonLayout"></a> 리본 메뉴 디자인  
 리본 디자이너를 여는 방법에는 다음 세 가지가 있습니다.  
  
-   **솔루션 탐색기**에서 리본 코드 파일을 두 번 클릭합니다.  
  
-   **솔루션 탐색기**에서 리본 코드 파일을 마우스 오른쪽 단추로 클릭한 다음 **디자이너 보기**를 클릭합니다.  
  
-   **솔루션 탐색기**에서 리본 코드 파일을 선택한 다음 **보기** 메뉴에서 **디자이너**를 클릭합니다.  
  
 리본 디자이너에는 기본 탭 및 그룹이 포함되어 있습니다.  이 기본 탭 및 그룹을 리본 디자이너에서 제거할 수 있습니다.  기본 그룹을 제거하려면 **Group1**을 마우스 오른쪽 단추로 클릭하고 **삭제**를 클릭합니다.  기본 탭을 제거하려면 디자인 화면의 빈 영역을 마우스 오른쪽 단추로 클릭하고 **리본 탭 제거**를 클릭합니다.  
  
 리본 디자이너에 사용자 지정 탭, 그룹 및 컨트롤을 추가할 수도 있습니다.  이러한 컨트롤은 **도구 상자**의 **Office 리본 컨트롤** 그룹에서 찾을 수 있습니다.  다음 세 가지 방법으로 **Office 리본 컨트롤** 그룹의 컨트롤을 리본 디자이너에 추가할 수 있습니다.  
  
-   리본 디자이너의 적절한 영역으로 컨트롤을 끌어 옵니다.  
  
-   컨트롤을 클릭한 다음 리본 디자이너에서 적절한 영역을 클릭합니다.  
  
-   디자이너에서 적절한 영역을 선택한 다음 **도구 상자**의 컨트롤을 두 번 클릭합니다.  
  
### 리본 디자인 워크플로  
 다음 기본 단계에 따라 리본 메뉴 레이아웃을 디자인합니다.  
  
1.  [리본 메뉴에 사용자 지정 탭 추가](#AddTabToRibbon).  
  
2.  [탭에 그룹 추가](#AddGroupsToTab).  
  
3.  [그룹에 컨트롤 추가](#AddControlsToGroups).  
  
 컨트롤은 그룹에만 끌어 놓을 수 있으며 탭이나 리본 메뉴에는 직접 끌어 놓을 수 없습니다.  그룹은 탭에만 끌어 놓을 수 있으며 리본 메뉴에는 직접 끌어 놓을 수 없습니다.  
  
 컨트롤을 올바른 위치로 끌어서 정렬합니다.  **속성** 창에서 컨트롤의 속성을 설정할 수 있습니다.  
  
 한 탭의 컨트롤을 리본 메뉴의 다른 탭으로 끌어 놓을 수는 없습니다.  컨트롤을 다른 탭으로 이동하려면 **잘라내기** 명령을 사용하여 한 탭에서 컨트롤을 제거한 다음 해당 컨트롤을 다른 탭에 붙여넣어야 합니다.  컨트롤을 잘라내어 붙여넣을 경우 이벤트 처리기의 작동이 중지됩니다.  **속성** 창에서 이벤트 처리기를 다시 연결할 수 있습니다.  자세한 내용은 [속성 창](../ide/reference/properties-window.md)을 참조하십시오.  
  
###  <a name="AddTabToRibbon"></a> 리본 메뉴에 사용자 지정 탭 추가  
 다음 세 가지 방법으로 리본 메뉴에 사용자 지정 탭을 추가할 수 있습니다.  
  
-   **도구 상자**에서 탭을 추가합니다.  
  
-   리본 디자이너를 마우스 오른쪽 단추로 클릭한 다음 **리본 탭 추가**를 클릭합니다.  
  
-   **탭 컬렉션 편집기**를 열고 **추가**를 클릭합니다.  
  
     **탭 컬렉션 편집기**를 열려면 **속성** 창에서 **Tabs** 속성을 선택하고 줄임표 단추 ![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.png "ASP.NET 모바일 디자이너 줄임표")를 클릭합니다.  
  
 탭을 추가한 후 컨트롤을 포함할 그룹을 추가할 수 있습니다.  
  
#### 리본 메뉴에서 사용자 지정 탭 제거  
 다음 세 가지 방법으로 리본 메뉴에서 사용자 지정 탭을 제거할 수 있습니다.  
  
-   디자이너를 마우스 오른쪽 단추로 클릭한 다음 **리본 탭 제거**를 클릭합니다.  
  
-   **속성** 창의 **명령** 창에서 **리본 탭 제거**를 클릭합니다.  
  
-   **탭 컬렉션 편집기**를 열고 탭을 선택한 다음 **제거**를 클릭합니다.  
  
#### 리본 메뉴의 탭 위치 변경  
 리본 메뉴의 사용자 지정 탭 순서를 변경할 수 있습니다.  리본 메뉴의 기본 제공 탭 앞이나 뒤에 사용자 지정 탭을 배치할 수도 있습니다.  자세한 내용은 [방법: 리본의 탭 위치 변경](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)을 참조하십시오.  
  
#### 리본 메뉴의 기본 제공 탭 사용자 지정  
 기본 제공 탭은 Microsoft Office 응용 프로그램의 리본 메뉴에 이미 있는 탭입니다.  예를 들어 **데이터** 탭은 Excel의 기본 제공 탭입니다.  
  
 기본 제공 탭에 그룹 및 컨트롤을 추가할 수 있습니다.  기본적으로 사용자 지정 그룹은 기본 제공 탭에 마지막 그룹으로 표시되지만 해당 탭의 기본 제공 그룹 앞이나 뒤로 이동할 수도 있습니다.  
  
 기본 제공 그룹은 제거할 수 없습니다.  
  
 기본 제공 탭을 사용자 지정하는 방법에 대한 자세한 내용은 [방법: 기본 제공 탭 사용자 지정](../vsto/how-to-customize-a-built-in-tab.md)을 참조하십시오.  
  
###  <a name="AddGroupsToTab"></a> 탭에 그룹 추가  
 그룹은 리본 메뉴의 컨트롤을 논리적으로 구성합니다.  그룹을 탭에 추가하고  다른 모든 컨트롤을 그룹에 추가합니다.  
  
###  <a name="AddControlsToGroups"></a> 그룹에 컨트롤 추가  
 그룹에는 하나 이상의 컨트롤을 추가합니다.  다음 표에서는 각 컨트롤에 대해 설명합니다.  
  
|컨트롤|설명|  
|---------|--------|  
|**Box**|그룹의 컨트롤을 구성하는 컨테이너입니다.  상자에는 구분 기호, 그룹 또는 탭을 제외한 모든 컨트롤을 추가할 수 있습니다.  상자는 가로 또는 세로일 수 있습니다.|  
|**Button**|작업을 시작하는 단추입니다.  그룹, 단추 그룹, 드롭다운 목록, 갤러리, 메뉴 또는 분할 단추에 단추를 추가할 수 있습니다.|  
|**ButtonGroup**|하나 이상의 단추, 설정\/해제 단추, 메뉴, 분할 단추 및 갤러리가 들어 있는 그룹입니다.  그룹 또는 메뉴에 단추 그룹을 추가할 수 있습니다.|  
|**CheckBox**|옵션을 설정 또는 해제하기 위해 선택하거나 선택 취소하는 상자입니다.|  
|**ComboBox**|목록 상자가 연결된 입력란입니다.  사용자는 원하는 내용을 입력하거나 선택할 수 있습니다.  이 상자에는 현재 선택 항목이 표시됩니다.  Office 응용 프로그램에 리본 메뉴가 로드되기 전이나 후에 런타임에 항목을 추가 및 제거하려면 <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.Items%2A> 속성을 사용합니다.|  
|**DropDown**|사용자가 선택할 수 있는 항목의 목록입니다.  사용자는 드롭다운 목록에 새 항목을 입력할 수 없습니다.<br /><br /> 목록에 항목을 추가하려면 <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.Items%2A> 속성을 사용합니다.  런타임에 항목을 추가 및 제거할 수 있습니다.<br /><br /> 목록에 단추를 추가하려면 <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.Buttons%2A> 속성을 사용합니다.  그러나 Office 응용 프로그램에 리본 메뉴가 로드된 후에는 런타임에 단추를 추가 및 제거할 수 없습니다.|  
|**EditBox**|사용자가 텍스트를 입력할 수 있는 상자입니다.|  
|**Gallery**|사용자가 선택할 수 있는 비주얼 선택 옵션으로 구성된 배열 또는 표를 표시하는 메뉴입니다.  메뉴의 선택 항목 레이아웃을 제어할 수 있습니다.  갤러리의 항목과 단추가 표시되는 행 및 열 수를 지정하려면 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ColumnCount%2A> 및 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.RowCount%2A> 속성을 사용합니다.|  
|**레이블**|리본 메뉴의 컨트롤을 식별하는 데 사용할 수 있는 텍스트입니다.|  
|**메뉴**|다음 컨트롤을 포함할 수 있는 드롭다운 목록입니다.<br /><br /> -   Button<br />-   Check box<br />-   Gallery<br />-   메뉴<br />-   Split button<br />-   Toggle button<br />-   Separator<br /><br /> 리본 디자이너에서 메뉴에 컨트롤을 추가하려면 메뉴의 아래쪽 화살표를 클릭하여 메뉴 디자인 화면을 표시합니다.  그런 다음 **도구 상자**의 리본 컨트롤을 메뉴로 끌어 옵니다.  컨트롤을 정렬하려면 컨트롤을 원하는 위치로 끌어 옵니다.<br /><br /> Office 응용 프로그램에 리본 메뉴가 로드된 후 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>에 컨트롤을 추가하려면 리본 메뉴가 로드되기 전에 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu.Dynamic%2A> 속성을 **true**로 설정해야 합니다.  이를 수행하는 방법에 대한 자세한 내용은 [리본 개체 모델 개요](../vsto/ribbon-object-model-overview.md)을 참조하십시오.|  
|**Separator**|목록의 항목을 구분하는 데 사용되는 가는 막대입니다.  이 막대는 그룹에 추가될 경우 세로로 표시되고  메뉴에 추가될 경우 가로로 표시됩니다.|  
|**SplitButton**|메뉴가 연결된 단추입니다.  분할 단추에는 다음 컨트롤이 포함될 수 있습니다.<br /><br /> -   Button<br />-   Check box<br />-   Gallery<br />-   메뉴<br />-   Split button<br />-   Toggle button<br />-   Separator<br /><br /> 메뉴와 같이 분할 단추에는 고유한 디자인 화면이 있습니다.  그러나 메뉴와 달리 분할 단추의 항목은 Office 응용 프로그램에 리본 메뉴가 로드되기 전에만 업데이트할 수 있습니다.  분할 단추의 항목을 업데이트하는 방법에 대한 자세한 내용은 [리본 개체 모델 개요](../vsto/ribbon-object-model-overview.md)를 참조하십시오.|  
|**ToggleButton**|눌러져 있거나 눌러져 있지 않은 것으로 표시되는 단추입니다.|  
  
##  <a name="HandleEventsSetProperties"></a> 이벤트 처리 및 속성 설정  
 리본 디자이너를 사용하면 디자인 타임에 **속성** 창에서 컨트롤 속성을 설정할 수 있습니다.  또한 리본 메뉴는 런타임에 리본 컨트롤의 속성을 가져오거나 설정하는 데 사용할 수 있는 강력한 형식의 개체 모델을 노출합니다.  
  
 디자이너에서 컨트롤을 두 번 클릭하여 컨트롤의 기본 이벤트에 대한 이벤트 처리기를 열 수 있습니다.  **속성** 창을 사용하여 다른 모든 컨트롤 이벤트의 이벤트 처리기를 만들 수 있습니다.  
  
 리본 이벤트 및 속성은 <xref:Microsoft.Office.Tools.Ribbon> 네임스페이스에 있습니다.  **리본\(비주얼 디자이너\)** 항목은 프로젝트에 이 어셈블리에 대한 참조를 자동으로 추가하고 리본 코드 파일의 맨 위에 적절한 **using** 또는 **Imports** 문을 삽입합니다.  
  
 런타임에 리본 이벤트를 처리하고 리본 컨트롤의 속성을 설정하는 것에 대한 자세한 내용은 [리본 개체 모델 개요](../vsto/ribbon-object-model-overview.md)를 참조하십시오.  
  
##  <a name="CustomizingMicrosoftOfficeButton"></a> Backstage 보기 사용자 지정  
 리본 디자이너를 사용하여 **파일** 탭을 클릭할 때 열리는 컨트롤을 메뉴에 추가할 수 있습니다.  이 메뉴는 Backstage 보기로 불립니다.  
  
 리본 디자이너를 사용하여 내장 컨트롤의 앞이나 뒤에 컨트롤을 배치할 수 없습니다.  기본 제공 컨트롤은 Backstage 뷰에 이미 나타난 컨트롤입니다.  기본 제공 컨트롤의 앞이나 뒤에 컨트롤을 배치하려면 리본 XML을 사용해야 합니다.  **리본\(XML\)**에 대한 자세한 내용은 [리본 XML](../vsto/ribbon-xml.md)을 참조하십시오.  Backstage 뷰 사용자 지정에 대한 자세한 내용은 [개발자용 Office 2010 Backstage 뷰에 대한 개요](http://go.microsoft.com/fwlink/?LinkId=182189) 및 [개발자용 Office 2010 Backstage 뷰 사용자 지정하기](http://go.microsoft.com/fwlink/?LinkId=182188)를 참조하십시오.  
  
 [!INCLUDE[appliesto_ribbon_2010](../vsto/includes/appliesto-ribbon-2010-md.md)]  
  
 백스테이지 뷰에 컨트롤을 추가하는 방법에 대한 자세한 내용은 [방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)을 참조하십시오.  
  
##  <a name="Accessibility"></a> 리본 디자이너의 내게 필요한 옵션  
 리본 디자이너에서 바로 가기 키를 사용하여 컨트롤을 이동할 수 있습니다.  일부 바로 가기 키는 모든 컨트롤에 적용되고 일부 바로 가기 키는 메뉴가 있는 컨트롤에만 적용됩니다.  
  
 다음 표에서는 모든 컨트롤에 적용되는 바로 가기 키를 보여 줍니다.  
  
|작업|바로 가기 키|  
|--------|-------------|  
|컨트롤을 목록의 이전 컨트롤 앞으로 이동합니다.|Ctrl\+위쪽 화살표<br /><br /> Ctrl\+왼쪽 화살표|  
|컨트롤을 목록의 다음 컨트롤 뒤로 이동합니다.|Ctrl\+아래쪽 화살표<br /><br /> Ctrl\+오른쪽 화살표|  
|한 컨트롤의 선택 항목을 동일한 그룹의 다른 컨트롤로 이동합니다.  드롭다운 패널의 경우 드롭다운 패널의 부모 컨트롤과 컨트롤 간을 이동합니다.|위쪽 화살표<br /><br /> 아래쪽 화살표|  
|모든 컨트롤을 정방향으로 반복합니다.|TAB|  
|모든 컨트롤을 역방향으로 반복합니다.|Shift\+Tab|  
|선택한 컨트롤 또는 컨트롤 집합을 삭제합니다.|Delete|  
|선택한 컨트롤을 복사합니다.|Ctrl\+C|  
|선택한 컨트롤을 잘라냅니다.|Ctrl\+X|  
|클립보드에서 컨트롤을 붙여넣습니다.|Ctrl\+V|  
|**도구 상자**를 선택합니다.|Ctrl\+Alt\+X|  
|부모 구성 요소를 선택합니다.|Esc|  
  
 다음 표에서는 Microsoft Office 메뉴, <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu> 및 <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>에만 적용되는 바로 가기 키를 보여 줍니다.  
  
|작업|바로 가기 키|  
|--------|-------------|  
|드롭다운 패널이 열려 있고 드롭다운 패널에 선택된 컨트롤이 있는 경우 부모 컨트롤을 선택합니다.|왼쪽 화살표|  
|드롭다운 패널이 열려 있고 부모 컨트롤이 선택되어 있는 경우 드롭다운 패널을 닫습니다.|왼쪽 화살표|  
|드롭다운 패널을 엽니다.|오른쪽 화살표|  
|드롭다운 패널이 열려 있는 경우 드롭다운 패널의 첫 번째 컨트롤을 선택합니다.|오른쪽 화살표|  
|드롭다운 패널을 닫습니다.|Esc|  
  
## 참고 항목  
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 XML](../vsto/ribbon-xml.md)   
 [연습: 리본 디자이너를 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)  
  
  