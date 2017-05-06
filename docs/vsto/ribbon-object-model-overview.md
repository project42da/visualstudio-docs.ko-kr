---
title: "리본 개체 모델 개요"
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
  - "리본[Visual Studio에서 Office 개발], 개체 모델"
ms.assetid: cae24f66-e980-41ee-a915-d4c8e03efbc1
caps.latest.revision: 75
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 74
---
# 리본 개체 모델 개요
  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 를 가져오고 런타임에 리본 컨트롤의 속성을 설정 하는 데 사용할 수 있는 강력한 형식의 개체 모델을 노출 합니다.  예를 들어 메뉴 컨트롤을 동적으로 채우거나, 컨트롤을 상황에 따라 표시하고 숨길 수 있습니다.  Office 응용 프로그램에 리본 메뉴가 로드 되기 전에만 있지만 리본, 탭, 그룹 및 컨트롤 또한 추가할 수 있습니다.  자세한 내용은 [읽기 전용이 되는 속성 설정](#SettingReadOnlyProperties)을 참조하십시오.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
 이 리본 개체 모델은 주로 [리본 클래스](#RibbonClass), [리본 이벤트](#RibbonEvents) 및 [리본 컨트롤 클래스](#RibbonControlClasses)로 구성됩니다.  
  
##  <a name="RibbonClass"></a> 리본 클래스  
 추가 새  **리본 \(비주얼 디자이너\)** 추가 하는 Visual Studio 프로젝트에 항목을 **Ribbon** 클래스를 프로젝트에.  **Ribbon** 클래스는 <xref:Microsoft.Office.Tools.Ribbon.RibbonBase> 클래스에서 상속합니다.  
  
 이 클래스는 리본 코드 파일과 리본 디자이너 코드 파일로 나뉘는 partial 클래스로 나타납니다.  
  
##  <a name="RibbonEvents"></a> 리본 이벤트  
 **Ribbon** 클래스는 다음과 같은 세 가지 이벤트를 포함 합니다.  
  
|Event|설명|  
|-----------|--------|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.Load>|Office 응용 프로그램의 리본 사용자 지정이 로드 될 때 발생 합니다.  <xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.Load> 이벤트 처리기는 리본 코드 파일에 자동으로 추가 됩니다.  이 이벤트 처리기를 사용 하 여 리본을 로드할 때 사용자 지정 코드를 실행 하려면.|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.LoadImage>|리본을 로드할 때 리본 사용자 지정의 이미지를 캐시할 수 있습니다.  이 이벤트 처리기에서 리본 이미지를 캐시 하는 코드를 작성 하는 경우 약간의 성능 향상을 얻을 수 있습니다.  자세한 내용은 <xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.LoadImage>을 참조하십시오.|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.Close>|리본 인스턴스가 닫힐 때 발생 합니다.|  
  
##  <a name="RibbonControlClasses"></a> 리본 컨트롤  
 <xref:Microsoft.Office.Tools.Ribbon> 네임스페이스에는 **도구 상자**의 **Office 리본 컨트롤** 그룹에 표시되는 각 컨트롤에 대한 형식이 포함되어 있습니다.  
  
 다음 표에서 형식 각각에 대 한 `Ribbon` 제어 합니다.  각 컨트롤에 대한 설명은 [리본 개요](../vsto/ribbon-overview.md)을 참조하십시오.  
  
|컨트롤 이름|클래스 이름|  
|------------|------------|  
|**Box**|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox>|  
|**Button**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton>|  
|**ButtonGroup**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButtonGroup>|  
|**CheckBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox>|  
|**ComboBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>|  
|**DropDown**|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>|  
|**EditBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|  
|**Gallery**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**그룹화**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|  
|**레이블**|<xref:Microsoft.Office.Tools.Ribbon.RibbonLabel>|  
|**메뉴**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|  
|**Separator**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|  
|**SplitButton**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|  
|**Tab**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|  
|**ToggleButton**|<xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|  
  
 <xref:Microsoft.Office.Tools.Ribbon> 네임스페이스에서는 이러한 형식에 대해 "Ribbon" 접두사를 사용하여 <xref:System.Windows.Forms> 네임스페이스에 있는 컨트롤 클래스와의 이름 충돌을 방지합니다.  
  
 리본 디자이너에 컨트롤을 추가하면 리본 디자이너에서 해당 컨트롤에 대한 클래스를 리본 디자이너 코드 파일의 필드로 선언합니다.  
  
### 리본 컨트롤의 속성을 사용한 일반적인 작업  
 각 `Ribbon` 컨트롤에는 컨트롤에 레이블을 할당 하거나 컨트롤 숨기기 및 표시와 같은 다양 한 작업을 수행 하는 데 사용할 수 있는 속성이 포함 됩니다.  
  
 경우에 따라서는 속성 리본 메뉴를 로드 한 후 또는 동적 메뉴에 컨트롤이 추가 된 후 읽기 전용으로 설정 됩니다.  자세한 내용은 [읽기 전용이 되는 속성 설정](#SettingReadOnlyProperties)을 참조하십시오.  
  
 다음 표에서 몇 가지를 사용 하 여 수행할 수 있는 작업 `Ribbon` 속성을 제어 합니다.  
  
|작업|작업 방법|  
|--------|-----------|  
|컨트롤을 숨기거나 표시합니다.|Visible 속성을 사용합니다.|  
|컨트롤을 활성화하거나 비활성화합니다.|Enabled 속성을 사용합니다.|  
|컨트롤 크기를 설정합니다.|ControlSize 속성을 사용합니다.|  
|컨트롤에 나타나는 이미지를 가져옵니다.|Image 속성을 사용합니다.|  
|컨트롤의 레이블을 변경합니다.|Label 속성을 사용합니다.|  
|컨트롤에 사용자 정의 데이터를 추가합니다.|Tag 속성을 사용합니다.|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox>, <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>, <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> 또는<br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton> 컨트롤의 항목을 가져옵니다.|Items 속성을 사용합니다.|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>, <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> 또는 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> 컨트롤에 항목을 추가합니다.|Items 속성을 사용합니다.|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>에 컨트롤을 추가합니다.|Items 속성을 사용합니다.<br /><br /> 컨트롤을 추가 하는 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu> 설정 해야 Office 응용 프로그램에 리본 메뉴가 로드 된 후의 <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu.Dynamic%2A> 속성을 **true** Office 응용 프로그램에 리본 메뉴가 로드 되기 전에.  자세한 내용은 [읽기 전용이 되는 속성 설정](#SettingReadOnlyProperties)을 참조하십시오.|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>,<br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> 또는 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>의 선택된 항목을 가져옵니다.|SelectedItem 속성을 사용합니다.  <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>의 경우 <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.Text%2A> 속성을 사용합니다.|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>의 그룹을 가져옵니다.|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab.Groups%2A> 속성을 사용합니다.|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>에 나타나는 행 및 열의 수를 지정합니다.|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.RowCount%2A> 및 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ColumnCount%2A> 속성을 사용합니다.|  
  
##  <a name="SettingReadOnlyProperties"></a> 읽기 전용이 되는 속성 설정  
 일부 속성은 리본 메뉴가 로드 되기 전에만 설정할 수 있습니다.  이러한 속성은 다음 세 위치에서 설정할 수 있습니다.  
  
-   Visual Studio **속성** 창  
  
-   생성자에서에서 **Ribbon** 클래스입니다.  
  
-   프로젝트에 사용된 `ThisAddin`, `ThisWorkbook` 또는 `ThisDocument` 클래스의 CreateRibbonExtensibilityObject 메서드  
  
 동적 메뉴는 몇 가지 예외를 제공합니다.  새 컨트롤을 만들 해당 속성을 설정 및 다음 런타임에 리본 메뉴가 로드 된 후에 동적 메뉴에 추가할 수 있습니다.  
  
 동적 메뉴에 추가하는 컨트롤의 속성은 아무 때나 설정할 수 있습니다.  
  
 자세한 내용은 [읽기 전용이 되는 속성 설정](#ReadOnlyProperties)을 참조하십시오.  
  
### 리본의 생성자에서 속성 설정  
 속성을 설정할 수 있는 `Ribbon` 컨트롤의 생성자에는 **Ribbon** 클래스.  이 코드는 `InitializeComponent` 메서드를 호출한 후에 나타나야 합니다.  다음 예제에서는 현재 시간이 태평양 표준시\(UTC\-8\) 17:00 이후인 경우에 그룹에 새 단추를 추가합니다.  
  
 다음 코드를 추가합니다.  
  
 [!code-csharp[Trin_Ribbon_ObjectModel#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Ribbon_ObjectModel/CS/Ribbon1.Designer.cs#1)]
 [!code-vb[Trin_Ribbon_ObjectModel#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Ribbon_ObjectModel/VB/Ribbon1.Designer.vb#1)]  
  
 C\# Visual Studio 2008에서 업그레이드 하는 프로젝트를 생성자에서 리본 코드 파일에 표시 됩니다.  
  
 C\#에서 만든 프로젝트 또는 Visual Basic 프로젝트에서 [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)], 생성자 리본 디자이너 코드 파일에 표시 됩니다.  이 파일의 이름은 *YourRibbonItem*.Designer.cs 또는 *YourRibbonItem*.Designer.vb입니다.  Visual Basic 프로젝트에서 이 파일을 보려면 먼저 솔루션 탐색기에서 **모든 파일 표시** 단추를 클릭해야 합니다.  
  
### CreateRibbonExtensibilityObject 메서드에서 속성 설정  
 속성을 설정할 수는 `Ribbon` 재정의 하는 경우 컨트롤의 CreateRibbonExtensibilityObject 메서드에서 `ThisAddin`, `ThisWorkbook`, 또는 `ThisDocument` 프로젝트의 클래스.  CreateRibbonExtensibilityObject 메서드에 대한 자세한 내용은 [리본 개요](../vsto/ribbon-overview.md)을 참조하십시오.  
  
 리본 속성을 설정 하는 예제는 CreateRibbonExtensibilityObject 메서드는 `ThisWorkbook` Excel 통합 문서 프로젝트의 클래스입니다.  
  
 다음 코드를 추가합니다.  
  
 [!code-csharp[Trin_Ribbon_ObjectModel#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Ribbon_ObjectModel/CS/ThisWorkbook.cs#2)]
 [!code-vb[Trin_Ribbon_ObjectModel#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Ribbon_ObjectModel/VB/ThisWorkbook.vb#2)]  
  
###  <a name="ReadOnlyProperties"></a> 읽기 전용이 되는 속성  
 다음 표에서는 리본 메뉴가 로드되기 전에만 설정할 수 있는 속성을 보여 줍니다.  
  
> [!NOTE]  
>  동적 메뉴의 컨트롤 속성은 아무 때나 설정할 수 있습니다.  이러한 경우 다음 표의 내용이 적용되지 않습니다.  
  
|속성|리본 컨트롤 클래스|  
|--------|----------------|  
|**BoxStyle**|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox>|  
|**ButtonType**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|  
|**ColumnCount**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**ControlId**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|  
|**DialogLauncher**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|  
|**Dynamic**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|  
|**Global**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**그룹**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|  
|**ImageName**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDialogLauncher><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|  
|**ItemSize**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|  
|**MaxLength**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|  
|**이름**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComponent>|  
|**위치**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGroup><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonTab><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|  
|**RibbonType**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**RowCount**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**ShowItemImage**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**ShowItemLabel**|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**ShowItemSelection**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**SizeString**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|  
|**StartFromScratch**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**탭**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**제목**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|  
  
### Outlook 검사기에 나타나는 리본 메뉴의 속성 설정  
 리본 메뉴의 새 인스턴스를 열면 검사기 리본 메뉴 표시 될 때마다 만들어집니다.  그러나 리본 메뉴의 첫 번째 인스턴스가 만들어지기 전에만 위의 표에 나열 된 속성을 설정할 수 있습니다.  후 첫 번째 인스턴스를 만들 이러한 속성이 읽기 전용이 되므로 첫 번째 인스턴스가 Outlook에서 리본 메뉴를 로드 하는 XML 파일을 정의 합니다.  
  
 리본 메뉴의 다른 인스턴스가 만들어질 때 이러한 속성을 다른 값으로 설정 하는 조건부 논리를 사용 하는 경우이 코드는 효과가 없습니다.  
  
> [!NOTE]  
>  하는  **이름** Outlook 리본 메뉴에 추가한 각 컨트롤에 대해 속성을 설정 합니다.  런타임에 Outlook 리본 메뉴에 컨트롤을 추가 하면 코드에서이 속성을 설정 해야 있습니다.  디자인 타임에 Outlook 리본 메뉴에 컨트롤을 추가 하면 Name 속성이 자동으로 설정 됩니다.  
  
## 리본 컨트롤 이벤트  
 각 컨트롤 클래스에는 하나 이상의 이벤트가 포함되어 있습니다.  다음 표에서는 이러한 이벤트를 설명합니다.  
  
|Event|설명|  
|-----------|--------|  
|Click|컨트롤을 클릭하면 발생합니다.|  
|TextChanged|입력란 또는 콤보 상자의 텍스트가 변경되면 발생합니다.|  
|ItemsLoading|Office에서 컨트롤의 Items 컬렉션이 필요한 경우에 발생합니다.  코드를 통해 컨트롤의 속성이 변경될 때까지 Office에서 Items 컬렉션을 캐시하거나 사용자가 직접 <xref:Microsoft.Office.Core.IRibbonUI.InvalidateControl%2A> 메서드를 호출할 수 있습니다.|  
|ButtonClick|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> 또는 <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>의 단추를 클릭하면 발생합니다.|  
|SelectionChanged|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> 또는 <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>의 선택 영역이 변경되면 발생합니다.|  
|DialogLauncherClick|그룹의 오른쪽 아래에 있는 대화 상자 표시 아이콘을 클릭하면 발생합니다.|  
  
 이러한 이벤트에 대한 이벤트 처리기에는 다음 두 개의 매개 변수가 사용됩니다.  
  
|Parameter|설명|  
|---------------|--------|  
|*sender*|이벤트를 발생시킨 컨트롤을 나타내는 <xref:System.Object>입니다.|  
|*e*|<xref:Microsoft.Office.Core.IRibbonControl>이 들어 있는 <xref:Microsoft.Office.Tools.Ribbon.RibbonControlEventArgs>입니다.  이 컨트롤은 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서 제공하는 리본 개체 모델에서 사용할 수 없는 속성에 액세스하는 데 사용합니다.|  
  
## 참고 항목  
 [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)   
 [리본 개요](../vsto/ribbon-overview.md)   
 [방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [연습: 리본 디자이너를 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [연습: 런타임에 리본 메뉴의 컨트롤 업데이트](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)   
 [Outlook에 대해 리본 메뉴 사용자 지정](../vsto/customizing-a-ribbon-for-outlook.md)   
 [방법: 기본 제공 탭 사용자 지정](../vsto/how-to-customize-a-built-in-tab.md)   
 [방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)   
 [방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [방법: 추가 기능 사용자 인터페이스 오류 표시](../vsto/how-to-show-add-in-user-interface-errors.md)  
  
  