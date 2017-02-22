---
title: "글꼴 및 Visual Studio에 대 한 서식 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c3c3df69-83b4-4fd0-b5b1-e18c33f39376
caps.latest.revision: 5
caps.handback.revision: 5
ms.author: "gregvanl"
manager: "ghogen"
---
# 글꼴 및 Visual Studio에 대 한 서식 지정
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

##  <a name="BKMK_TheEnvironmentFont"></a> 환경 글꼴  
 Visual Studio 내에서 모든 글꼴을 사용자 지정에 대 한 사용자에 게 노출 되어야 합니다. 통해 주로 이렇게는 **글꼴 및 색** 페이지에 **도구 \> 옵션** 대화 합니다. 글꼴 설정의 세 가지 주요 범주는:  
  
-   **환경 글꼴** \-대화 상자, 메뉴, 도구 창 및 문서 창을 포함 하 여 모든 인터페이스 요소에 사용 되는 IDE \(통합된 개발 환경\)에 대 한 기본 글꼴입니다. 기본적으로 환경 글꼴은 현재 버전의 Windows 9 포인트 Segoe UI로 표시 되는 시스템 글꼴에 연결 됩니다. 모든 인터페이스 요소에 대 한 글꼴을 사용 하 여 IDE 전체에서 일관 된 글꼴 모양이 표시 되도록 하는 데 도움이 됩니다.  
  
-   **텍스트 편집기** \-페이지의 요소는 코드 및 기타 표면 텍스트 기반 편집기 사용자 지정할 수 있습니다 텍스트 편집기에서 **도구 \> 옵션**합니다.  
  
-   **특정 컬렉션** \-자체 설정 페이지에서 해당 인터페이스 요소의 사용자 지정 글꼴 관련 디자인에 노출 될 수 있습니다 제공 하는 디자이너 창 화면 **도구 \> 옵션**합니다.  
  
### 편집기 글꼴 사용자 지정 및 크기 조정  
 사용자가 자주 됩니다를 확대 하거나 크기 및\/또는 독립적인 일반 사용자 인터페이스의 기본 설정에 따라 편집기에서 텍스트의 색을 확대\/축소 합니다. 환경 글꼴 내에서 또는 편집기\/designer의 일부로 표시 될 수 있는 요소를 사용할 경우, 이므로 이러한 글꼴 분류 중 하나가 변경 되는 경우 예상 되는 동작을 확인 해야 합니다.  
  
 일부가 아니라는 편집기에 표시 되는 UI 요소를 만들 때의 *콘텐츠*, 예측 가능한 방식으로 크기가 조정 요소 환경 글꼴 및 텍스트 글꼴이 아닌를 사용 해야 합니다.  
  
1.  텍스트 편집기에서 코드에 대 한 코드 텍스트 글꼴 설정을 함께 크기 조정 하 고 편집기 텍스트의 확대\/축소 수준에 응답 합니다.  
  
2.  환경 글꼴 설정을 연결 해야 하 고 환경에서 모든 전역 변화에 대응 하는 인터페이스의 다른 모든 요소입니다. 이 포함 하지만에 제한 되지 않습니다.  
  
    -   상황에 맞는 메뉴에는 텍스트  
  
    -   편집기 장식 전구 메뉴 텍스트를 빠른 등의 텍스트 편집기 창에서 찾아서 창으로 이동  
  
    -   파일에서 찾기 또는 리팩터링과 같은 대화 상자, 레이블 텍스트  
  
### 환경 글꼴에 액세스  
 기본 모드 또는 WinForms 코드 환경 글꼴 메서드를 호출 하 여 액세스할 수 있습니다 **IUIHostLocale::GetDialogFont** 후 SID\_SUIHostLocale 서비스에서 인터페이스를 쿼리 합니다.  
  
 에 대 한 WPF Windows Presentation Foundation \(\), 셸에서 대화 상자 창 클래스를 파생 **DialogWindow** WPF의 대신 클래스 **창** 클래스입니다.  
  
 XAML에서 코드는 다음과 같습니다.  
  
