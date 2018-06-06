---
title: 리본 디자이너
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- Designer_Microsoft.VisualStudio.Tools.Office.Ribbon.Design.RibbonDesigner
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, about Ribbon Designer
- controls [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], controls
- customizing the Ribbon, about Ribbon Designer
- Ribbon [Office development in Visual Studio], visual designer
- customizing the Ribbon
- custom Ribbon
- designers [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], customizing
- Ribbon [Office development in Visual Studio], common tasks
- Ribbon Designer [Office development in Visual Studio]
- read-only properties
- Ribbon [Office development in Visual Studio], shortcut keys
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8cb8df33c89ce044572508918ba48edae2a6d75e
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693346"
---
# <a name="ribbon-designer"></a>리본 디자이너
  리본 디자이너는 시각적 디자인 캔버스입니다. 리본 디자이너를 사용 하 여 Microsoft Office 응용 프로그램의 리본에 사용자 지정 탭, 그룹 및 컨트롤을 추가 합니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
 리본 디자이너를 열려면 추가 **리본 (비주얼 디자이너)** 항목을 프로젝트입니다. 그런 다음 다음과 같은 작업에 대 한 디자인 도구를 사용할 수 있습니다.  
  
-   [리본 레이아웃 디자인](#DesigningRibbonLayout)  
  
-   [이벤트를 처리 하 고 컨트롤 속성 설정](#HandleEventsSetProperties)  
  
-   [Backstage 보기에 컨트롤 추가](#CustomizingMicrosoftOfficeButton)  
  
> [!NOTE]  
>  일부 작업이 리본 디자이너를 사용 하 여 수행할 수 없습니다. 이러한 작업을 수행 하는 방법에 대 한 자세한 내용은 참조 [리본 개요](../vsto/ribbon-overview.md)합니다.  
  
 ![비디오에 링크](../vsto/media/playvideo.gif "비디오에 링크") 관련된 동영상 데모를 참조 하십시오. [사용 할까요?: Outlook에서 리본을 사용자 지정 리본 디자이너 작업 방법?](http://go.microsoft.com/fwlink/?LinkID=130312)합니다.  
  
## <a name="add-a-ribbon-visual-designer-item-to-a-project"></a>프로젝트에 리본 (비주얼 디자이너) 항목을 추가 합니다.  
 리본 디자이너를 사용 하려면 새 추가 **리본 (비주얼 디자이너)** 항목을 프로젝트입니다. 자세한 내용은 참조 [하는 방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)합니다.  
  
 추가 하는 경우 새 **리본 (비주얼 디자이너)** 항목, Visual Studio 자동으로 다음 파일이 프로젝트에 추가 합니다.  
  
-   리본 코드 파일. 이 파일에 대해 지정한 이름을 가진는 **리본 (비주얼 디자이너)** 항목에 **새 항목 추가** 대화 상자. 이 파일에 리본 이벤트를 처리 하는 코드를 추가 합니다.  
  
-   리본 디자이너 코드 파일입니다. 이 파일은 리본 디자이너에서 생성 된 코드를 포함 하며 직접 편집할 수 없습니다.  
  
-   리소스 파일입니다. 이 파일의 리본에 있는 각 컨트롤의 속성 값을 포함합니다.  
  
 이미 있는 경우는 **리본 (비주얼 디자이너)** 항목 다른 프로젝트에서 다시 사용할 수 있습니다 것을 현재 프로젝트에 사용 하 여는 **기존 항목 추가** 대화 상자.  
  
##  <a name="DesigningRibbonLayout"></a> 리본 메뉴를 디자인 합니다.  
 세 가지 방법으로 리본 디자이너를 엽니다.  
  
-   **솔루션 탐색기**, 리본 코드 파일을 두 번 클릭 합니다.  
  
-   **솔루션 탐색기**리본 코드 파일을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **뷰 디자이너**합니다.  
  
-   **솔루션 탐색기**리본 코드 파일을 선택한 다음 **디자이너** 에 **보기** 메뉴.  
  
 리본 디자이너에는 기본 탭 및 그룹이 포함 되어 있습니다. 리본 디자이너에서 기본 탭 및 그룹을 제거할 수 있습니다. 기본 그룹을 제거 하려면 마우스 오른쪽 단추로 클릭 **Group1**, 클릭 하 고 **삭제**합니다. 기본 탭을 제거 하려면 디자인 화면의 빈 영역을 마우스 오른쪽 단추로 클릭 하 고 클릭 **리본 탭 제거**합니다.  
  
 또한 리본 디자이너를 사용자 지정 탭, 그룹 및 컨트롤을 추가할 수 있습니다. 이러한 컨트롤을 찾을 수 있습니다는 **도구 상자**에 **Office 리본 컨트롤** 그룹입니다. 세 가지 방법으로 컨트롤을 추가 하는 **Office 리본 컨트롤** 리본 디자이너 그룹:  
  
-   리본 디자이너에서 컨트롤을 적절 한 영역을 끌어옵니다.  
  
-   컨트롤을 클릭 한 다음 리본 디자이너에서 적절 한 영역을 클릭 합니다.  
  
-   디자이너에서 적절 한 영역을 선택 하 고 다음에 있는 컨트롤을 두 번 클릭은 **도구 상자**합니다.  
  
### <a name="ribbon-design-workflow"></a>리본 디자인 워크플로  
 리본 레이아웃을 디자인 하려면 다음 기본 단계를 수행 합니다.  
  
1.  [리본에 사용자 지정 탭 추가](#AddTabToRibbon)합니다.  
  
2.  [탭에 그룹을 추가](#AddGroupsToTab)합니다.  
  
3.  [컨트롤 그룹을 추가할](#AddControlsToGroups)합니다.  
  
 컨트롤 그룹;에 대해서만 삭제할 수 있습니다. 리본 메뉴 또는 탭에 직접 컨트롤을 끌 수 없습니다. 탭이 있습니다.; 경우에 그룹을 삭제할 수 있습니다. 리본 메뉴에 직접 그룹을 끌 수 없습니다.  
  
 올바른 위치로 드래그 하 여 컨트롤을 정렬 합니다. 사용 하 여 컨트롤의 속성을 설정할 수 있습니다는 **속성** 창.  
  
 리본 메뉴에서 다른 탭 간에 컨트롤을 끌 수 없습니다. 컨트롤을 다른 탭으로 이동 하려는 경우 사용 해야는 **잘라내기** 명령을 한 탭에서 컨트롤을 제거 하 고 컨트롤을 다른 탭을 붙여 넣습니다. 컨트롤을 잘라내어 붙여지 않습니다, 이벤트 처리기 작동 하지 않습니다. 이벤트 처리기에 다시 연결할 수 있습니다는 **속성** 창. 자세한 내용은 참조 [속성 창](/visualstudio/ide/reference/properties-window)합니다.  
  
###  <a name="AddTabToRibbon"></a> 리본에 사용자 지정 탭 추가  
 리본에 사용자 지정 탭을 추가 하는 방법은 세 가지가 있습니다.  
  
-   탭 추가 **도구 상자**합니다.  
  
-   리본 디자이너를 마우스 오른쪽 단추로 누른 **리본 탭 추가**합니다.  
  
-   열기는 **탭 컬렉션 편집기**, 클릭 하 고 **추가**합니다.  
  
     열려는 **탭 컬렉션 편집기**에 **속성** 창에서는 **탭** 속성을 다음 줄임표 단추를 클릭 하 고 ![ASP.NET 모바일 디자이너 타원](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표")합니다.  
  
 탭에 추가한 후에 컨트롤을 포함할 그룹을 추가할 수 있습니다.  
  
#### <a name="remove-custom-tabs-from-the-ribbon"></a>리본 메뉴에서 사용자 지정 탭을 제거 합니다.  
 리본 메뉴에서 사용자 지정 탭을 제거 하는 방법은 세 가지가 있습니다.  
  
-   디자이너를 마우스 오른쪽 단추로 누른 **리본 탭 제거**합니다.  
  
-   에 **명령을** 의 창은 **속성** 창 클릭 **리본 탭 제거**합니다.  
  
-   열기는 **탭 컬렉션 편집기**탭을 선택한 다음 **제거**합니다.  
  
#### <a name="change-the-position-of-a-tab-on-the-ribbon"></a>리본의 탭 위치 변경  
 리본 메뉴 사용자 지정 탭의 순서를 변경할 수 있습니다. 리본의 기본 제공 탭 앞 이나 뒤에 사용자 지정 탭을 배치할 수 있습니다. 자세한 내용은 참조 [하는 방법: 리본의 탭 위치 변경](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)합니다.  
  
#### <a name="customize-built-in-tabs-on-the-ribbon"></a>리본의 기본 제공 탭 사용자 지정  
 기본 제공 탭은 Microsoft Office 응용 프로그램의 리본 메뉴에 이미 있는 탭입니다. 예를 들어는 **데이터** 탭은 Excel의 기본 제공 탭입니다.  
  
 기본 제공 탭에 그룹과 컨트롤을 추가할 수 있습니다. 기본적으로 이동할 수 있습니다 모든 기본 제공 그룹 이전 또는 이후에 탭에는 있지만 사용자 지정 그룹은 기본 제공 탭에 있는 마지막 그룹으로 나타납니다.  
  
 기본 제공 그룹을 제거할 수 없습니다.  
  
 기본 제공 탭 사용자 지정 하는 방법에 대 한 세부 정보를 참조 하십시오. [하는 방법: 기본 제공 탭 사용자 지정](../vsto/how-to-customize-a-built-in-tab.md)합니다.  
  
###  <a name="AddGroupsToTab"></a> 탭에 그룹 추가  
 그룹의 리본 메뉴의 컨트롤을 논리적으로 구성합니다. 탭에 그룹을 추가 합니다. 그룹에 다른 모든 컨트롤을 추가 합니다.  
  
###  <a name="AddControlsToGroups"></a> 그룹에 컨트롤 추가  
 그룹에 하나 이상의 컨트롤을 추가 합니다. 다음 표에서 각 컨트롤에 설명 합니다.  
  
|Control|설명|  
|-------------|-----------------|  
|**상자**|그룹의 컨트롤을 구성 하는 컨테이너입니다. 구분 기호, 그룹 또는 탭을 제외 하 고 상자에 컨트롤을 추가할 수 있습니다. 수평 또는 수직 일 수 있습니다.|  
|**Button**|액션을 시작 하는 단추입니다. 그룹, 단추 그룹, 드롭 다운 목록, 갤러리, 메뉴 또는 분할 단추는 단추를 추가할 수 있습니다.|  
|**ButtonGroup**|하나 이상의 단추, 토글 단추, 메뉴, 분할 단추 및 갤러리를 포함 하는 그룹입니다. 그룹 또는 메뉴 단추 그룹을 추가할 수 있습니다.|  
|**CheckBox**|상자에 켜기 / 끄기 옵션 설정을 변경 해도입니다.|  
|**ComboBox**|목록 상자가 추가 된 입력란입니다. 사용자가 입력 하거나 해당 옵션을 선택 합니다. 상자는 현재 선택 영역을 표시합니다. 사용 하 여 <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.Items%2A> 속성을 추가 하 고 리본이 Office 응용 프로그램에 로드 된 후 전이나 런타임에 항목을 제거 합니다.|  
|**드롭다운**|사용자가 선택할 수 있는 항목의 목록. 사용자는 드롭 다운 목록에서 새 항목을 입력할 수 없습니다.<br /><br /> 사용 하 여는 <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.Items%2A> 속성 목록에 항목을 추가 합니다. 추가 하 고 런타임 시 항목을 제거할 수 있습니다.<br /><br /> 사용 하 여는 <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.Buttons%2A> 속성 목록에 단추를 추가 합니다. 그러나 추가할 수 있으며 런타임에 리본이 Office 응용 프로그램에 로드 된 후 제거 단추 수 없습니다.|  
|**편집 상자**|사용자가 텍스트를 입력할 수 있는 상자입니다.|  
|**갤러리**|배열 또는 사용자가 선택할 수 있는 시각적 선택 항목의 모눈을 표시 하는 메뉴 메뉴에서 선택한 항목의 레이아웃을 제어할 수 있습니다. 사용 하 여는 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ColumnCount%2A> 및 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.RowCount%2A> 행과 항목을 표시 하는 열 개수 및 갤러리의 단추를 지정 하는 속성입니다.|  
|**레이블**|리본 메뉴에 컨트롤을 식별 하는 데 사용할 수 있는 텍스트입니다.|  
|**메뉴**|다음 컨트롤 중 하나를 포함할 수 있는 드롭 다운 목록:<br /><br /> 단추<br />-확인란<br />-갤러리<br />메뉴<br />분할 단추<br />-토글 단추<br />구분 기호<br /><br /> 리본 디자이너에서 메뉴에 컨트롤을 추가 하려면 메뉴 디자인 화면을 표시 하려면 메뉴에서 아래쪽 화살표를 클릭 합니다. 리본 컨트롤을 끌어 놓을 수 있습니다는 **도구 상자** 메뉴로 합니다. 컨트롤을 정렬 하려면를 원하는 위치로 끌어 옵니다.<br /><br /> 컨트롤을 추가 하려면는 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu> 리본이 Office 응용 프로그램에 로드 된 후 설정 해야 합니다는 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu.Dynamic%2A> 속성을 **true** 리본 메뉴를 로드 하기 전에. 이 작업을 수행 하는 방법에 대 한 정보를 참조 하십시오. [리본 개체 모델 개요](../vsto/ribbon-object-model-overview.md)합니다.|  
|**구분 기호**|목록에 항목을 구분 하는 데 사용 되는 씬 모음입니다. 그룹에 추가 하는 경우 막대는 세로입니다. 메뉴에 추가 하면 가로로 표시 됩니다.|  
|**분할 단추**|연결 된 메뉴 단추입니다. 분할 단추는 다음 컨트롤 중 하나를 포함할 수 있습니다.<br /><br /> 단추<br />-확인란<br />-갤러리<br />메뉴<br />분할 단추<br />-토글 단추<br />구분 기호<br /><br /> 메뉴에서와 마찬가지로 분할 단추는 디자인 화면을 있습니다. 그러나 메뉴에서 달리 업데이트할 수 있습니다만 분할 단추에 있는 항목 리본이 Office 응용 프로그램에 로드 되기 전에. 분할 단추에 있는 항목을 업데이트 하는 방법에 대 한 정보를 참조 하십시오. [리본 개체 모델 개요](../vsto/ribbon-object-model-overview.md)합니다.|  
|**토글 단추**|표시 되는 단추 상태나 누르지 않은 합니다.|  
  
##  <a name="HandleEventsSetProperties"></a> 이벤트를 처리 하는 속성 설정  
 리본 디자이너를 사용 하면 사용 하 여 디자인 타임에 컨트롤 속성을 설정 하는 **속성** 창. 또한 리본 가져오고 런타임에 리본 컨트롤의 속성을 설정 하는 데 사용할 수 있는 강력한 형식의 개체 모델을 노출 합니다.  
  
 컨트롤의 기본 이벤트에 대 한 이벤트 처리기를 열려는 디자이너에 있는 컨트롤을 두 번 클릭 수 있습니다. 사용 하 여 다른 모든 컨트롤 이벤트에 대 한 이벤트 처리기를 만들 수는 **속성** 창.  
  
 리본 이벤트 및 속성에 있는 경우는 <xref:Microsoft.Office.Tools.Ribbon> 네임 스페이스입니다. **리본 (비주얼 디자이너)** 항목 자동으로이 어셈블리에 대 한 참조를 프로젝트에 추가 하 고 적절 한 삽입 **를 사용 하 여** 또는 **Imports** 문에 리본 코드 파일.  
  
 리본 이벤트를 처리 하 고 런타임에 리본 컨트롤의 속성을 설정 하는 방법에 대 한 정보를 참조 하십시오. [리본 개체 모델 개요](../vsto/ribbon-object-model-overview.md)합니다.  
  
##  <a name="CustomizingMicrosoftOfficeButton"></a> Backstage 보기 사용자 지정  
 리본 디자이너를 사용 하 여 컨트롤을 클릭할 때 열리는 메뉴에 추가 하 고 **파일** 탭 합니다. 이 메뉴 Backstage 보기를 라고 합니다.  
  
 리본 디자이너를 사용 하 여 기본 제공 컨트롤 전후 컨트롤을 배치할 수 없습니다. 기본 제공 컨트롤에는 이미 Backstage 보기에 표시 되는 컨트롤이입니다. 기본 제공 컨트롤 전후 컨트롤을 배치 하려는 경우 리본 XML을 사용 해야 합니다. 에 대 한 자세한 내용은 **리본 (XML)**, 참조 [리본 XML](../vsto/ribbon-xml.md)합니다. Backstage 보기 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 [개발자를 위한 Office 2010 Backstage 보기 소개](http://go.microsoft.com/fwlink/?LinkId=182189) 및 [개발자를 위한 Office 2010 Backstage 보기 사용자 지정](http://go.microsoft.com/fwlink/?LinkId=182188)합니다.  
  
 [!INCLUDE[appliesto_ribbon_2010](../vsto/includes/appliesto-ribbon-2010-md.md)]  
  
 Backstage 보기에 컨트롤을 추가 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)합니다.  
  
##  <a name="Accessibility"></a> 리본 디자이너의 내게 필요한 옵션  
 리본 디자이너에서 컨트롤을 이동 하려면 바로 가기 키를 사용할 수 있습니다. 일부 바로 가기 키는 모든 컨트롤에 적용 하 고 메뉴를 포함 하는 컨트롤에만 적용 합니다.  
  
 다음 표에서 모든 컨트롤에 적용 되는 바로 가기 키 표시 됩니다.  
  
|작업|바로 가기 키|  
|------------|-----------------------|  
|목록에서 이전 컨트롤로 전에 컨트롤을 이동 합니다.|**Ctrl**+**를**<br /><br /> **Ctrl**+**왼쪽**|  
|컨트롤 목록에서 다음 컨트롤 뒤로 이동 합니다.|**Ctrl**+**아래로**<br /><br /> **Ctrl**+**오른쪽**|  
|같은 그룹에서 다른 한 컨트롤에서 선택 영역을 이동 합니다. 드롭다운 패널에 대 한 부모 컨트롤 드롭다운 패널의 컨트롤이 간을 이동 합니다.|**위쪽**<br /><br /> **아래로**|  
|모든 컨트롤을 정방향으로 반복 합니다.|**Tab**|  
|모든 컨트롤 역방향으로 반복 합니다.|**Shift**+**Tab**|  
|선택한 컨트롤 또는 컨트롤 집합을 삭제 합니다.|**삭제**|  
|선택한 컨트롤을 복사 합니다.|**Ctrl**+**C**|  
|선택한 컨트롤을 잘라냅니다.|**Ctrl**+**X**|  
|컨트롤을에서 클립보드에 붙여 넣습니다.|**Ctrl**+**V**|  
|선택 된 **도구 상자**합니다.|**Ctrl**+**Alt**+**X**|  
|부모 구성 요소를 선택 합니다.|**Esc**|  
  
 Microsoft Office 메뉴에만 적용 되는 바로 가기 키 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>, 및 <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton> 다음 표에 나와 있습니다.  
  
|작업|바로 가기 키|  
|------------|-----------------------|  
|드롭다운 패널 열려 있고 드롭다운 패널에서 선택한 컨트롤이 없는 경우 부모 컨트롤을 선택 합니다.|**왼쪽**|  
|드롭다운 패널 열려 있고 부모 컨트롤을 선택할 경우 드롭다운 패널을 닫습니다.|**왼쪽**|  
|드롭다운 패널을 엽니다.|**오른쪽**|  
|드롭다운 패널 열려 있으면 드롭다운 패널에서 첫 번째 컨트롤을 선택 합니다.|**오른쪽**|  
|드롭다운 패널을 닫습니다.|**Esc**|  
  
## <a name="see-also"></a>참고자료  
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 XML](../vsto/ribbon-xml.md)   
 [연습: 리본 디자이너를 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)  
  
  