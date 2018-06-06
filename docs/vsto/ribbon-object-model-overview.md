---
title: 리본 개체 모델 개요
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Ribbon [Office development in Visual Studio], object model
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2be8f0ecdb4f2d7a8ea379474c4b5ec0062d2b57
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34692963"
---
# <a name="ribbon-object-model-overview"></a>리본 개체 모델 개요
  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 가져오고 런타임에 리본 컨트롤의 속성을 설정 하는 데 사용할 수 있는 강력한 형식의 개체 모델을 노출 합니다. 예를 들어 하면 동적으로 메뉴 컨트롤을 채우는 또는 표시 하거나 숨길 수 컨트롤 컨텍스트. 리본이 Office 응용 프로그램에서 로드 되기 전에만 하지만 리본, 탭, 그룹 및 컨트롤도 추가할 수 있습니다. 자세한 내용은 참조 [읽기 전용이 되는 속성을 설정할](#SettingReadOnlyProperties)합니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
 주로 구성이 리본 개체 모델에서 [리본 클래스](#RibbonClass), [이벤트 리본](#RibbonEvents), 및 [리본 컨트롤 클래스](#RibbonControlClasses)합니다.  
  
##  <a name="RibbonClass"></a> 리본 클래스  
 추가 하는 경우 새 **리본 (비주얼 디자이너)** 항목을 프로젝트에 추가 하는 Visual Studio는 **리본** 프로젝트에 클래스입니다. **리본** 클래스에서 상속 된 <xref:Microsoft.Office.Tools.Ribbon.RibbonBase> 클래스입니다.  
  
 이 클래스는 리본 코드 파일 및 리본 디자이너 코드 파일 분할 된 partial 클래스로 표시 됩니다.  
  
##  <a name="RibbonEvents"></a> 리본 이벤트  
 **리본** 클래스는 다음 세 가지 이벤트를 포함 합니다.  
  
|이벤트(event)|설명|  
|-----------|-----------------|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.Load>|Office 응용 프로그램 리본 메뉴 사용자 지정을 로드할 때 발생 합니다. <xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.Load> 리본 코드 파일에 이벤트 처리기가 자동으로 추가 합니다. 이 이벤트 처리기를 사용 하 여 리본 메뉴를 로드 하는 경우 사용자 지정 코드를 실행 합니다.|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.LoadImage>|리본을 로드할 때의 리본 메뉴 사용자 지정 이미지를 캐시할 수 합니다. 이 이벤트 처리기에서 리본 메뉴 이미지를 캐시 하는 코드를 작성 하는 경우 성능이 약간 향상을 얻을 수 있습니다. 자세한 내용은 <xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.LoadImage>을 참조하세요.|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.Close>|리본 인스턴스가 닫힐 때 발생 합니다.|  
  
##  <a name="RibbonControlClasses"></a> 리본 컨트롤  
 <xref:Microsoft.Office.Tools.Ribbon> 네임 스페이스에서 볼 수 있는 각 컨트롤에 대 한 형식이 포함 되어는 **Office 리본 컨트롤** 그룹는 **도구 상자**합니다.  
  
 다음 표에서 각 형식을 보여 줍니다. `Ribbon` 제어 합니다. 각 컨트롤에 대 한 참조 [리본 개요](../vsto/ribbon-overview.md)합니다.  
  
|컨트롤 이름|클래스 이름|  
|------------------|----------------|  
|**상자**|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox>|  
|**Button**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton>|  
|**ButtonGroup**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButtonGroup>|  
|**CheckBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox>|  
|**ComboBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>|  
|**드롭다운**|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>|  
|**편집 상자**|<xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|  
|**갤러리**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**그룹**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|  
|**레이블**|<xref:Microsoft.Office.Tools.Ribbon.RibbonLabel>|  
|**메뉴**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|  
|**구분 기호**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|  
|**분할 단추**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|  
|**Tab**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|  
|**토글 단추**|<xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|  
  
 <xref:Microsoft.Office.Tools.Ribbon> 네임 스페이스에서 컨트롤 클래스의 이름으로는 이름 충돌을 방지 하기 위해 이러한 형식에 대 한 "리본" 접두사를 사용 하 여 <xref:System.Windows.Forms> 네임 스페이스입니다.  
  
 리본 디자이너에 컨트롤을 추가할 때 리본 디자이너 리본 디자이너 코드 파일의 필드와 해당 컨트롤에 대 한 클래스를 선언 합니다.  
  
### <a name="common-tasks-using-the-properties-of-ribbon-controls"></a>리본 컨트롤의 속성을 사용 하 여 일반 작업  
 각 `Ribbon` 컨트롤에 컨트롤에 레이블을 할당 또는 컨트롤 숨기기 및 표시 등의 다양 한 작업을 수행 하는 데 사용할 수 있는 속성이 포함 됩니다.  
  
 경우에 따라 속성 리본 로드 하거나 동적 메뉴에 컨트롤을 추가한 후 읽기 전용으로 설정 됩니다. 자세한 내용은 참조 [읽기 전용이 되는 속성을 설정할](#SettingReadOnlyProperties)합니다.  
  
 다음 표에서 몇 가지를 사용 하 여 수행할 수 있는 작업에 설명 `Ribbon` 속성을 제어 합니다.  
  
|작업|방법|  
|--------------------|--------------|  
|컨트롤을 표시 하거나 숨깁니다.|Visible 속성을 사용 합니다.|  
|컨트롤을 사용 하지 않도록 설정 하거나 사용 합니다.|Enabled 속성을 사용 합니다.|  
|컨트롤의 크기를 설정 합니다.|ControlSize 속성을 사용 합니다.|  
|컨트롤에 표시 되는 이미지를 가져옵니다.|이미지 속성을 사용 합니다.|  
|컨트롤의 레이블을 변경 합니다.|Label 속성을 사용 합니다.|  
|컨트롤에 사용자 정의 데이터를 추가 합니다.|Tag 속성을 사용 합니다.|  
|항목을 가져올는 <xref:Microsoft.Office.Tools.Ribbon.RibbonBox>, <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>, <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>, 또는<br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton> 컨트롤입니다.|Items 속성을 사용 합니다.|  
|에 항목 추가 <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>, <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>, 또는 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> 제어 합니다.|Items 속성을 사용 합니다.|  
|컨트롤을 추가 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>합니다.|Items 속성을 사용 합니다.<br /><br /> 컨트롤을 추가 하려면는 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu> 리본이 Office 응용 프로그램에 로드 된 후 설정 해야 합니다는 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu.Dynamic%2A> 속성을 **true** 리본이 Office 응용 프로그램에 로드 되기 전에 합니다. 자세한 내용은 참조 [읽기 전용이 되는 속성을 설정할](#SettingReadOnlyProperties)합니다.|  
|선택된 항목 가져오기는 <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>,<br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>또는 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>합니다.|SelectedItem 속성을 사용 합니다. 에 대 한는 <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>를 사용 하 여는 <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.Text%2A> 속성입니다.|  
|그룹을 가져옵니다는 <xref:Microsoft.Office.Tools.Ribbon.RibbonTab>합니다.|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab.Groups%2A> 속성을 사용합니다.|  
|최대 5 개의 행과 열에 표시 되는 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>합니다.|사용 하 여 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.RowCount%2A> 및 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ColumnCount%2A> 속성입니다.|  
  
##  <a name="SettingReadOnlyProperties"></a> 읽기 전용으로 설정 하는 속성 설정  
 리본을 로드 하기 전에만 일부 속성을 설정할 수 있습니다. 이러한 속성을 설정 하려면 다음 세 위치 가지가 있습니다.  
  
-   Visual Studio에서 **속성** 창.  
  
-   생성자에는 **리본** 클래스입니다.  
  
-   에 `CreateRibbonExtensibilityObject` 의 메서드는 `ThisAddin`, `ThisWorkbook`, 또는 `ThisDocument` 프로젝트의 클래스입니다.  
  
 동적 메뉴에는 몇 가지 예외가 제공합니다. 새 컨트롤을 만들 지정, 해당 속성을 설정 및 다음 메뉴가 포함 된 리본이 로드 된 후에 런타임에 동적 메뉴에 추가 합니다.  
  
 언제 든 지 동적 메뉴에 추가 하는 컨트롤의 속성을 설정할 수 있습니다.  
  
 자세한 내용은 참조 [읽기 전용으로 설정 되는 속성](#ReadOnlyProperties)합니다.  
  
### <a name="set-properties-in-the-constructor-of-the-ribbon"></a>리본 메뉴의 생성자에서 속성을 설정 합니다.  
 속성을 설정할 수는 `Ribbon` 컨트롤의 생성자에는 **리본** 클래스입니다. 이 코드에 대 한 호출 뒤에 나타나야 합니다는 `InitializeComponent` 메서드. 다음 예제에서는 현재 시간이 17시 이면 새 단추를 그룹에 추가 태평양 표준시 (UTC-8) 이상.  
  
 다음 코드를 추가 합니다.  
  
 [!code-csharp[Trin_Ribbon_ObjectModel#1](../vsto/codesnippet/CSharp/trin_Ribbon_objectmodel_dotnet4/Ribbon1.Designer.cs#1)]
 [!code-vb[Trin_Ribbon_ObjectModel#1](../vsto/codesnippet/VisualBasic/trin_Ribbon_objectmodel_dotnet4/Ribbon1.Designer.vb#1)]  
  
 Visual C# 프로젝트에서 Visual Studio 2008에서 업그레이드 하는 생성자는 리본 코드 파일에 나타납니다.  
  
 Visual Basic 프로젝트에서 또는 Visual C# 프로젝트에서 만든 [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)], 생성자 리본 디자이너 코드 파일에 나타납니다. 이 파일의 이름은 *YourRibbonItem*합니다. Designer.cs 또는 *YourRibbonItem*합니다. Designer.vb 합니다. Visual Basic 프로젝트에서이 파일을 보려면 먼저 눌러야는 **모든 파일 표시** 솔루션 탐색기에서 단추입니다.  
  
### <a name="set-properties-in-the-createribbonextensibilityobject-method"></a>프로젝트 메서드에서 속성 설정  
 속성을 설정할 수는 `Ribbon` 재정의 하는 경우 제어는 `CreateRibbonExtensibilityObject` 에서 메서드는 `ThisAddin`, `ThisWorkbook`, 또는 `ThisDocument` 프로젝트의 클래스입니다. 에 대 한 자세한 내용은 `CreateRibbonExtensibilityObject` 메서드를 참조 [리본 개요](../vsto/ribbon-overview.md)합니다.  
  
 리본 속성을 설정 하는 다음 예제는 `CreateRibbonExtensibilityObject` 의 메서드는 `ThisWorkbook` 는 Excel 통합 문서 프로젝트의 클래스.  
  
 다음 코드를 추가 합니다.  
  
 [!code-vb[Trin_Ribbon_ObjectModel#2](../vsto/codesnippet/VisualBasic/trin_Ribbon_objectmodel_dotnet4/ThisWorkbook.vb#2)]
 [!code-csharp[Trin_Ribbon_ObjectModel#2](../vsto/codesnippet/CSharp/trin_Ribbon_objectmodel_dotnet4/ThisWorkbook.cs#2)]  
  
###  <a name="ReadOnlyProperties"></a> 읽기 전용으로 설정 되는 속성  
 다음 표에서 리본을 로드 하기 전에만 설정할 수 있는 속성을 보여 줍니다.  
  
> [!NOTE]  
>  언제 든 지 동적 메뉴의 컨트롤의 속성을 설정할 수 있습니다. 이 테이블은 경우에 적용 되지 않습니다.  
  
|속성|리본 컨트롤 클래스|  
|--------------|--------------------------|  
|**BoxStyle**|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox>|  
|**ButtonType**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|  
|**열 개수**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**controlId**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|  
|**DialogLauncher**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|  
|**동적**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|  
|**Global**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**그룹**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|  
|**ImageName**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDialogLauncher><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|  
|**ItemSize**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|  
|**MaxLength**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|  
|**이름**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComponent>|  
|**위치**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGroup><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonTab><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|  
|**RibbonType**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**행 개수**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**ShowItemImage**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**ShowItemLabel**|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**ShowItemSelection**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**SizeString**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|  
|**StartFromScratch**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**탭**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**제목**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|  
  
### <a name="set-properties-for-ribbons-that-appear-in-outlook-inspectors"></a>Outlook 검사기에 나타나는 리본 메뉴에 대 한 속성을 설정 합니다.  
 리본 메뉴의 새 인스턴스를 사용자가 리본이 표시 되는 검사기를 열 때마다 만들어집니다. 그러나 리본 메뉴의 첫 번째 인스턴스가 만들어지기 전에만 위의 표에 나열 된 속성을 설정할 수 있습니다. 첫 번째 후 인스턴스가 만들어지면 이러한 속성은 읽기 전용이 첫 번째 인스턴스는 Outlook에서 리본 메뉴를 로드 하는 XML 파일을 정의 하기 때문에 합니다.  
  
 리본 메뉴의 다른 인스턴스를 만들 때 이러한 속성 중 하나라도 다른 값으로 설정 하는 조건부 논리를 사용 하도록 설정한 경우이 코드는 효과가 없습니다.  
  
> [!NOTE]  
>  확인는 **이름** Outlook 리본 메뉴에 추가 하는 각 컨트롤에 대 한 속성이 설정 되어 있습니다. 런타임 시 Outlook 리본 메뉴에 컨트롤을 추가 하는 경우 코드에서이 속성을 설정 해야 합니다. 디자인 타임에 Outlook 리본 메뉴에 컨트롤을 추가 하면 Name 속성은 자동으로 설정 됩니다.  
  
## <a name="ribbon-control-events"></a>리본 컨트롤 이벤트  
 각 컨트롤 클래스는 하나 이상의 이벤트를 포함합니다. 다음 표에서 이러한 이벤트에 설명 합니다.  
  
|이벤트(event)|설명|  
|-----------|-----------------|  
|클릭|컨트롤을 클릭할 때 발생 합니다.|  
|TextChanged|편집 상자 또는 콤보 상자 텍스트가 변경 될 때 발생 합니다.|  
|ItemsLoading|Items 컬렉션 컨트롤의 Office가 요청 될 때 발생 합니다. 코드는 컨트롤의 속성을 변경 하거나 호출할 때까지 office Items 컬렉션을 캐시는 <xref:Microsoft.Office.Core.IRibbonUI.InvalidateControl%2A> 메서드.|  
|클릭|단추에 경우에 발생 한 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> 또는 <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> 를 클릭 합니다.|  
|SelectionChanged|발생 경우에서 선택은 <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> 또는 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> 변경 합니다.|  
|DialogLauncherClick|그룹의 오른쪽 아래 모서리에 대화 상자 표시 아이콘을 클릭할 때 발생 합니다.|  
  
 이러한 이벤트에 대 한 이벤트 처리기는 다음 두 매개 변수를 포함 합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|*보낸 사람*|<xref:System.Object> 이벤트를 발생 하는 컨트롤을 나타내는입니다.|  
|*e*|A <xref:Microsoft.Office.Tools.Ribbon.RibbonControlEventArgs> 를 포함 하는 <xref:Microsoft.Office.Core.IRibbonControl>합니다. 제공 하는 리본 개체 모델에서 사용할 수 없는 모든 속성에 액세스 하려면이 컨트롤을 사용 하 여는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]합니다.|  
  
## <a name="see-also"></a>참고자료  
 [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)   
 [리본 개요](../vsto/ribbon-overview.md)   
 [방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [연습: 리본 디자이너를 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [연습: 런타임에 리본 메뉴의 컨트롤 업데이트](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)   
 [Outlook에 대 한 리본을 사용자 지정](../vsto/customizing-a-ribbon-for-outlook.md)   
 [방법: 기본 제공 탭 사용자 지정](../vsto/how-to-customize-a-built-in-tab.md)   
 [방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)   
 [방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [방법: 사용자 인터페이스 오류 표시 추가 기능](../vsto/how-to-show-add-in-user-interface-errors.md)  
 