```  
<ui:DialogWindow x:Class"MyNameSpace.MyWindow" xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xmlns:s="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:ui="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.11.0" ShowInTaskbar="False" WindowStartupLocation="CenterOwner" Title="My Dialog"> </ui:DialogWindow> code behind: internal partial class WebConfigModificationWindow : DialogWindow { }  
  
```  
  
 \(대체 `Microsoft.VisualStudio.Shell.11.0` MPF dll의 현재 버전과.\)  
  
 호출 하 여 대화 상자를 표시 하려면 "**ShowModal\(\)**"를 통해 클래스에 **ShowDialog\(\)**합니다.**ShowModal\(\)** 셸에서 모달 상태를 올바른 설정으로, 부모 창에는 대화 상자 가운데 맞춤 합니다.  
  
 코드는 다음과 같습니다.  
  
```  
MyWindow window = new MyWindow(); window.ShowModal()  
  
```  
  
 **ShowModal** 부울 값을 반환? \(null 허용 부울\)와 **DialogResult**, 필요한 경우 사용할 수 있습니다. 반환 값은 true와 대화 상자를 닫은 경우 **확인**합니다.  
  
 자체에 작업을 하 고 호스트 되는 몇 가지 WPF UI를 표시 하는 경우 **HwndSource**, 예: 팝업 창 또는 Win32\/WinForms 부모 창 창의 자식 창 WPF 설정 해야 합니다는 **FontFamily** 및 **FontSize** WPF 요소의 루트 요소에 있습니다. 주 창에서 속성을 설정 하는 셸 수 있지만 HWND를 지나서 상속 되지 않습니다. 셸에서 속성을 바인딩할 수, 다음과 같은 리소스를 제공 합니다.  
  
```  
<Setter property="FontFamily" Value="{DynamicResource VsFont.EnvironmentFontFamily}" /> <Setter property="FontSize" Value="{DynamicResource VsFont.EnvironmentFontSize}" />  
  
```  
  
###  <a name="BKMK_Formatting"></a> 서식 \(크기 조정\/굵은\) 참조  
 일부 대화 상자에는 특정 텍스트를 굵게 표시 또는 이외의 환경 글꼴 크기를 요구 합니다. 이전에 환경 글꼴 보다 큰 글꼴 "환경 글꼴 \+ 2"로 코딩 또는 유사한 되었습니다. 제공 된 코드 조각을 사용 하 여 높은 DPI 모니터를 지원 하 고 올바른 크기와 무게 \(예: Light 또는 Semilight\) 표시 텍스트 항상 표시 되는지 확인 합니다.  
  
> **참고: 서식을 적용 하기 전에 확인의 지침을 따르는 [텍스트 스타일](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle)합니다.**  
  
 환경 글꼴의 크기를 조정 하는 TextBlock 또는 레이블 표시 된 대로의 스타일을 설정 합니다. 이러한 코드 조각의 제대로 사용 각는 적절 한 크기 및 무게 변형을 포함 하 여 올바른 글꼴을 생성 합니다.  
  
 여기서 "vsui"은 Microsoft.VisualStudio.Shell 네임 스페이스에 대 한 참조입니다.  
  
```  
xmlns:vsui="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"  
  
```  
  
#### 375% 환경 글꼴 \+ Light  
 **으로 나타납니다:** 34 pt Segoe UI Light  
  
 **삼아:** \(드문 경우\) 고유한 브랜드 UI, 시작 페이지에서와 같이  
  
 **프로시저 코드:** 여기서 "textBlock"은 이전에 정의 된 TextBlock 하 고 "label" 이전에 정의 된 레이블이 사용 됩니다.  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty, VsResourceKeys.TextBlockEnvironment375PercentFontSizeStyleKey); label.SetResourceReference(Label.StyleProperty, VsResourceKeys.LabelEnvironment375PercentFontSizeStyleKey);  
  
```  
  
 **XAML:** 같이 TextBlock 또는 레이블 스타일을 설정 합니다.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment375PercentFontSizeStyleKey}}">TextBlock: 375 Percent Scaling</TextBlock> <Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment375PercentFontSizeStyleKey}}">Label: 375 Percent Scaling</Label>  
  
```  
  
#### 310% 환경 글꼴 \+ Light  
 **으로 나타납니다:** 28 pt Segoe UI Light  
  
 **삼아:** 큰 서명 대화 상자 제목, 주 보고서에 제목  
  
 **프로시저 코드:** 여기서 "textBlock"은 이전에 정의 된 TextBlock 하 고 "label" 이전에 정의 된 레이블이 사용 됩니다.  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty, VsResourceKeys.TextBlockEnvironment310PercentFontSizeStyleKey); label.SetResourceReference(Label.StyleProperty, VsResourceKeys.LabelEnvironment310PercentFontSizeStyleKey);  
  
