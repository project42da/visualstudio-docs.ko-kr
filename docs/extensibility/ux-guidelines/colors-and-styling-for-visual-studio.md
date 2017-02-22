---
title: "색 및 Visual Studio에 대 한 스타일 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0e384ea1-4d9e-4307-8884-6e183900732c
caps.latest.revision: 4
caps.handback.revision: 4
ms.author: "gregvanl"
manager: "ghogen"
---
# 색 및 Visual Studio에 대 한 스타일 지정
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

## Visual Studio에서 색을 사용 하 여  
 Visual Studio에서 색으로 장식으로 뿐만 아니라 통신 도구를 사용 됩니다. 색을 최소한으로 사용 하 고을 상황에 대 한 예약 합니다.  
  
-   통신 의미 나 정보 \(예: 플랫폼 또는 언어 한정자\)  
  
-   \(예: 상태 변경을 나타내는\) 관심을 갖게  
  
-   가독성을 향상 하 고 UI 탐색을 위한 이정표를 제공 합니다.  
  
-   원활 하 게 사용할 증가  
  
 Visual Studio에서 UI 요소에 색을 할당 하기 위한 몇 가지 옵션이 있습니다. 때로는 그림 어려울 수 있습니다 옵션을 사용 하기로 하 또는 올바르게 사용 하는 방법입니다. 이 항목 도움이 됩니다.  
  
1.  다른 서비스와 Visual Studio에서 색을 정의 하는 데 사용 하는 시스템을 이해 합니다.  
  
2.  지정된 된 요소에 대 한 올바른 옵션을 선택 합니다.  
  
3.  선택한 옵션을 올바르게 사용.  
  
 **중요:** 하드 코딩 16 진수, RGB 또는 UI 요소에 대 한 시스템 색 하지 않습니다. 서비스를 사용 하 여 유연 하 게 색상 튜닝 있습니다. 또한 서비스를 사용 하지 않는 됩니다의 테마 전환 기능을 이용할 수는 [VSColor 서비스](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_TheVSColorService)합니다.  
  
### Visual Studio 인터페이스 요소에 색을 할당 하기 위한 메서드  
 UI 요소에 가장 적합 한 방법을 선택 합니다.  
  
|UI|메서드|어떤 방법 일까요?|  
|--------|---------|----------------|  
|포함 된 또는 독립 실행형 대화 상자입니다.|**시스템 색**|운영 체제와 같은 색상과 UI 요소의 모양을 공용 대화 상자 컨트롤에 대 한 정의를 허용 하는 시스템 이름입니다.|  
|전체 VS 환경와 일치 하도록 원하는 사용자 지정 UI 있고 범주와 공유 하는 토큰의 의미와 일치 하는 UI 요소를 포함할 수 있습니다.|**일반적인 공유 색**|특정 UI 요소에 대 한 기존 미리 정의 된 색 토큰 이름|  
|개별 기능 또는 기능 그룹 및 유사한 요소에 대 한 색이 없으면 공유 합니다.|**사용자 지정 색**|영역에 관련 되며 하지 다른 UI와 공유할 수는 색 토큰 이름|  
|최종 사용자 \(예: 텍스트 편집기 또는 디자이너 창 특수화 된\) UI 또는 콘텐츠를 사용자 지정할 수 있도록 하려고 합니다.|**최종 사용자의 사용자 지정**<br /><br /> **\(도구 \> 옵션 대화 상자\)**|"글꼴 및 색" 페이지에 정의 된 설정을 **도구 \> 옵션** 대화 또는 특정 한 UI 기능에 특수 한 페이지입니다.|  
|HTML에서 작성 된 UI 해야 합니다.|**Daytona**|UI를 색 및 글꼴 서비스에 액세스 하는 HTML로 작성할 수 있습니다.|  
  
### Visual Studio 테마  
 Visual Studio의 세 가지 서로 다른 색 테마 기능: 가볍고, 진한 파란색입니다. 또한 고대비 모드는 내게 필요한 옵션 지원 하기 위한 시스템 차원의 색 테마를 검색 합니다.  
  
 사용자가 Visual Studio를 처음 사용 하는 동안에 테마를 선택 하 라는 메시지가 나타나면 및로 이동 하 여 테마를 나중에 전환할 수 **도구 \> 옵션 \> 환경 \> 일반** "색 테마" 드롭다운 메뉴에서 새 테마를 선택 합니다.  
  
 사용자가 제어판을 사용 하 여 여러 고대비 테마 중 하나에 전체 시스템을 전환할 수 있습니다. 사용자가 고대비 테마를 선택 하는 경우 다음 Visual Studio 색상 테마 선택 기가 더 이상 영향을 줍니다 Visual Studio의 색을 있지만 사용자가 고대비 모드를 종료 하는 경우 모든 테마 변경에 대 한 저장 됩니다. 고대비 모드에 대 한 자세한 내용은 참조 [고대비 색상을 선택합니다.](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_ChoosingHighContrastColors)합니다.  
  
### VSColor 서비스  
 Visual Studio UI 요소에 색 값을 각 Visual Studio 테마 색 값을 포함 하는 명명 된 항목을 바인딩할 수 있는 VSColor 서비스 라고 하는 환경 색 서비스를 제공 합니다. 이렇게 하면 색을 현재 사용자가 선택한 테마 또는 시스템 고대비 모드를 반영 하도록 자동으로 변경 됩니다. 서비스 사용을 한 곳에서 처리 되는 모든 색 테마와 관련 된 변경 내용 구현 하 고 서비스에서 일반적인 공유 색을 사용 하는 UI를 자동으로 반영 됩니다 이후 버전의 Visual Studio에서 새 테마를 의미 합니다.  
  
### 구현  
 Visual Studio 소스 코드에 토큰 이름 및 각 테마에 대 한 각 색상 값의 목록을 포함 하는 여러 패키지 정의 파일에 포함 됩니다. 색 서비스는 이러한 패키지 정의 파일에 정의 된 VSColors를 읽습니다. 이러한 색을 XAML 마크업에서 또는 코드에서 참조 하 고 다음 중 하나를 통해 로드 된 **IVsUIShell5.GetThemedColor** 메서드 또는 DynamicResource 매핑.  
  
### 시스템 색  
 공용 컨트롤 기본적으로 시스템 색을 참조합니다. UI가 포함 되거나 독립 실행형 대화 상자를 만들 때와 같이 시스템 색을 사용 하 여 원하는 작업을 수행할 필요가 없습니다.  
  
### VSColor 서비스의 일반적인 공유 색  
 사용자 인터페이스 요소에는 전체 Visual Studio 환경을 반영 해야 합니다. 디자인할 UI 구성 요소에 해당 되는 일반적인 공유 색을 다시 사용 하 여 인터페이스에 다른 Visual Studio 인터페이스와 일치 하 고 테마 추가 되거나 업데이트 되 면 색은 자동으로 업데이트를 확인 합니다.  
  
 일반적인 공유 색을 사용 하기 전에 올바르게 사용 하는 방법을 이해 하 고 있는지 확인 합니다. 사용자가 일치 하지 않는 불편 함을 느끼게, 또는 혼란 스러운 환경을 공유 일반적인 색의 잘못 된 사용 될 수 있습니다.  
  