```  
  
 **XAML:** 같이 TextBlock 또는 레이블 스타일을 설정 합니다.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment310PercentFontSizeStyleKey}}">TextBlock: 310 Percent Scaling</TextBlock> <Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment310PercentFontSizeStyleKey}}">Label: 310 Percent Scaling</Label>  
  
```  
  
#### 200% 환경 글꼴 \+ Semilight  
 **으로 나타납니다:** 18 포인트 Segoe UI Semilight  
  
 **삼아:** 부제목, 중소 규모 대화 상자에서 제목  
  
 **프로시저 코드:** 여기서 "textBlock"은 이전에 정의 된 TextBlock 하 고 "label" 이전에 정의 된 레이블이 사용 됩니다.  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty, VsResourceKeys.TextBlockEnvironment200PercentFontSizeStyleKey); label.SetResourceReference(Label.StyleProperty, VsResourceKeys.LabelEnvironment200PercentFontSizeStyleKey);  
  
```  
  
 **XAML:** 같이 TextBlock 또는 레이블 스타일을 설정 합니다.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment200PercentFontSizeStyleKey}}">TextBlock: 200 Percent Scaling</TextBlock> <Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment200PercentFontSizeStyleKey}}">Label: 200 Percent Scaling</Label>  
  
```  
  
#### 155% 환경 글꼴  
 **으로 나타납니다:** 14pt Segoe UI  
  
 **삼아:** UI 또는 보고서를 효율적으로 문서에서 섹션 제목  
  
 **프로시저 코드:** 여기서 "textBlock"은 이전에 정의 된 TextBlock 하 고 "label" 이전에 정의 된 레이블이 사용 됩니다.  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty, VsResourceKeys.TextBlockEnvironment155PercentFontSizeStyleKey); label.SetResourceReference(Label.StyleProperty, VsResourceKeys.LabelEnvironment155PercentFontSizeStyleKey);  
  
```  
  
 **XAML:** 같이 TextBlock 또는 레이블 스타일을 설정 합니다.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment155PercentFontSizeStyleKey}}">TextBlock: 155 Percent Scaling</TextBlock> <Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment155PercentFontSizeStyleKey}}">Label: 155 Percent Scaling</Label>  
  
```  
  
#### 133% 환경 글꼴  
 **으로 나타납니다:** 12 포인트 Segoe UI  
  
 **삼아:** 서명 대화 상자 및 문서에 더 작은 부제목 UI를 효율적으로  
  
 **프로시저 코드:** 여기서 "textBlock"은 이전에 정의 된 TextBlock 하 고 "label" 이전에 정의 된 레이블이 사용 됩니다.  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty, VsResourceKeys.TextBlockEnvironment133PercentFontSizeStyleKey); label.SetResourceReference(Label.StyleProperty, VsResourceKeys.LabelEnvironment133PercentFontSizeStyleKey);  
  
```  
  
 **XAML:** 같이 TextBlock 또는 레이블 스타일을 설정 합니다.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment133PercentFontSizeStyleKey}}">TextBlock: 133 Percent Scaling</TextBlock> <Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment133PercentFontSizeStyleKey}}">Label: 133 Percent Scaling</Label>  
  
```  
  
#### 122% 환경 글꼴  
 **으로 나타납니다:** 11 pt Segoe UI  
  
 **삼아:** 서명 대화 상자에서 머리글 섹션, 세로 탭 탐색 트리 뷰에서 노드를 상위  
  
 **프로시저 코드:** 여기서 "textBlock"은 이전에 정의 된 TextBlock 하 고 "label" 이전에 정의 된 레이블이 사용 됩니다.  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty, VsResourceKeys.TextBlockEnvironment122PercentFontSizeStyleKey); label.SetResourceReference(Label.StyleProperty, VsResourceKeys.LabelEnvironment122PercentFontSizeStyleKey);  
  
```  
  
 **XAML:** 같이 TextBlock 또는 레이블 스타일을 설정 합니다.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment122PercentFontSizeStyleKey}}">TextBlock: 122 Percent Scaling</TextBlock> <Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment122PercentFontSizeStyleKey}}">Label: 122 Percent Scaling</Label>  
  
```  
  
#### 환경 글꼴 \+ 굵게 표시  
 **으로 나타납니다:** 굵게 표시 된 9 포인트 Segoe UI  
  
 **삼아:** 레이블과 부제목 서명 대화 상자, 보고서 및 문서에 잘 UI  
  
 **프로시저 코드:** 여기서 "textBlock"은 이전에 정의 된 TextBlock 하 고 "label" 이전에 정의 된 레이블이 사용 됩니다.  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty, VsResourceKeys.TextBlockEnvironmentBoldStyleKey); label.SetResourceReference(Label.StyleProperty, VsResourceKeys.LabelEnvironmentBoldStyleKey);  
  
```  
  
 **XAML:** 같이 TextBlock 또는 레이블 스타일을 설정 합니다.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironmentBoldStyleKey}}"> Bold TextBlock</TextBlock> <Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironmentBoldStyleKey}}"> Bold Label</Label>  
  
```  
  
### 지역화할 수 있는 스타일  
 경우에 따라 지역화 담당자가 굵은 동아시아 언어에 대 한 텍스트에서 제거 하는 등의 다른 로캘에 대 한 글꼴 스타일을 수정 해야 합니다. 글꼴 스타일의 지역화를 가능 하 게 하려면 해당 스타일.resx 파일 이어야 합니다. 이 작업을 수행 하 고 여전히 Visual Studio 폼 디자이너에서 글꼴 스타일을 편집 하는 최상의 방법은 명시적으로 디자인 타임에 글꼴 스타일을 설정 하는 것입니다. 이 전체 font 개체를 만듭니다 부모 글꼴의 상속을 해제 하는 것 처럼 보일 수 있지만 글꼴을 설정 하는 FontStyle 속성만 사용 됩니다.  
  
 대화 상자 폼을 연결 하는 솔루션은 **FontChanged** 이벤트입니다. 에 **FontChanged** 이벤트를 모든 컨트롤을 설명 하 고 해당 글꼴 설정 되어 있는지 확인 합니다. 이 속성을 설정 하는 경우 폼의 글꼴 및 컨트롤의 이전 글꼴 스타일에 따라 새 글꼴을 변경 합니다. 이 코드에서는 예제가입니다.  
  
```  
private void Form1_FontChanged(object sender, System.EventArgs e) { SetFontStyles(); } /// <summary> /// SetFontStyles - This function will iterate all controls on a page /// and recreate their font with the desired fontstyle. /// It should be called in the OnFontChanged handler (and also in the constructor /// in case the IUIService is not available so OnFontChange doesn't fire). /// This way, when the VS shell font is given to us the controls that have /// a different style for the font (bolded for example) will recreate their font /// and use the VS shell font but with a style variation (bolded ...). /// </summary> protected void SetFontStyles() { SetFontStyles(this, this, this.Font); } protected static void SetFontStyles(Control topControl, Control parent, Font referenceFont) { foreach(Control c in parent.Controls) { if (c.Controls != null && c.Controls.Count > 0) { SetFontStyles(topControl, c, referenceFont); } if (c.Font != topControl.Font) { c.Font = new Font(referenceFont, c.Font.Style); } } }  
```  
  
 이 코드를 사용 하는 폼의 글꼴 업데이트 되 면 컨트롤의 글꼴을 업데이트 합니다도 보장 합니다. 이 메서드는 대화의 인스턴스를 가져오려면 실패할 수 있으므로 폼의 생성자에서 호출도 해야 **IUIService** 및 **FontChanged** 이벤트는 발생 하지 않습니다. 후크 **FontChanged** 대화 상자 대화 상자가 이미 열려 있는 경우에 새 글꼴을 동적으로 선택할 수 있습니다.  
  