### 사용자 지정이 가능한 색  
 참조 하십시오. [최종 사용자에 대 한 색을 노출합니다.](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_ExposingColorsForEndUsers)  
  
 경우에 따라 최종 사용자는 코드 편집기 또는 디자인 화면을 만들 때와 같은 UI를 사용자 지정할 수 있도록 합니다. 사용자 지정 가능한 UI 구성 요소에서 발견 되는 **글꼴 및 색** 의 섹션은 **도구 \> 옵션** 전경색, 배경색, 또는 둘 다를 변경 하려면 사용자가 선택할 수 있는 대화 상자.  
  
 ![Tools &#62; Options dialog in Visual Studio](../../extensibility/ux-guidelines/media/0301-a_toolsoptionsdialog.png "0301\-a\_ToolsOptionsDialog")  
  
 **도구 \> 옵션 대화 상자**  
  
### 웹 UI 색  
 Visual Studio online 및 Visual Studio 내에서 사용할 수 있도록 HTML을 사용 하 여 만든 UI 구성 요소에 공통 되 고가 있습니다. 여전히 HTML로 작성 된 UI는 Visual Studio 환경 내에서 실행할 때는 VSColor 서비스를 사용 해야 합니다. Daytona 및 사용 하는 방법에 대 한 정보를 참조 하십시오. [Daytona 및 웹 UI](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_DaytonaAndWebUI)합니다.  
  
##  <a name="BKMK_TheVSColorService"></a> VSColor 서비스  
 Visual Studio VSColor 서비스 또는 셸 색 서비스 라고도 하는 환경 색 서비스를 제공 합니다. 이 서비스를 사용 하면 각 테마에 대 한 색 포함 된 집합 이름\-값 색을 UI 요소에 색 값을 바인딩할 수 있습니다. 색이 자동으로 현재 사용자가 선택한 테마를 반영 하도록 변경 되 고 UI 환경 색 서비스에 바인딩된 있도록와 통합 합니다 새 테마 이후 버전의 Visual Studio 모든 UI 요소에 대해 VSColor 서비스를 사용 해야 합니다.  
  
### 서비스의 작동 원리  
 환경 색 서비스 VSColors.pkgdef UI 구성 요소에 대 한 정의 읽습니다. 이러한 VSColors 코드 또는 XAML 태그에서 다음 참조 및를 통해 로드 되는 **IVsUIShell5.GetThemedColor** 또는 DynamicResource 매핑.  
  
 ![Environment color service architecture](../../extensibility/ux-guidelines/media/0302-a_environmentcolorservicearchitecture.png "0302\-a\_EnvironmentColorServiceArchitecture")  
  
 **환경 색 서비스 아키텍처**  
  
### 서비스에 액세스  
 여러 가지 방법으로 액세스 하면 토큰의 색의 종류에 따라 VSColor 서비스를 사용 하는 컴퓨터에 설치 된 코드의 종류 및 있습니다.  
  
#### 미리 정의 된 환경 색  
  
##### 네이티브 코드에서  
 셸 색의 COLORREF에 대 한 액세스를 제공 하는 서비스를 제공 합니다. 다음은 서비스\/인터페이스입니다.  
  
```  
IVsUIShell2::GetVSSysColorEx(VSSYSCOLOR dwSysColIndex, DWORD *pdwRGBval)  
```  
  
 파일 VSShell80.idl, 열거형에서에서 **\_\_VSSYSCOLOREX** 셸 색 상수 했습니다. 사용 하 여 인덱스 값이 MSDN에 문서화 enum \_\_VSSYSCOLOREX의 값 중 하나 이거나 일반 인덱스 번호 API, Windows 시스템으로 전달 **GetSysColor**, 를 허용 합니다. 이 두 번째 매개 변수에서 사용 해야 하는 색의 RGB 값을 다시 가져옵니다.  
  
 펜 또는 새 색을 사용 하 여 브러시를 저장 하는 경우 AdviseBroadcastMessages \(외부 Visual Studio shell\) 해야 하 고 WM\_SYSCOLORCHANGE 및 WM\_THEMECHANGED 메시지를 수신 대기 합니다.  
  
```  
// To access the color service in native code, you'll make a call that resembles this: pUIShell2->GetVSSysColorEx(VSCOLOR_COLOR_NAME, &rgbLOCAL_COLOR);  
  
```  
  
 **참고:** The COLORREF 값에서 반환 된 **GetVSSysColorEx\(\)** 포함 방금 R, G, 테마 색의 B 구성 요소입니다. 테마 항목에서 투명도 사용 하는 경우 알파 채널 값을 반환 하기 전에 삭제 됩니다. 따라서 원하는 환경 색 투명도 채널 않은 중요 한 위치에서 사용할 수 하는 경우이 항목의 뒷부분에 설명 된 대로 IVsUIShell2::GetVSSysColorEx, 대신 IVsUIShell5.GetThemedColor 사용 해야 있습니다.  
  
##### 관리 코드에서  
 네이티브 코드를 통해 VSColor 서비스에 액세스 하는 것은 매우 간단 합니다. 그러나 관리 되는 코드를 통해 작업 하는 경우 서비스를 사용 하는 방법을 결정 까다로울 수 있습니다. 이 점을 염두에서이 프로세스를 보여 주는 C\# 코드 조각은 다음과 같습니다.  
  
```  
private void VSColorPaint(object sender, System.Windows.Forms.PaintEventArgs e) { //getIVSUIShell2 IVsUIShell2 uiShell2 = Package.GetService(typeof(SVsUIShell)) as IVsUIShell2; Debug.Assert (uiShell2 != null, "failed to get IVsUIShell2"); if (uiShell2 != null) { //get the COLORREF structure uint win32Color; uiShell.GetVSSysColorEx(VSSYSCOLOREX.VSCOLOR_SMARTTAG_HOVER_FILL, out win32Color); //translate it to a managed Color structure Color myColor = ColorTranslator.FromWin32((int)win32Color); //use it e.Graphics.FillRectangle(new SolidBrush(myColor), 0, 0, 100, 100); } }  
```  
  
 Visual Basic에서 작업 하는 경우 사용 합니다.  
  
```  
Dim myColor As Color = ColorTranslator.FromWin32((Integer)win32Color)  
```  
  
##### WPF UI에서  
 응용 프로그램의 ResourceDictionary에 내보낸 값을 통해 Visual Studio 색에 바인딩할 수 있습니다. 다음은 XAML의 환경 글꼴 데이터에 바인딩 뿐만 아니라 리소스 색상표를 사용 하는 예제입니다.  
  
```  
<Style TargetType="{x:Type Button}"> <Setter Property="TextBlock.FontFamily" Value="{DynamicResource VsFont.EnvironmentFontFamily}" /> <Setter Property="TextBlock.FontSize" Value="{DynamicResource VsFont.EnvironmentFontSize}" /> <Setter Property="Background" Value="{DynamicResource VsBrush.EnvironmentBackgroundGradient}" /> </Style>  
```  
  
#### 관리 코드의 도우미 클래스 및 메서드  
 셸의 관리 되는 패키지 프레임 워크 라이브러리 \(Microsoft.VisualStudio.Shell.12.0.dll\) 관리 코드에 대 한 두 가지 테마가 지정 된 색의 사용을 촉진 하는 도우미 클래스를 포함 합니다.  
  
 사용 되는 도우미 메서드는 **Microsoft.VisualStudio.Shell.VsColors** MPF에서 클래스에 포함 **GetThemedGDIColor\(\)** 및 **GetThemedWPFColor\(\)**합니다. 이러한 도우미 메서드는 System.Drawing.Color 또는 System.Windows.Media.Color, WinForms 또는 WPF UI에서 사용할 수 있는 테마 항목의 색 값을 반환 합니다.  
  
```  
IVsUIShell5 shell5; Button button = new Button(); button.BackColor = GetThemedGDIColor(shell5, SolutionExplorerColors.SelectedItemBrushKey); button.ForeColor = GetThemedGDIColor(shell5, SolutionExplorerColors.SelectedItemTextBrushKey); /// <summary> /// Gets a System.Drawing.Color value from the current theme for the given color key. /// </summary> /// <param name="vsUIShell">The IVsUIShell5 service, used to get the color's value.</param> /// <param name="themeResourceKey">The key to find the color for.</param> /// <returns>The current theme's value of the named color.</returns> public static System.Drawing.Color GetThemedGDIColor(this IVsUIShell5 vsUIShell, ThemeResourceKey themeResourceKey) { Validate.IsNotNull(vsUIShell, "vsUIShell"); Validate.IsNotNull(themeResourceKey, "themeResourceKey"); byte[] colorComponents = GetThemedColorRgba(vsUIShell, themeResourceKey); // Note: The Win32 color we get back from IVsUIShell5.GetThemedColor is ABGR return System.Drawing.Color.FromArgb(colorComponents[3], colorComponents[0], colorComponents[1], colorComponents[2]); } private static byte[] GetThemedColorRgba(IVsUIShell5 vsUIShell, ThemeResourceKey themeResourceKey) { Guid category = themeResourceKey.Category; __THEMEDCOLORTYPE colorType = __THEMEDCOLORTYPE.TCT_Foreground if (themeResourceKey.KeyType == ThemeResourceKeyType.BackgroundColor || themeResourceKey.KeyType == ThemeResourceKeyType.BackgroundBrush) { colorType = __THEMEDCOLORTYPE.TCT_Background; } // This call will throw an exception if the color is not found uint rgbaColor = vsUIShell.GetThemedColor(ref category, themeResourceKey.Name, (uint)colorType); return BitConverter.GetBytes(rgbaColor); } public static System.Windows.Media.Color GetThemedWPFColor(this IVsUIShell5 vsUIShell, ThemeResourceKey themeResourceKey) { Validate.IsNotNull(vsUIShell, "vsUIShell"); Validate.IsNotNull(themeResourceKey, "themeResourceKey"); byte[] colorComponents = GetThemedColorComponents(vsUIShell, themeResourceKey); return System.Windows.Media.Color.FromArgb(colorComponents[3], colorComponents[0], colorComponents[1], colorComponents[2]); }  
  
```  
  
 주어진된 WPF 색 리소스 키에 대 한 VSCOLOR 식별자를 가져오려면 클래스도 사용할 수 또는 그 반대의 경우도 마찬가지입니다.  
  
```  
public static string GetColorBaseKey(int vsSysColor); public static bool TryGetColorIDFromBaseKey(string baseKey, out int vsSysColor);  
```  
  
 메서드 **VsColors** 될 때마다 호출 되는 색 값을 반환 하는 VSColor 서비스를 쿼리 하는 클래스입니다. 으로 색 값을 가져올 **System.Drawing.Color**, 향상 된 성능의 대안이 대신의 메서드를 사용 하는 것은 **Microsoft.VisualStudio.PlatformUI.VSThemeColor** VSColor 서비스에서 가져온 색 값을 캐시 하는 클래스입니다. 클래스는 셸 브로드캐스트 메시지 이벤트를 내부적으로 구독 하 고 테마 변경 이벤트가 발생할 때 캐시 된 값을 삭제 합니다. 또한 제공 하는 클래스는 합니다. 테마 변경 구독할 NET 친화적인 이벤트입니다. 사용 하 여는 **ThemeChanged** 새 처리기를 추가 하 고 사용 하 여 이벤트를는 **GetThemedColor\(\)** 구하는 색에 대 한 값은 **ThemeResourceKeys** 관심 합니다. 샘플 코드는 다음과 같습니다.  
  
```  
public MyWindowPanel() { InitializeComponent(); // Subscribe to theme changes events so we can refresh the colors VSColorTheme.ThemeChanged += VSColorTheme_ThemeChanged; RefreshColors(); } private void VSColorTheme_ThemeChanged(ThemeChangedEventArgs e) { RefreshColors(); // Also post a message to all the children so they can apply the current theme appropriately foreach (System.Windows.Forms.Control child in this.Controls) { NativeMethods.SendMessage(child.Handle, e.Message, IntPtr.Zero, IntPtr.Zero); } } private void RefreshColors() { this.BackColor = VSColorTheme.GetThemedColor(EnvironmentColors.ToolWindowBackgroundColorKey); this.ForeColor = VSColorTheme.GetThemedColor(EnvironmentColors.ToolWindowTextColorKey); } protected override void Dispose(bool disposing) { if (disposing) { VSColorTheme.ThemeChanged -= this.VSColorTheme_ThemeChanged; base.Dispose(disposing);} }  
```  
  
##  <a name="BKMK_ChoosingHighContrastColors"></a> 고대비 색상을 선택합니다.  
  
### 개요  
 Windows 더 분명 화면에 표시 되는 요소에 텍스트, 배경 및 이미지의 색상 대비 증가 하는 여러 고대비 시스템 수준 테마를 사용 합니다. 이 액세스 가능성을 위해 사용자가 고대비 테마를 전환할 때 Visual Studio 인터페이스 요소 올바르게 응답 중요 합니다.  
  
 고대비 테마에 대 한 시스템 색 밖에 사용할 수 있습니다. 시스템 색 이름을 선택할 때 다음 팁을 기억해 야 합니다.  
  
1.  **동일한 의미 체계 의미를 가지는 시스템 색 선택** 강조 되는 요소와 합니다. 예를 들어, 텍스트 창에 고대비 색을 선택 하는 경우 WindowText 및 하지 ControlText를 사용 합니다.  
  
2.  **전경\/배경 쌍을 선택** 함께 또는 모든 고대비 테마의 색 선택을 작동 하는지 확신할 수 없습니다.  
  
3.  **가장 중요 한 UI의 어떤 부분을 확인 하 고 콘텐츠 영역 차별화 됩니다 확인 합니다.** 여러 콘텐츠 영역에 대 한 색 변형이 없는 있기 때문에 강력한 테두리 색을 사용 콘텐츠 영역 정의에 공통적으로 적용 되므로 다양 한 색 색상의 미묘한 차이 구분 하기 일반적으로 세부 손실 됩니다.  
  
### 시스템 색 집합  
 테이블에 [WPF 팀 블로그: SystemColors 참조](http://blogs.msdn.com/b/wpf/archive/2010/11/30/systemcolors-reference.aspx) 시스템 색 이름 및 각 테마에 표시 된 해당 색상의 전체 집합을 나타냅니다.  
  
 UI에 대 한 색 집합을 제한이 적용 될 때 *미묘한 세부 정보 "일반" 테마에 있던를 잃게 될 것*합니다. 도구 창 내에서 영역을 구분 하는 데 사용 되는 미묘한 회색 색으로 UI의 예를 들면 다음과 같습니다. 고대비 모드에 표시 된 동일한 창을 이루는 모든 배경이 색조를 해당 영역의 테두리 테두리 단독으로 표시 됩니다를 확인할 수 있습니다.  
  
 ![Properties window](../../extensibility/ux-guidelines/media/030303-a_propertieswindow.png "030303\-a\_PropertiesWindow")  
  
 **어떻게 미묘한 세부 정보의 예제 고대비에 있을 때 손실 됩니다.**  
  
#### 편집기에서 텍스트 색을 선택합니다.  
 컬러로 텍스트는 유사 항목 그룹을 쉽게 식별 하기 위해 허용 하는 등의 의미를 나타내기 위해 편집기에서 또는 디자인 화면에 사용 됩니다. 그러나 고대비 테마의 않아도 세 개 이상의 텍스트 색을 구분 하는 기능입니다. WindowText, GrayText 및 HotTrackText WindowBackground 표면에 사용할 수 있는 유일한 색을입니다. 4 가지 이상의 색을 사용할 수 없으므로 신중 하 게 고대비 모드에 있을 때 표시할 가장 중요 한 차이점을 선택 합니다.  
  
 각 각 고대비 테마에 표시 되는 편집기 화면에서 허용 되는 토큰 이름에 대 한 색상:  
  
 ![High Contrast editor comparison](../../extensibility/ux-guidelines/media/030303-b_hceditorcomparison.png "030303\-b\_HCEditorComparison")  
  
 **고대비 편집기 비교**  
  
 파란색 테마의 편집기 화면의 예:  
  
 ![Editor in Blue theme](../../extensibility/ux-guidelines/media/030303-c_editorblue.png "030303\-c\_EditorBlue")  
  
 **파란색 테마의 편집기**  
  
 ![Editor in High Contrast theme](../../extensibility/ux-guidelines/media/030303-d_editorhc1.png "030303\-d\_EditorHC1")  
  
 **고대비 \#1 테마의 편집기**  
  
### 사용 패턴  
 많은 일반적인 UI 요소에 이미 정의 된 고대비 색입니다. 참조할 수 있습니다 이러한 사용 패턴 색 이름, 사용자 자신의 시스템을 선택할 때 UI 요소는 비슷한 구성 요소와 일치 합니다.  
  
|시스템 색|사용량|  
|-----------|---------|  
|ActiveCaption|-   활성 IDE 및 rafted 창 호버 누릅니다에 있는 문자 모양의 단추<br />-   IDE 및 rafted windows에 대 한 제목 표시줄 배경<br />-   기본 상태 표시줄 배경색|  
|ActiveCaptionText|-   활성 IDE 및 제목 표시줄 전경 \(텍스트 및 문자 모양\)에 대 한 rafted 기간<br />-   배경 및 호버 및 키를 눌러 활성 창 단추의 테두리|  
|컨트롤|-   기본 및 드롭다운 단추를 포함 하 여 비활성화 된 배경 콤보 상자, 드롭다운 목록 및 검색 제어<br />-   도킹 대상 단추 배경<br />-   명령 모음 배경<br />-   도구 창 배경|  
|ControlDark|-   IDE 배경<br />-   메뉴 및 명령 모음 구분 기호<br />-   명령 모음 테두리<br />-   메뉴 그림자<br />-   도구 창 탭 기본 커서를 놓으면 테두리 및 구분 기호<br />-   오버플로 단추 배경 잘 문서화<br />-   도킹 대상 문자 모양의 테두리|  
|ControlDarkDark|-   포커스가 없는 선택한 문서 탭 창|  
|ControlLight|-   자동 숨기기 탭 테두리<br />-   콤보 상자 및 드롭다운 목록에서 테두리<br />-   도킹 대상 배경색 및 테두리|  
|ControlLightLight|-   선택한, 집중 된 임시 테두리|  
|ControlText|-   콤보 상자 및 드롭다운 목록에서 문자 모양<br />-   도구 창 선택 취소 된 상태로 탭 텍스트|  
|GrayText|-   테두리, 드롭다운 문자 모양, 텍스트 및 메뉴 항목의 텍스트 콤보 상자 및 드롭다운 목록에 사용할 수 없습니다.<br />-   비활성화 메뉴 텍스트<br />-   검색 컨트롤 '검색 옵션' 머리글 텍스트<br />-   검색 컨트롤 섹션 구분 기호|  
|강조 표시|-   모든 마우스를 이동 하 고 콤보 상자 드롭다운 제외 하 고, 테두리 및 배경 누름 단추 배경 및 문서도 오버플로 단추 테두리<br />-   선택한 항목 배경|  
|HighlightText|-   모든 가리키기 및 누름된 foregrounds \(텍스트 및 문자 모양\)<br />-   포커스가 있는 도구 창 및 문서 탭 창 컨트롤 전경<br />-   포커스가 있는 도구 창 제목 표시줄 테두리<br />-   포커스가 있는, 선택한\-임시 탭 전경<br />-   가리키기 및 키를 눌러 문서 잘 오버플로 단추 테두리<br />-   선택 된 아이콘 테두리|  
|HotTrack|-   스크롤 막대의 엄지 단추 배경 및 키를 눌러에 테두리<br />-   스크롤 막대 화살표 키를 눌러는 문자 모양|  
|InactiveCaption|-   비활성 IDE 및 가리키기 rafted 창 단추 문자<br />-   IDE 및 rafted windows에 대 한 제목 표시줄 배경<br />-   비활성화 된 검색 컨트롤 배경|  
|InactiveCaptionText|-   비활성 IDE 및 rafted windows 제목 표시줄 전경 \(텍스트 및 문자 모양\)<br />-   비활성 창 단추 배경색 및 테두리 가리키기<br />-   포커스가 없는 도구 창 단추 배경색 및 테두리<br />-   비활성화 된 검색 컨트롤 전경|  
|메뉴|-   드롭다운 메뉴 배경<br />-   Checked 및 사용 안 함 확인 표시 배경|  
|MenuText|-   드롭다운 메뉴 테두리<br />-   확인 표시 확인<br />-   문자 모양의 메뉴<br />-   드롭다운 메뉴 텍스트<br />-   선택 된 아이콘 테두리|  
|스크롤 막대|-   스크롤 막대 및 스크롤 막대 화살표 배경 모든 상태|  
|창|-   자동 숨기기 탭 배경<br />-   메뉴 모음 및 명령 선반 배경<br />-   포커스가 없는 또는 선택 되지 않은 문서 창 탭 배경 및 열기 및\-임시 탭에 대 한 문서 테두리<br />-   포커스가 없는 도구 창 제목 표시줄 배경<br />-   도구 창 탭 배경 둘 다 선택 및 선택이 취소|  
|WindowFrame|-   IDE 테두리|  
|WindowText|-   자동 숨기기 탭 전경<br />-   선택한 도구 창 탭 전경<br />-   포커스가 없는 문서 창 탭 및\-임시 탭 포커스가 없는 또는 선택 취소 전경<br />-   트리 보기의 기본 전경 및 가리키기 선택 하지 않은 문자 모양<br />-   도구 창 선택 된 탭 테두리<br />-   스크롤 막대의 엄지 단추 배경, 테두리 및 문자 모양|  
  
##  <a name="BKMK_ExposingColorsForEndUsers"></a> 최종 사용자에 대 한 색을 노출합니다.  
  
### 개요  
 최종 사용자 코드 편집기 또는 디자인 화면을 만들 때와 같은 UI를 사용자 지정할 수 있도록 수도 있습니다. 이 작업을 수행 하는 가장 일반적인 방법은 사용 하는 것은 **도구 \> 옵션** 대화 합니다. 통해 사용자 지정을 제공 하는 가장 쉬운 방법은 특수 컨트롤을 필요로 하는 UI, 특수 한 항상 있는 경우가 아니면는 **글꼴 및 색** 내에서 페이지는 **환경** 대화 상자의 섹션입니다. 사용자 지정을 위해 노출 하는 각 요소에 대 한 사용자는 전경색, 배경색, 또는 둘 다 변경 하도록 선택할 수 있습니다.  
  
### 사용자 지정 색에 대 한 VSPackage를 구축합니다.  
 VSPackage는 글꼴 및 색 사용자 지정 범주를 통해 제어 하 고 글꼴 및 색 속성 페이지에서 항목을 표시할 수 있습니다. Vspackage를 구현 해야이 메커니즘을 사용 하는 경우는 [IVsFontAndColorDefaultsProvider](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaultsprovider.aspx) 인터페이스와 연결 된 해당 인터페이스입니다.  
  
 원칙적으로이 메커니즘 모든 기존 항목 및 포함 된 범주를 수정 하려면 사용할 수 있습니다. 그러나 하지 사용할 텍스트 편집기 범주 또는 표시 항목을 수정 하 합니다. 텍스트 편집기 범주에 대 한 자세한 내용은 참조 하십시오. [글꼴 및 색상 개요](https://msdn.microsoft.com/en-us/library/bb165065.aspx)합니다.  
  
 VSPackage를 사용자 지정 범주를 구현 하거나 항목을 표시 하려면 다음을 해야 합니다.  
  
-   **만들거나 레지스트리에 범주를 식별 합니다.** IDE의 구현은 **글꼴 및 색** 속성 페이지에서이 정보를 사용 하 여 올바르게 지정된 된 범주를 지 원하는 서비스를 쿼리할 수 있습니다.  
  
-   **만들거나 레지스트리 \(선택 사항\)에서 그룹을 식별 합니다.** 두 개 이상의 범주 합집합을 나타내는 그룹을 정의 하면 유용할 수 있습니다. 그룹을 정의 하는 경우 IDE 자동으로 병합 하는 하위 범주 고이 배포 그룹 내에서 항목을 표시 합니다.  
  
-   **IDE 지원을 구현 합니다.**  
  
-   **글꼴 및 색 변경 내용을 처리 합니다.**  
  
#### 만들거나 범주를 식별 하려면  
 특수 한 유형의 \[HKLM\\SOFTWARE\\Microsoft \\Visual Studio\\ \< Visual Studio 버전 \> \\FontAndColors\\ \< 범주 \>\] 아래 범주 레지스트리 항목을 생성 합니다. \< 범주 \>에 범주에 속하는 지역화 되지 않은 이름입니다.  
  
 두 개의 값으로 레지스트리를 채웁니다.  
  
|이름|형식|데이터|설명|  
|--------|--------|---------|--------|  
|범주|REG\_SZ|GUID|범주를 식별 하기 위해 만든 GUID|  
|Package|REG\_SZ|GUID|범주를 지 원하는 VSPackage 서비스의 GUID|  
  
 레지스트리에 지정 된 서비스의 구현을 제공 해야 [IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx) 해당 범주에 대 한 합니다.  
  
#### 그룹 만들기 또는 식별 하려면  
 특수 한 유형의 \[HKLM\\SOFTWARE\\Microsoft \\Visual Studio\\ \< Visual Studio 버전 \> \\FontAndColors\\ \< 그룹 \>\] 아래 범주 레지스트리 항목을 생성 합니다. \< 그룹 \> 그룹의 지역화 되지 않은 이름입니다.  
  
 두 개의 값으로 레지스트리를 채웁니다.  
  
|이름|형식|데이터|설명|  
|--------|--------|---------|--------|  
|범주|REG\_SZ|GUID|범주를 식별 하기 위해 만든 GUID|  
|Package|REG\_SZ|GUID|범주를 지 원하는 VSPackage 서비스의 GUID|  
  
 레지스트리에 지정 된 서비스의 구현을 제공 해야 **T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup** 해당 그룹에 대 한 합니다.  
  
 ![IVsFontAndColorGroup](../../extensibility/ux-guidelines/media/0304-a_fontandcolorgroup.png "0304\-a\_FontAndColorGroup")  
  
### IDE 지원을 구현 하려면  
 구현 [GetObject](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaultsprovider.getobject.aspx), 를 반환 하는 [IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx) 인터페이스 또는 **T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup** 각 범주에 대 한 IDE에 인터페이스 또는 제공 된 GUID를 그룹화 합니다.  
  
 VSPackage 지 원하는 모든 범주에 대 한 별도의 인스턴스를 구현 하는 [IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx) 인터페이스입니다.  
  
 메서드를 통해 구현 [IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx) 사용 하는 IDE를 제공 해야 합니다.  
  
-   범주의 표시 항목 목록  
  
-   표시 항목에 대 한 지역화 가능한 이름  
  
-   범주에 속하는 각 멤버에 대 한 정보를 표시 합니다.  
  
 **참고:** 모든 범주 표시 항목을 하나 이상 포함 해야 합니다.  
  
 IDE를 사용 하는 **T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup** 여러 종류의 합집합을 정의 하는 인터페이스입니다.  
  
 구현을 사용 하는 IDE를 제공합니다.  
  
-   지정된 된 그룹을 구성 하는 범주 목록  
  
-   인스턴스에 대 한 액세스 [IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx) 그룹 내에서 각 범주를 지원 합니다.  
  
-   지역화할 수 있는 그룹 이름  
  
#### IDE를 업데이트합니다.  
 IDE 글꼴 및 색상 설정에 대 한 정보를 캐시합니다. 따라서 IDE 글꼴 및 색 구성의 모든 수정 후 인지 확인 하는 캐시를 최신으로 가장 좋습니다.  
  
 통해 이루어집니다 캐시를 업데이트는 [IvsFontAndColorCacheManager](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorcachemanager.aspx) 인터페이스를 전역으로 또는 있는 것이 아니라 선택한 항목으로 수행된 될 수 있습니다.  
  
### 글꼴 및 색 변경 내용 처리  
 VSPackage를 표시 하는 텍스트의 색 지정을 올바르게 지원 하려면 VSPackage를 지 원하는 색 조정 서비스 사용자가 시작한 변경 글꼴 및 색 속성 페이지 내용에 응답 해야 합니다.  
  
 이 작업을 수행 하려면 VSPackage 해야 합니다.  
  
-   **IDE에서 생성 된 이벤트를 처리할** 를 구현 하 여는 [IVsFontAndColorEvents](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorevents.aspx) 인터페이스입니다. IDE 글꼴 및 색 페이지의 사용자 수정 해도 다음 적절 한 메서드를 호출 합니다. 예를 들어 호출는 [OnFontChanged](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorevents.onfontchanged.aspx) 메서드는 새 글꼴을 선택 합니다.  
  
 **또는**  
  
-   **변경에 대 한 IDE를 폴링할**합니다. 시스템 구현를 통해이 작업을 수행할 수 있습니다 [IVsFontAndColorStorage](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorstorage.aspx) 인터페이스입니다. 하지만 주로 지원에 대 한 지 속성의 [GetItem](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorstorage.getitem.aspx) 메서드 표시 항목에 대 한 글꼴 및 색 정보를 얻을 수 있습니다. 글꼴 및 색상 설정에 대 한 자세한 내용은 MSDN 기사를 참조 하십시오. [에 액세스 하는 저장 된 글꼴 및 색 설정을](https://msdn.microsoft.com/en-us/library/bb166382.aspx)합니다.  
  
 **참고:** 사용을 보장 하기 위해 폴링 결과가 올바른지는 [IVsFontAndColorCacheManager](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorcachemanager.aspx) 캐시 플러시 및 업데이트의 검색 메서드를 호출 하기 전에 필요한 지 확인 하는 인터페이스는 [IVsFontAndColorStorage](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorstorage.aspx) 인터페이스입니다.  
  
#### 인터페이스를 구현 하지 않고 사용자 지정 글꼴 및 색 범주를 등록 합니다.  
 다음 코드 예제에서는 인터페이스를 구현 하지 않고 색 범주 및 사용자 지정 글꼴을 등록 하는 방법을 보여 줍니다.  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\FontAndColors\CSharp Tool Window] "Package"="{F5E7E71D-1401-11D1-883B-0000F87579D2}" "Category"="{9FF46859-A47E-47bf-8AC5-EC3DBE69D1FE}" "ToolWindowPackage"="{7259e420-6241-4e0d-b535-5b820671d183}" "NameID"=dword:00000064  
```  
  
 **참고:**  
  
-   "NameID" 패키지에서 지역화 된 범주 이름의 리소스 ID \=  
  
-   "ToolWindowPackage" 패키지 GUID \=  
  
-   "Category" \= "{9FF46859\-A47E\-47bf\-8AC5\-EC3DBE69D1FE}" 예로 든 것일 뿐 이며 실제 값은 구현자에 의해 제공 되는 새 GUID를 수 있습니다.  
  
### GUID의 글꼴 및 색 속성 범주를 설정 합니다.  
 아래 코드 예제에서는 범주의 Guid를 설정 하는 방법을 보여 줍니다.  
  
```  
// m_pView is your IVsTextView IVsTextEditorPropertyCategoryContainer spPropCatContainer = (IVsTextEditorPropertyCategoryContainer)m_pView; if (spPropCatContainer != null) { IVsTextEditorPropertyContainer spPropContainer; Guid GUID_EditPropCategory_View_MasterSettings = new Guid("{D1756E7C-B7FD-49a8-B48E-87B14A55655A}"); hr = spPropCatContainer.GetPropertyCategory( ref GUID_EditPropCategory_View_MasterSettings, out spPropContainer); if(hr == 0) { hr = spPropContainer.SetProperty( VSEDITPROPID.VSEDITPROPID_ViewGeneral_FontCategory, catGUID); hr = spPropContainer.SetProperty( VSEDITPROPID.VSEDITPROPID_ViewGeneral_ColorCategory, catGUID); } }  
```  
  
##  <a name="BKMK_DaytonaAndWebUI"></a> Daytona 및 웹 UI  
  
### 개요  
 "Daytona"은 Api, 도구 및 사용자가 HTML, CSS 및 JavaScript 다양 한 Visual Studio 또는 F12 같은 호스트에서에서 사용할 수 있는 플러그 인을 만들 수 있도록 하는 서비스의 집합. HTML, CSS 및 JavaScript로 작성 된 이식 가능한 구성 요소 및 선택적 호스트 관련 구성 요소는 플러그 인으로 구성 됩니다. 각 Daytona 호스트에는 고유한 암시적 또는 명시적으로 해당 환경에 고유한 표시 하기 위해 플러그 인을 준수 해야 UI 규칙 집합이 있을 수 있습니다. Visual Studio와 같은 일부 호스트 하면 최종 사용자가 하는 스타일 시트를 만들 때 호스트의 시각적 측면 정적으로 대상이 될 수 없습니다 "기본"테마를 변경 해야 합니다. 이 휴대용 플러그 인을 작성 하는 개발자에 게 문제를 제기 합니다. 이 항목에서는 웹 Daytona 호스트를 사용 하 여 제대로 테마 및 고대비 모두를 지원 하는 방식에서으로 Visual Studio에서 UI를 작성 하는 방법을 설명 합니다.  
  
### Daytona 테마 메커니즘  
 Daytona 런타임 UI 규칙을 추상화 하는 서비스 집합 및 호스트의 테마 기능을 제공 합니다. 이러한 서비스 플러그 인에서 호스팅되는 환경에 따라 사용자의 시각적 기대에 자동으로 부합 되는지 확인 합니다. 이 문제는 세 가지 기본 기능으로 제공 됩니다.  
  
1.  투명 하 게 플러그 인의 UI에 CSS 규칙의 집합을 적용 하 고 \(예를 들어 HTMLInputElement 및 HTMLButtonElement HTML 컨트롤의 기본 집합 스타일이 있는 런타임 주입 스타일 시트 \(plugin.css\)  
  
2.  테마 기반 하드 코딩 하는 대신 값을 사용 하 여 스타일 UI 요소에 사용할 수 있는 호스트에서 제공한 토큰 집합을  
  
    1.  CSS로 이러한 토큰에 액세스 하기 위한 선언적 구문  
  
    2.  JavaScript에서 테마 토큰을 프로그래밍 방식으로 액세스 하기 위한 API  
  
3.  테마 변경 알림  
  
#### 런타임 주입 스타일 시트  
 스타일을 삽입 하는 호스트와 Daytona 런타임 좌표 시트 테마의 플러그 인에는 표준 UI 요소를 자동으로입니다. 다음과 같은 개념에 대 한 스타일 지정은 다음과 같습니다.  
  
-   환경 글꼴  
  
-   배경색  
  
-   하이퍼링크  
  
-   양식 컨트롤 \(예: \< 선택 \>, \< 입력 \>, \< 단추 \>  
  
-   Tables  
  
-   머리글  
  
-   스크롤 막대  
  
 이 의미 하는 경우 UI 이루어져 표준 HTML UI 컨트롤을 추가 작업 없이 해야 필요 합니다 테마 변경에 제대로 응답 하 고 고대비를 지원 하도록 합니다.  
  
#### 사용자 지정 UI  
 거의 모든 복잡 한 경우에는 표준 HTML UI 컨트롤 플러그 인에 대 한 완벽 한 환경을 제공 하는 데 충분 한 없게 되 고 사용자 지정 UI를 도입 해야 합니다. 적절 한 글꼴 선택 및 색 사용을 지원 하기 위해 **테마 토큰** 아래에서 설명 하는 JavaScript API를 통해 CSS에서 선언적으로 또는 명령적으로 사용 해야 합니다. Daytona 런타임 하므로 플러그 인 로드 및 테마를 변경 해도 이러한 토큰을 사용 하는 스타일 시트를 업데이트 합니다.  
  
##### 테마 토큰  
 사용할 수 있는 두 표준 및 호스트별 테마 토큰이 있습니다. 표준 토큰은 호스트 주입 및 항상 사용 가능입니다. 가급적 표준 토큰을 사용 하는 것이 좋습니다. 표준 토큰은 모든 Daytona 호스트에서 제공 하 고 이러한 사용 플러그 인에 본질적으로 이식 가능성이 향상 합니다. 표준 토큰 집합이 변경 될 수만 새 토큰을 추가 해야 하 고 제거할 수 없음입니다. Visual Studio 2013 버전은 아래에서 설명 합니다.  
  
|토큰 이름|설명|  
|-----------|--------|  
|플러그 인 배경색|플러그 인에 대 한 기본 배경색|  
|플러그 인 색|플러그 인에 대 한 기본 전경색|  
|contextmenu 액티브 색 플러그 인|활성화 된 경우 상황에 맞는 메뉴에 대 한 기본 전경색 선택 \(포커스를 둔\)|  
|contextmenu 배경 색 플러그 인|상황에 맞는 메뉴에 대 한 기본 배경색|  
|플러그 인 contextmenu\-테두리 색|상황에 맞는 메뉴의 기본 테두리 색|  
|플러그 인 contextmenu 색|상황에 맞는 메뉴에 대 한 기본 전경색|  
|contextmenu 가리킨 항목 색 플러그 인|상황에 맞는 메뉴에 대 한 기본 전경색 배경|  
|플러그 인 contextmenu\-호버\-텍스트 색|상황에 맞는 메뉴에 대 한 기본 전경색 전경|  
|contextmenu 아이콘 확인란 플러그 인|상황에 맞는 메뉴에 대 한 기본 확인란 아이콘 색|  
|플러그 인 contextmenu\-비활성\-텍스트 색|활성화 되지 않은 상황에 맞는 메뉴에 대 한 기본 전경색 선택|  
|contextmenu 구분 기호 색 플러그 인|상황에 맞는 메뉴에 대 한 기본 구분 기호 색|  
|플러그 인 글꼴 패밀리|플러그 인에 사용할 기본 글꼴 패밀리|  
  
 Visual Studio에서 다음과 같은 플러그 인 글꼴 토큰 환경 글꼴 설정을 따릅니다.  
  
-   플러그 인 글꼴 크기  
  
-   플러그 인 글꼴 두께  
  
-   플러그 인\-강조\-배경색  
  
-   강조색 플러그 인  
  
-   비활성 색 플러그 인  
  
 HTMLElements \(하이퍼링크\) 스타일을 지정 하는 다음 플러그 인 링크 토큰이 사용 됩니다.  
  
-   플러그 인 링크 색  
  
-   플러그 인 링크\-활성 색  
  
-   플러그 인 링크\-가리킨 항목 색  
  
 Plugin.css 스타일 스크롤 막대가 지원 향상 시키기 위해 다음과 같은 토큰을 사용 하 여 기본적으로 \(특히, Visual Studio\)에서 다양 한 호스트에서 테마:  
  
-   스크롤 막대 화살표 색 플러그 인  
  
-   스크롤 막대 배경 색 플러그 인  
  
-   스크롤 막대 표면 색 플러그 인  
  
 \(콤보 상자 드롭다운\) HTMLSelectElement 스타일을 지정 하는 다음 플러그 인 선택 토큰이 사용 됩니다.  
  
-   플러그 인\-선택\-옵션\-배경색  
  
-   플러그 인 선택\-옵션 색  
  
-   plugin\-select\-option\-checked\-background\-color  
  
-   plugin\-select\-option\-checked\-border\-color  
  
-   plugin\-select\-option\-checked\-foreground\-color  
  
-   plugin\-select\-option\-hover\-background\-color  
  
-   plugin\-select\-option\-hover\-border\-color  
  
-   plugin\-select\-option\-hover\-foreground\-color  
  
-   플러그 인 선택\-테두리 색  
  
-   플러그 인 선택\-배경 색  
  
-   플러그 인 선택\-전경 색  
  
-   플러그 인\-선택\-호버\-배경색  
  
-   플러그 인\-선택\-\-테두리\-전경색  
  
-   플러그 인\-선택\-\-전경\-전경색  
  
-   플러그 인 테이블\-테두리 색  
  
-   플러그 인\-테이블\-헤더\-배경색  
  
-   테이블 머리글 색 플러그 인  
  
-   플러그 인 텍스트 상자\-테두리 색  
  
-   텍스트 상자의 배경 색 플러그 인  
  
-   플러그 인 텍스트 상자 색  
  
-   플러그 인\-textbox\-사용 안 함\-배경색  
  
-   플러그 인\-textbox\-사용 안 함\-테두리\-색  
  
-   텍스트 상자 사용 안 함 색 플러그 인  
  
 이러한 토큰에 사용할 *모든* 올바른 기본 테마 및 고대비 지원 하기 위해 다양 한 호스트 설정 했기 때문에 트리 뷰 및 테이블의 경우:  
  
-   플러그 인\-treeview\-콘텐츠\-배경색  
  
-   treeview 콘텐츠 색 플러그 인  
  
-   plugin\-treeview\-content\-inactive\-selected\-color  
  
-   plugin\-treeview\-content\-mouseover\-background\-color  
  
-   플러그 인\-treeview\-콘텐츠\-mouseover\-색  
  
-   plugin\-treeview\-content\-inactive\-selected\-color  
  
-   plugin\-treeview\-content\-selected\-background\-color  
  
-   plugin\-treeview\-content\-selected\-border\-color  
  
-   플러그 인\-treeview\-콘텐츠\-선택\-색  
  
##### 호스트 별로 토큰  
 토큰의 표준 집합을 지 원하는 것 외에도 호스트는 비표준 토큰을 제공할 수도 있습니다. Visual Studio 호스트 플러그 인의 매니페스트의 Visual Studio 관련 섹션에서 테마 토큰 별칭 지정을 허용 하 여이 수행 합니다. 예:  
  
```  
"vs": { "theme_token_aliases": { "diagnostics-host-border": { "category": "f8a8b2a5-dd35-43f6-a382-fd6a61325c22", "key_type": "BackgroundColor", "name": "Border" }, ... } }  
  
```  
  
 이 예제는 테마 토큰을 "진단\-호스트\-테두리" 라는 위에서 언급 한 표준 토큰을 동일 하 게 참조할 수 있는 소개 합니다. 범주, key\_type, 및 이름을 통해 색을 확인 하는데 사용 되는 **IVsFontAndColorStorage** 인터페이스입니다. 대부분의 경우에서 vscommon\\themes에 있는 XML 파일에서 \(범주, key\_type, 및 이름 정보\)와 함께 적절 한 색을 찾을 수는 있습니다. 패키지 구성 가능한 새로운 색을 소개 하는 경우이 동일한 메커니즘이 사용: 범주, key\_type, 및을 사용 하 여 원하는 색으로 이름과 일치 합니다. 플러그 인 작성자는 가능 하면 표준 토큰을 사용 하려고 하 고 호스트별 토큰 꼭 필요한 경우에 사용 해야 합니다.  
  
##### CSS에서 테마 토큰 사용  
 테마 토큰 구체적으로 서식이 지정 된 주석 구문을 통해 참조 됩니다. 토큰 구문 분석 중에 대 한 규칙:  
  
1.  주석 식 대괄호로 묶어야 합니다 \(\).  
  
2.  주석 내에서 아니라 식 외부에서 모든 공백 무시 됩니다.  
  
3.  주석 식을 대체 하는 속성을 직접 따라야 합니다.  
  
4.  식 내에 모든 선행 또는 후행 공백이 잘립니다.  
  
5.  식 내의 각 토큰 이름을 중괄호로 묶어야 합니다 \(예를 들어 **{글꼴 패밀리}** 및 **{단추\-전경색}**\). 그렇지 않으면 리터럴 값으로 처리 됩니다.  
  
 토큰 파서 CSS 값, 가정 하 고 어떻게 바뀝니다의 예는 다음과 같습니다는 **플러그 인 배경색** 토큰에는 값이 \#000 및 **플러그 인 글꼴 패밀리** 토큰에는 값이 "Verdana"로 지정 합니다.  
  
|작성 된 CSS|구문 분석 된 CSS|참고|  
|--------------|-----------------|--------|  
|`background-color: #fff; /*[{plugin-background-color}]*/`|`background-color: #000;`|기본값은 동적 호스트별 값으로 대체 됩니다.|  
|`background-color: #fff; /*   [{plugin-background-color}]   */`|`background-color: #000;`|식 외부에서 공백을 무시 됩니다.|  
|`background-color: #fff; /*[   {plugin-background-color}   ]*/`|`background-color: #000;`|식 내에서 선행 및 후행 공백은 잘립니다.|  
|`background-color: #fff; /*{plugin-background-color}*/`|`background-color: #fff;`|식은 대괄호를 포함 되지 하 고 따라서 주석을 무시 됩니다.|  
|`background-color: #fff; /*[plugin-background-color]*/`|`background-color: plugin-background-color;`|토큰을 중괄호로 묶인 되지 이며 따라서 리터럴 값으로 취급 됩니다.|  
|`/*[{plugin-background-color}]*/ background-color: #fff;`|`background-color: #fff;`|속성 값을 따르지 않는 주석과 따라서 무시 됩니다.|  
|`background-color: #fff; /*[{plugin-background-color}]*/`|`background-color: #fff;`|*위와 동일*|  
|`/*[{plugin-background-color}]*/ background-color: #fff;`|`background-color: #fff;`|*위와 동일*|  
|`font-family: Arial, sans-serif; /*[{plugin-font-family}, sans-serif]*/`|`font-family: Verdana, sans-serif;`|토큰이 바뀌고 리터럴 콘텐츠는 유지 관리 합니다.|  
|`background-image: linear-gradient(0% #000, 100% #ccc); /*[linear-gradient(0% #000, 100% {plugin-background-color})]*/`|`background-image: linear-gradient(0% #000, 100% #000);`|*위와 동일*|  
  
 CSS 파일에 테마 토큰에 포함 된 경우에 HTML 파일에서 링크 요소에 대해 데이터 플러그 인 테마 특성으로 표시 되어야 합니다. 예:  
  
```  
<link href="default.css" rel="stylesheet" data-plugin-theme="true" />  
```  
  
##### JavaScript에서 테마 토큰을 사용 하 여  
 사용자 지정 UI 테마가 적용 된 CSS에서 가능한 경우 생각 하는 동안 시나리오가 테마 값 토큰 프로그래밍 방식으로 액세스할 수 있어야 하는 경우. 예를 들어 사용자 지정 UI에서 CSS 스타일을 상속 하지 않습니다는 CanvasElement에 그려지는 또는 UI 요소의 동적으로 되는 경우 스타일 시트를 참조 하는 대신 만들어집니다. 시나리오를 사용 하 여 Daytona API를 사용 하 여 **Plugin.Theme.getValue**합니다. 이 함수에 토큰 이름을 지정 하면 호스트에서 제공한 테마 값을 반환 합니다.  
  
|테마가 지정 된 하지|테마가 지정 된|  
|-----------------|--------------|  
|`var surface = document.getElementById("surface").getContext("2d"); surface.fillStyle = "#ccc"; surface.fillRect(0, 0, 200, 200);`|`var surface = document.getElementById("surface").getContext("2d"); surface.fillStyle = ("plugin-background-color"); surface.fillRect(0, 0, 200, 200);`|  
|`var el = document.createElement("div"); el.style.backgroundColor = "#ccc";`|`var el = document.createElement("div"); el.style.backgroundColor = Plugin.Theme.getValue("plugin-background-color");`|  
  
 토큰은 JavaScript에서 사용 하는 경우**, 업데이트에 응답 하는 테마 변경 이벤트를 처리 해야 합니다**합니다. 이 필요 하지 않습니다 CSS에서 선언적으로 사용 하는 테마 토큰에 대 한 플러그 인을 담당 Daytona 런타임입니다. 테마 이벤트는 다음과 같은 방식으로 처리할 수 있습니다.  
  
|멤버 \(단일 처리기\)|DOM 이벤트 \(여러 처리기\)|  
|-------------------|------------------------|  
|`Plugin.Theme.onchange = function () { // re-draw dynamic UI here }`|`Plugin.Theme.addEventListener("change", function () { // re-draw dynamic UI here });`|  
  
 이 경우에 것 다시 호출 하는 매우 일반적인 **Plugin.Theme.getValue** 테마가 변경 될 때 변경 가능성이 테마 토큰의 값으로 이러한 처리기에 있습니다.  
  
##### 표준 토큰 매핑  
 표준 토큰 환경 및 셸 색에 매핑됩니다. 아래 목록에는 이러한 매핑에 이란의 버전을 제공 합니다.  
  
|토큰 이름|VS 매핑 \(EnvironmentColors\)|  
|-----------|---------------------------------|  
|플러그 인 색|ToolWindowTextColorKey|  
|플러그 인 배경색|ToolWindowBackgroundColorKey|  
|플러그 인 링크 색|ControlLinkTextColorKey|  
|플러그 인 링크\-가리킨 항목 색|ControlLinkTextHoverColorKey|  
|플러그 인 링크\-활성 색|ControlLinkTextPressedColorKey|  
|강조색 플러그 인|HighlightTextColorKey|  
|플러그 인\-강조\-배경색|HighlightColorKey|  
|플러그 인\-테이블\-헤더\-배경색|GridHeadingBackgroundColorKey|  
|테이블 머리글 색 플러그 인|GridHeadingTextColorKey|  
|플러그 인 테이블\-테두리 색|GridLineColorKey|  
|플러그 인\-단추\-배경색|ButtonFaceColorKey|  
|플러그 인\-단추\-호버\-배경색|ButtonHighlightColorKey|  
|플러그 인 단추 색|ButtonTextColorKey|  
|플러그 인 단추\-테두리 색|ButtonBorderColorKey|  
  
##### 테마 변경  
 Visual Studio 호스트 트리거 플러그인 테마 변경 내용을 때 최종 사용자가 다음 설정을 변경:  
  
 **색 테마:**  
  
 ![Color theme changes](../../extensibility/ux-guidelines/media/0305-a_colortheme.png "0305\-a\_ColorTheme")  
  
 **환경 테마:**  
  
 ![Environment theme changes](../../extensibility/ux-guidelines/media/0305-b_environmenttheme.png "0305\-b\_EnvironmentTheme")  
  
 **운영 체제 테마** \(경우에 변경 하 고 고대비에서\).  
  
 ![OS theme changes](../../extensibility/ux-guidelines/media/0305-c_ostheme.png "0305\-c\_OSTheme")