### 환경 글꼴 테스트  
 을 보장 하기 위해 UI 환경 글꼴을 사용 하는 크기 설정을 열고 **도구 \> 옵션 \> 환경 \> 글꼴 및 색** 아래에서 "환경 글꼴"를 선택 하 고는 "설정 표시:" 드롭다운 메뉴.  
  
 ![Fonts and Colors page in Tools &#62; Options dialog](../../extensibility/ux-guidelines/media/0201-a_optionsfonts.png "0201\-a\_OptionsFonts")  
  
 **글꼴 및 색 설정을 도구에서 \> 옵션 대화 상자**  
  
 기본값 보다 전혀 다른 결과가 발생 하는 글꼴을 설정 합니다. 를 하 게 확실 한는 UI를 업데이트 하지 않습니다 \(예: "Times New Roman"\) 돌출 된 글꼴을 선택 하 고 매우 큰 크기를 설정 합니다. 그런 다음 환경을 반영 하기 위해 UI를 테스트 합니다. 라이선스 대화 상자를 사용 하는 예제는 다음과 같습니다.  
  
 ![Example of dialog not using the environment font](../../extensibility/ux-guidelines/media/0201-b_wrongfontdialog.png "0201\-b\_WrongFontDialog")  
  
 **환경 글꼴을 고려 하지 않는 UI 텍스트의 예**  
  
 이 경우 "사용자 정보" 및 "제품 정보" 글꼴을 유지 하지 됩니다. 일부 경우에는 명시적으로 디자인 선택이 될 수 있습니다이 있지만 명시적 글꼴 검토 사양의 일부로 지정 하지 않으면 버그 수 있습니다.  
  
 글꼴을 다시 설정 하려면 클릭 "기본값 사용"에서 **도구 \> 옵션 \> 환경 \> 글꼴 및 색**합니다.  
  
##  <a name="BKMK_TextStyle"></a> 텍스트 스타일  
 텍스트 스타일 글꼴 크기, 두께 및 대\/소문자를 가리킵니다. 구현 지침에 대 한 참조 [환경 글꼴](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont)합니다.  
  
### 텍스트 대\/소문자  
  
#### 모두 대문자  
 제목 또는 레이블을 Visual Studio에서 모두 대문자를 사용 하지 마십시오.  
  
#### 모든 소문자  
 사용 하지 마십시오 모두 소문자 제목이 나 Visual Studio에서 레이블의.  
  
#### 문장 및 제목 대\/소문자  
 Visual Studio의 텍스트는 대문자로 또는 문장 경우 상황에 따라 사용 해야 합니다.  
  
|에 대 한 제목 대\/소문자를 사용 합니다.|사용에 대 한 문장 사례:|  
|------------------------------|--------------------|  
|대화 상자 제목|레이블|  
|그룹 상자|확인란|  
|메뉴 항목|라디오 단추|  
|상황에 맞는 메뉴 항목|목록 상자 항목|  
|단추|상태 표시줄|  
|테이블 레이블||  
|열 머리글||  
|도구 설명||  
  
##### 제목 대\/소문자  
 단어의 첫은 대부분 또는 모든 구 내에서 단어의 첫 번째 문자는 대문자로 시작 하는 스타일입니다. Visual Studio에서 단어의 첫 비롯 한 여러 항목에 사용 됩니다.  
  
-   **도구 설명 합니다.** 예: "미리 보기 선택한 항목"  
  
-   **열 머리글입니다.** 예: "시스템 응답"  
  
-   **메뉴 항목입니다.** 예: "모두 저장"  
  
 제목 대\/소문자를 사용할 때는 이러한은 단어를 대문자로 표시 하는 시기 및 소문자 상태로 유지 하는 시기에 대 한 지침입니다.  
  
|대문자|설명 및 예|  
|---------|------------|  
|모든 명사||  
|모든 동사|"Is" 및 다른 형태의 "에 게"를 포함 하 여|  
|모든 부사|"보다" 및 ""를 포함 하 여|  
|모든 형용사|"This" 및 "는"를 포함 하 여|  
|모든 대명사|소유격이 포함 하 여 "의" 뿐 이므로"," 대명사의 축약 된 것 "it" 및 동사 "is"|  
|문장 요소에 관계 없이 첫 번째 및 마지막 단어||  
|동사 구의 일부인 전치사|"모든 Windows closing" 또는 "시스템 종료"|  
|머리 글자어의 모든 문자|HTML, XML, URL, IDE, RGB|  
|명사 또는 형용사 적절 한 경우 또는 동일한 가중치 단어 경우 복합 단어의 두 번째 단어|상호 참조, 전 Microsoft 소프트웨어의 경우 읽기\/쓰기 액세스, 실행 시간|  
  
|소문자|예제|  
|---------|--------|  
|다른 음성 부분 인지는 분사 첫 번째 단어를 수정 하는 경우에 복합 단어의 두 번째 단어|오프 라인 사용 방법|  
|문서 제목에 첫 번째 단어 하나가 아닌 경우|a는,|  
|접속사 조정|하지만, 하거나, 또는|  
|동사 구 외부에서 4 개 이하의 문자의 단어로 전치사|대상으로 부족의 상단에서|  
|"대상"에 무한 구를 사용 하는 경우|"하드 디스크를 포맷 하는 방법"|  
  
##### 문장의 첫 글자  
 문장의 첫 글자 문장의 첫 번째 단어만 대문자로 시작, 모든 명사와 대명사과 함께 쓰기를 위한 표준 대\/소문자 메서드는 "I"입니다. 일반적으로 문장의 첫 글자 전세계 고객에 게 특히 때 콘텐츠 변환할 컴퓨터에서 읽기 쉽습니다. 사용에 대 한 문장 사례:  
  
1.  **상태 표시줄 메시지입니다.** 이들 간단 간단히 말해 되며만 상태 정보를 제공 합니다. 예: "프로젝트 파일 로드"  
  
2.  **다른 모든 UI 요소**, 레이블, 확인란, 라디오 단추 및 목록 상자 항목입니다. 예: "모든 항목 선택 목록에"  
  
### 텍스트 서식 지정  
 기본 텍스트 서식을 Visual Studio 2013에 의해 제어 되는 [환경 글꼴](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont)합니다. 이 서비스를 사용 하면 IDE \(통합된 개발 환경\), 전체에서 일관 된 글꼴 모양 및 사용자를 위한 일관 된 환경을 보장 하기 위해 사용 해야 합니다.  
  
 Visual Studio 글꼴 서비스에서 사용 되는 기본 크기는 Windows에서 제공 하 고 9 pt로 나타납니다.  
  
 환경 글꼴에 서식을 적용할 수 있습니다. 이 항목에서는 방법과 위치 스타일을 사용 하도록 합니다. 구현 정보에 대 한 참조를 [환경 글꼴](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont)합니다.  
  
#### 굵게 표시 된 텍스트  
 굵은 텍스트 Visual Studio에서 필요한 경우에 사용 됩니다 하 고을 위해 예약 해야 합니다.  
  
-   마법사의 질문 레이블  
  
-   솔루션 탐색기에서 현재 프로젝트를 지정합니다.  
  
-   속성 도구 창에서 재정의 된 값  
  
-   Visual Basic 편집기 드롭다운 목록에서 특정 이벤트  
  
-   웹 페이지에 대 한 문서 개요의 서버에서 생성 된 콘텐츠  
  
-   복잡 한 대화 또는 디자이너 UI의 섹션 헤더  
  
#### 기울임꼴  
 Visual Studio에서 기울임꼴 또는 굵게 표시 된 기울임꼴 텍스트를 사용 하지 않습니다.  
  
#### 색  
  
-   파랑은 하이퍼링크 \(탐색 및 명령 실행\)에 대 한 예약 및 방향에 대해 사용 하지 말아야 합니다.  
  
-   이러한 목적을 위해 큰 머리글 \(환경 글꼴 x 155% 이상\)를 색칠 할 수 있습니다.  
  
    -   눈에 띄는 서명 Visual Studio UI를 제공 하기  
  
    -   특정 영역을 강조할  
  
    -   진한 회색\/검은색 환경 표준 텍스트 색상에서 제공 합니다.  
  
-   머리글의 색은 기존 Visual Studio 브랜드 색, 주 자주색 주로 \#FF68217A 활용 해야 합니다.  
  
-   머리글의 색을 사용할 때 따라야는 [Windows 색 지침](https://msdn.microsoft.com/en-us/library/dn742482.aspx), 비율 및 기타 내게 필요한 옵션 고려 사항을 포함 합니다.  
  
### 글꼴 크기  
 Visual Studio UI 디자인 자세한 공백이 있는 밝은 모양을 갖추고 있습니다. 가능한 경우, chrome 및 제목 표시줄 감소 되거나 제거 된 합니다. 정보 밀도 Visual Studio에서 요구 사항, 입력 체계 개방성 줄 간격 및 글꼴 크기 및 중량의 변형에 중점을 두어 중요 한 것으로 계속 됩니다.  
  
 아래 테이블에는 디자인 세부 정보 및 Visual Studio에서 사용 되는 디스플레이 글꼴에 대 한 시각적인 예가 포함 되어 있습니다. 일부 디스플레이 글꼴 변형 크기와 Semilight 광원, 모양은에 코딩 등의 가중치는 합니다.  
  
 모든 디스플레이에서 글꼴을 찾을 수 있습니다에 대 한 구현 코드 조각을 [서식 (크기 조정/굵은) 참조](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_Formatting)합니다.  
  
#### 375% 환경 글꼴 \+ Light  
  
|||  
|-|-|  
|**사용:** 드물게 발생 합니다. 고유한 브랜드 UI만 합니다.<br /><br /> **수행 합니다.**<br /><br /> -   문장의 첫 글자를 사용 하 여<br />-   항상 단순 사용<br /><br /> **하지 않습니다.**<br /><br /> -   시작 페이지와 같은 UI 서명 이외의 UI에 대 한 사용<br />-   굵게, 기울임꼴 또는 굵게 기울임꼴<br />-   본문 텍스트에 대 한 사용<br />-   도구 창에서 사용 하 여|**으로 나타납니다:** 34 pt Segoe UI Light<br /><br /> **예를 보여 줍니다.**<br /><br /> *현재 사용되지 않습니다. 시작 페이지에서 사용할 수 있습니다.*|  
  
#### 310% 환경 글꼴 \+ Light  
  
|||  
|-|-|  
|**사용법:**<br /><br /> -   서명 대화 상자에서 더 큰 제목<br />-   주 보고서 제목<br /><br /> **수행 합니다.**<br /><br /> -   문장의 첫 글자를 사용 하 여<br />-   항상 단순 사용<br /><br /> **하지 않습니다.**<br /><br /> -   시작 페이지와 같은 UI 서명 이외의 UI에 대 한 사용<br />-   굵게, 기울임꼴 또는 굵게 기울임꼴<br />-   본문 텍스트에 대 한 사용<br />-   도구 창에서 사용 하 여|**으로 나타납니다:** 28 pt Segoe UI Light<br /><br /> **예를 보여 줍니다.**<br /><br /> ![Example of 310% Environment font &#43; Light heading](../../extensibility/ux-guidelines/media/0202-a_ef310.png "0202\-a\_EF310")|  
  
#### 200% 환경 글꼴 \+ Semilight  
  
|||  
|-|-|  
|**사용법:**<br /><br /> -   부제목<br />-   중소 규모 대화 상자에서 제목<br /><br /> **수행 합니다.**<br /><br /> -   문장의 첫 글자를 사용 하 여<br />-   항상 Semilight 가중치를 사용 합니다.<br /><br /> **하지 않습니다.**<br /><br /> -   굵게, 기울임꼴 또는 굵게 기울임꼴<br />-   본문 텍스트에 대 한 사용<br />-   도구 창에서 사용 하 여|**으로 나타납니다:** 18 포인트 Segoe UI Semillight<br /><br /> **예를 보여 줍니다.**<br /><br /> ![Example of 200% Environment font &#43; Semilight](../../extensibility/ux-guidelines/media/0202-b_ef200.png "0202\-b\_EF200")|  
  
#### 155% 환경 글꼴  
  
|||  
|-|-|  
|**사용법:**<br /><br /> -   UI를 효율적으로 문서에서 섹션 제목<br />-   Reports<br /><br /> **않습니다:** 문장의 첫 글자를 사용 하 여<br /><br /> **하지 않습니다.**<br /><br /> -   굵게, 기울임꼴 또는 굵게 기울임꼴<br />-   본문 텍스트에 대 한 사용<br />-   Visual Studio를 제어 하는 표준에 사용 하 여<br />-   도구 창에서 사용 하 여|**으로 나타납니다:** 14pt Segoe UI<br /><br /> **예를 보여 줍니다.**<br /><br /> ![Example of 155% Environment font heading](../../extensibility/ux-guidelines/media/0202-c_ef155.png "0202\-c\_EF155")|  
  
#### 133% 환경 글꼴  
  
|||  
|-|-|  
|**사용법:**<br /><br /> -   서명 대화 상자에서 더 작은 부제목<br />-   문서에서 더 작은 부제목 UI를 효율적으로<br /><br /> **않습니다:** 문장의 첫 글자를 사용 하 여<br /><br /> **하지 않습니다.**<br /><br /> -   굵게, 기울임꼴 또는 굵게 기울임꼴<br />-   본문 텍스트에 대 한 사용<br />-   Visual Studio를 제어 하는 표준에 사용 하 여<br />-   도구 창에서 사용 하 여|**으로 나타납니다:** 12 포인트 Segoe UI<br /><br /> **예를 보여 줍니다.**<br /><br /> ![Example of 133% Environment font heading](../../extensibility/ux-guidelines/media/0202-d_ef133.png "0202\-d\_EF133")|  
  
#### 122% 환경 글꼴  
  
|||  
|-|-|  
|**사용법:**<br /><br /> -   서명 대화 상자에서 섹션 제목<br />-   트리 뷰의 최상위 노드<br />-   세로 탭 탐색<br /><br /> **않습니다:** 문장의 첫 글자를 사용 하 여<br /><br /> **하지 않습니다.**<br /><br /> -   굵게, 기울임꼴 또는 굵게 기울임꼴<br />-   본문 텍스트에 대 한 사용<br />-   Visual Studio를 제어 하는 표준에 사용 하 여<br />-   도구 창에서 사용 하 여|**으로 나타납니다:** 11 pt Segoe UI<br /><br /> **예를 보여 줍니다.**<br /><br /> ![Example of 122% Environment font heading](../../extensibility/ux-guidelines/media/0202-e_ef122.png "0202\-e\_EF122")|  
  
#### 환경 글꼴 \+ 굵게 표시  
  
|||  
|-|-|  
|**사용법:**<br /><br /> -   레이블 및 부제목 서명 대화 상자에서<br />-   레이블 및 보고서에 부제목<br />-   레이블 및 문서에 부제목 UI를 효율적으로<br /><br /> **수행 합니다.**<br /><br /> -   문장의 첫 글자를 사용 하 여<br />-   굵게 표시 된 가중치를 사용 하 여<br /><br /> **하지 않습니다.**<br /><br /> -   기울임꼴 또는 굵게 기울임꼴<br />-   본문 텍스트에 대 한 사용<br />-   Visual Studio를 제어 하는 표준에 사용 하 여<br />-   도구 창에서 사용 하 여|**으로 나타납니다:** 굵게 표시 된 9 포인트 Segoe UI<br /><br /> **예를 보여 줍니다.**<br /><br /> ![Example of Environment font &#43; Bold heading](../../extensibility/ux-guidelines/media/0202-f_efb.png "0202\-f\_EFB")|  
  
#### 환경 글꼴  
  
|||  
|-|-|  
|**사용:** 다른 모든 텍스트<br /><br /> **않습니다:** 문장의 첫 글자를 사용 하 여<br /><br /> **하지 않습니다:** 기울임꼴 또는 굵게 기울임꼴|**으로 나타납니다:** 9 포인트 Segoe UI<br /><br /> **예를 보여 줍니다.**<br /><br /> ![Example of Environment font](../../extensibility/ux-guidelines/media/0202-g_ef.png "0202\-g\_EF")|  
  
### 안쪽 여백 및 간격  
 머리글에는 적절 한 강조 부여할 주위의 공간이 필요 합니다. 이 공간은 포인트 크기 이며 다른 어떤는 머리글, 단락 구분선 또는 환경 글꼴의 텍스트 줄과 같이 근처에 따라 달라 집니다.  
  
-   자체적으로 제목에 대 한 이상적인 안쪽 여백을 대문자 문자 높이 공간의 90% 여야 합니다. 예를 들어, 28 pt Segoe UI Light 제목 26 포인트의 대문자 높이 있으며 23 pt 또는 약 31 픽셀의 안쪽 여백을 약 해야 합니다.  
  
-   제목 주위에 최소 공간에는 대문자 문자 높이의 50% 이어야 합니다. 규칙 또는 기타 밀접 하 게 맞춤 요소 제목과 함께 더 적은 공간을 사용할 수 있습니다.  
  
-   환경 글꼴 텍스트를 굵게 표시 된 기본 줄 높이 간격 및 안쪽 여백 따라야 합니다.  
  
## 참고 항목  
 [MSDN: 글꼴 \(Windows\)](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742483\(v=vs.85\).aspx)   
 [MSDN: 사용자 인터페이스 텍스트 \(Windows\)](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx)