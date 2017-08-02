---
title: "글꼴 및 Visual Studio에 대 한 서식을 | Microsoft Docs"
ms.custom: 
ms.date: 04/26/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3c3df69-83b4-4fd0-b5b1-e18c33f39376
caps.latest.revision: 5
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9524ecc3cadef58821fba857de8e82e59eea9b43
ms.openlocfilehash: c55c135034f5b3b2dd09ccf94e22e56e8f04797e
ms.contentlocale: ko-kr
ms.lasthandoff: 05/04/2017

---
# <a name="fonts-and-formatting-for-visual-studio"></a>글꼴 및 Visual Studio에 대 한 서식 지정
##  <a name="BKMK_TheEnvironmentFont"></a>환경 글꼴  
 Visual Studio 내에서 모든 글꼴 사용자 지정에 대 한 사용자에 게 노출 되어야 합니다. 이 기능은 주로 통해 수행 되어는 **글꼴 및 색** 페이지에 **도구 > 옵션** 대화 상자. 글꼴 설정의 세 가지 주요 범주는:  
  
-   **환경 글꼴** -IDE (통합된 개발 환경)에 대 한 기본 글꼴 대화 상자, 메뉴, 도구 창 및 문서 창 포함 하 여 모든 인터페이스 요소에 사용 합니다. 기본적으로 현재 버전의 Windows에서 9 포인트 맑은 고딕, Segoe UI로 표시 되는 시스템 글꼴 환경 글꼴 연결 됩니다. 모든 인터페이스 요소에 대 한 글꼴을 사용 하 여 IDE 전체에서 일관 된 글꼴 모양이 표시 되도록 하는 데 도움이 됩니다.  
  
-   **텍스트 편집기** -는 표면에서 코드 및 기타 텍스트 기반 편집기 사용자 지정할 수 있는 텍스트 편집기에서 요소를 페이지에 **도구 > 옵션**합니다.  
  
-   **특정 컬렉션** -자신의 설정 페이지에서 해당 인터페이스 요소의 사용자 지정 디자인 특정 글꼴을 노출 될 수 있습니다를 제공 하는 디자이너 창 화면 **도구 > 옵션**합니다.  
  
### <a name="editor-font-customization-and-resizing"></a>글꼴 사용자 지정 편집기 및 크기 조정  
 사용자가 자주 됩니다를 확대 하거나 독립적인 일반 사용자 인터페이스의 기본 설정에 따라 편집기에서 텍스트의 색 및/또는 크기를 확대/축소 합니다. 내에서 또는 편집기/designer의 일부로 표시 될 수 있는 요소에 사용 되므로 환경 글꼴에는 다음 글꼴 분류 중 하나가 변경 될 때 예상 되는 동작에 유의 해야 합니다.  
  
 일부가 아닌는 없지만 편집기에 표시 되는 UI 요소를 만들 때는 *콘텐츠*, 예측 가능한 방식으로 크기가 조정 요소 환경 글꼴 및 텍스트 글꼴이 아닌를 사용 해야 합니다.  
  
1.  코드 편집기에서 텍스트에 대 한 코드 텍스트 글꼴 설정을 조정 하 고 편집기 텍스트의 확대/축소 수준에 응답 합니다.  
  
2.  환경 글꼴 설정을 연결 해야 하 고 환경에서 모든 전역 변경 내용에 응답 하는 인터페이스의 다른 모든 요소입니다. 이 포함 됩니다 (그러나에 국한 되지 않음):  
  
    -   상황에 맞는 메뉴의 텍스트  
  
    -   텍스트 편집기 adornment에 같은 전구 메뉴 텍스트를 빠른 찾기 편집기 창 및 창으로 이동  
  
    -   같은 대화 상자의 텍스트에에서 레이블을 지정 **파일에서 찾기** 또는 **리팩터링**  
  
### <a name="accessing-the-environment-font"></a>환경 글꼴에 액세스  
 기본 모드 또는 WinForms 코드 환경 글꼴 메서드를 호출 하 여 액세스할 수 있습니다 `IUIHostLocale::GetDialogFont` 인터페이스를 쿼리 한 후의 `SID_SUIHostLocale` 서비스입니다.  
  
 에 대 한 WPF Windows Presentation Foundation (), 셸의에서 대화 상자 창 클래스를 파생 `DialogWindow` WPF의 대신 클래스 `Window` 클래스입니다.  
  
 XAML에서 코드는 다음과 같습니다.  
  
```  
<ui:DialogWindow  
    x:Class"MyNameSpace.MyWindow"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:s="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:ui="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.11.0"  
    ShowInTaskbar="False"  
    WindowStartupLocation="CenterOwner"  
    Title="My Dialog">  
</ui:DialogWindow>  
  
code behind:  
  
internal partial class WebConfigModificationWindow : DialogWindow  
{  
}  
```  
  
 (바꾸기 `Microsoft.VisualStudio.Shell.11.0` MPF dll의 현재 버전과.)  
  
 대화 상자를 표시 하려면 "`ShowModal()`" 클래스를 통해 `ShowDialog()`합니다. `ShowModal()`셸에서 올바른 모달 상태를 설정으로, 대화 상자에 확인 하 고 부모 창을에 가운데 맞춤 됩니다.  
  
 코드는 다음과 같습니다.  
  
```  
MyWindow window = new MyWindow();  
window.ShowModal()  
```  
  
 `ShowModal`부울 값을 반환? (nullable 부울)와 `DialogResult`, 필요한 경우 사용할 수 있는 합니다. 반환 값은 true와 대화 상자를 닫은 경우 **확인**합니다.  
  
 자체에 대화 상자 아니며 호스팅되는 일부 WPF UI를 표시 하기 위해 필요한 경우 `HwndSource`, 팝업 창 또는 Win32/WinForms 부모 창 창의 WPF 자식 창 같은 설정 해야 합니다는 `FontFamily` 및 `FontSize` WPF 요소의 루트 요소에 있습니다. (주 창에서 속성을 설정 하는 셸 하지만 지난 상속 되지 것입니다는 `HWND`). 셸에 속성을 바인딩할 수, 다음과 같은 리소스를 제공 합니다.  
  
```  
<Setter property="FontFamily" Value="{DynamicResource VsFont.EnvironmentFontFamily}" />  
<Setter property="FontSize" Value="{DynamicResource VsFont.EnvironmentFontSize}" />  
```  
  
###  <a name="BKMK_Formatting"></a>(확장/굵게 표시) 참조 서식 지정  
 일부 대화 상자에는 특정 텍스트를 굵게 표시 또는 이외의 환경 글꼴 크기 필요 합니다. 환경 글꼴 보다 큰 글꼴으로 코딩 된 이전에 "`environment font +2`" 또는 유사한 곳입니다. 제공 된 코드 조각을 사용 하 여 높은 DPI 모니터를 지원 되 고 표시 텍스트 정확한 크기와 가중치 (예: 조명 또는 semilight를 권장)에서 항상 표시 되는지 확인 됩니다.  
  
> **참고: 서식 지정을 적용 하기 전에 확인의 지침을 따르는 [텍스트 스타일](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle)합니다.**  
  
 환경 글꼴의 크기를 조정 하려면 TextBlock 또는 표시 된 대로 레이블 스타일을 설정 합니다. 각 올바로 사용 이러한 코드 조각은 적절 한 크기 및 중량 변경을 포함 하 여 올바른 글꼴을 생성 합니다.  
  
 여기서 "`vsui`" 네임 스페이스에 대 한 참조 `Microsoft.VisualStudio.Shell`:  
  
```  
xmlns:vsui="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0" 
```  
  
#### <a name="375-environment-font--light"></a>375% 환경 글꼴 + Light  
 **로 표시:** 34 pt 맑은 고딕, Segoe UI Light  
 **에 대 한 사용:** (드물게) 고유 브랜드 UI, like 시작 페이지에서

 **프로시저 코드:** 여기서 `textBlock` 은 이전에 정의한 TextBlock 및 `label` 이전에 정의 된 레이블이:  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment375PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment375PercentFontSizeStyleKey);  
```  
  
 **XAML:** 표시 된 대로 TextBlock 또는 레이블 스타일을 설정 합니다.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment375PercentFontSizeStyleKey}}">TextBlock: 375 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment375PercentFontSizeStyleKey}}">Label: 375 Percent Scaling</Label>  
```  
  
#### <a name="310-environment-font--light"></a>310% 환경 글꼴 + Light  
 **로 표시:** 28 pt 맑은 고딕, Segoe UI Light   
 **에 대 한 사용:** 큰 서명 대화 상자 제목, 주 보고서의 제목  
  
 **프로시저 코드:** 여기서 `textBlock` 은 이전에 정의한 TextBlock 및 `label` 이전에 정의 된 레이블이:  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment310PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment310PercentFontSizeStyleKey);    
```  
  
 **XAML:** 표시 된 대로 TextBlock 또는 레이블 스타일을 설정 합니다.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment310PercentFontSizeStyleKey}}">TextBlock: 310 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment310PercentFontSizeStyleKey}}">Label: 310 Percent Scaling</Label>     
```  
  
#### <a name="200-environment-font--semilight"></a>200% 환경 글꼴 + semilight를 권장  
 **로 표시:** 18 포인트 맑은 고딕, Segoe UI semilight를 권장    
 **에 대 한 사용:** 부제목, 소규모 및 중간 규모 대화 상자에 제목  
  
 **프로시저 코드:** 여기서 `textBlock` 은 이전에 정의한 TextBlock 및 `label` 이전에 정의 된 레이블이: 
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment200PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment200PercentFontSizeStyleKey);    
```  
  
 **XAML:** 표시 된 대로 TextBlock 또는 레이블 스타일을 설정 합니다.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment200PercentFontSizeStyleKey}}">TextBlock: 200 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment200PercentFontSizeStyleKey}}">Label: 200 Percent Scaling</Label>    
```  
  
#### <a name="155-environment-font"></a>155% 환경 글꼴  
 **로 표시:** 14pt 맑은 고딕, Segoe UI    
 **에 대 한 사용:** UI 또는 보고서 제대로 작동 하는 문서의 섹션 제목  
  
 **프로시저 코드:** 여기서 `textBlock` 은 이전에 정의한 TextBlock 및 `label` 이전에 정의 된 레이블이:  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment155PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment155PercentFontSizeStyleKey);    
```  
  
 **XAML:** 표시 된 대로 TextBlock 또는 레이블 스타일을 설정 합니다.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment155PercentFontSizeStyleKey}}">TextBlock: 155 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment155PercentFontSizeStyleKey}}">Label: 155 Percent Scaling</Label>  
```  
  
#### <a name="133-environment-font"></a>133% 환경 글꼴  
 **로 표시:** 12 포인트 맑은 고딕, Segoe UI    
 **에 대 한 사용:** 서명 대화 상자와 문서에 더 작은 부제목 잘 UI  
  
 **프로시저 코드:** 여기서 `textBlock` 은 이전에 정의한 TextBlock 및 `label` 이전에 정의 된 레이블이:  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment133PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment133PercentFontSizeStyleKey);    
```  
  
 **XAML:** 표시 된 대로 TextBlock 또는 레이블 스타일을 설정 합니다.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment133PercentFontSizeStyleKey}}">TextBlock: 133 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment133PercentFontSizeStyleKey}}">Label: 133 Percent Scaling</Label>    
```  
  
#### <a name="122-environment-font"></a>122% 환경 글꼴  
 **로 표시:** 11 pt 맑은 고딕, Segoe UI    
 **에 대 한 사용:** 서명 대화 상자에는 머리글 섹션, 세로 탭 탐색 트리 뷰에서 노드 최상위  
  
 **프로시저 코드:** 여기서 `textBlock` 은 이전에 정의한 TextBlock 및 `label` 이전에 정의 된 레이블이:  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment122PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment122PercentFontSizeStyleKey);    
```  
  
 **XAML:** 표시 된 대로 TextBlock 또는 레이블 스타일을 설정 합니다.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment122PercentFontSizeStyleKey}}">TextBlock: 122 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment122PercentFontSizeStyleKey}}">Label: 122 Percent Scaling</Label>    
```  
  
#### <a name="environment-font--bold"></a>환경 글꼴 + 굵게 표시  
 **로 표시:** 굵게 표시 된 9 포인트 맑은 고딕, Segoe UI    
 **에 대 한 사용:** 레이블 및 부제목 서명 대화 상자, 보고서 및 문서에 잘 UI  
  
 **프로시저 코드:** 여기서 `textBlock` 은 이전에 정의한 TextBlock 및 `label` 이전에 정의 된 레이블이:  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironmentBoldStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironmentBoldStyleKey);    
```  
  
 **XAML:** 표시 된 대로 TextBlock 또는 레이블 스타일을 설정 합니다.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironmentBoldStyleKey}}"> Bold TextBlock</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironmentBoldStyleKey}}"> Bold Label</Label>    
```  
  
### <a name="localizable-styles"></a>지역화할 수 있는 스타일  
 경우에 따라 지역화 담당자 동아시아 언어에 대 한 텍스트에서 굵게 표시를 제거 하는 등의 다른 로캘에 대 한 글꼴 스타일을 수정 해야 합니다. 글꼴 스타일의 지역화를 가능 하 게 하려면 해당 스타일.resx 파일 내에 있어야 합니다. 이 작업을 수행할 여전히 Visual Studio 폼 디자이너에서 글꼴 스타일을 편집 하는 가장 좋은 방법은 명시적으로 디자인 타임에 글꼴 스타일을 설정 하는 합니다. 전체 font 개체 만들어지고 부모 글꼴의 상속을 해제 하는 것 처럼 보일 수, 글꼴을 설정 하는 FontStyle 속성만 사용 됩니다.  
  
 이 솔루션은 대화 상자 폼의 연결을 `FontChanged` 이벤트입니다. 에 `FontChanged` 이벤트를 모든 컨트롤을 안내 하 고 해당 글꼴 설정 되어 있는지 확인 합니다. 이 속성을 설정 하는 경우 폼의 글꼴 및 컨트롤의 이전 글꼴 스타일에 따라 새 글꼴으로 변경 합니다. 코드에서이 예는.  
  
```  
private void Form1_FontChanged(object sender, System.EventArgs e)  
{  
          SetFontStyles();  
}  
  
/// <summary>  
/// SetFontStyles - This function will iterate all controls on a page  
/// and recreate their font with the desired fontstyle.  
/// It should be called in the OnFontChanged handler (and also in the constructor  
/// in case the IUIService is not available so OnFontChange doesn't fire).  
/// This way, when the VS shell font is given to us the controls that have  
/// a different style for the font (bolded for example) will recreate their font  
/// and use the VS shell font but with a style variation (bolded ...).  
/// </summary>   
protected void SetFontStyles()  
{  
     SetFontStyles(this, this, this.Font);  
}  
  
protected static void SetFontStyles(Control topControl, Control parent, Font referenceFont)  
{  
     foreach(Control c in parent.Controls)  
     {  
          if (c.Controls != null && c.Controls.Count > 0) {  
               SetFontStyles(topControl, c, referenceFont);  
          }  
          if (c.Font != topControl.Font) {  
               c.Font = new Font(referenceFont, c.Font.Style);  
          }  
     }  
}  
```  
  
 이 코드를 사용 하 여 폼의 글꼴 업데이트 될 때 컨트롤의 글꼴은 업데이트를 보장 합니다. 이 메서드는 대화의 인스턴스를 실패할 수 있으므로 폼의 생성자에서 호출 또한 해야 `IUIService` 및 `FontChanged` 이벤트가 발생 하지 것입니다. 후크 `FontChanged` 대화 상자가 이미 열려 있는 경우에가 동적으로 새 글꼴 선택 대화 상자 허용 됩니다.  
  
### <a name="testing-the-environment-font"></a>테스트 환경 글꼴  
 UI 환경 글꼴을 사용 하 고 크기 설정을 적용 되도록 열고 **도구 > 옵션 > 환경 > 글꼴 및 색** "환경 글꼴" 아래에서 선택 하 고는 "설정 표시:" 드롭 다운 메뉴.  
  
 ![도구에서 글꼴 및 색 설정을 &gt; 옵션 대화 상자](~/extensibility/ux-guidelines/media/0201-a_optionsfonts.png "0201-a_OptionsFonts")<br />도구에서 글꼴 및 색 설정을 &gt; 옵션 대화 상자
  
 기본값 보다 매우 다른 글꼴을 설정 합니다. 명확 하 게 하는 UI를 업데이트 하지 않습니다, serif (예: "Times New Roman")와 글꼴을 선택 하 고 매우 큰 크기를 설정 합니다. 그런 다음 테스트 환경에 반영 하기 위해 UI. 라이선스 대화 상자를 사용 하는 예제는 다음과 같습니다.  
  
 ![환경 글꼴을 고려 하지 않는 UI 텍스트의 예](~/extensibility/ux-guidelines/media/0201-b_wrongfontdialog.png "0201-b_WrongFontDialog")<br />환경 글꼴을 고려 하지 않는 UI 텍스트의 예
  
 이 경우 "사용자 정보" 및 "제품 정보" 글꼴을 유지 하지 됩니다. 명시적 글꼴 검토 사양의 일부분으로 지정 하지 않으면 버그 수 없지만 일부 경우에는 명시적 디자인 선택 수 있습니다.  
  
 글꼴을 다시 설정 하려면 아래를 클릭 "기본값 사용" **도구 > 옵션 > 환경 > 글꼴 및 색**합니다.  
  
##  <a name="BKMK_TextStyle"></a>텍스트 스타일  
 텍스트 스타일 글꼴 크기, 두께 및 대/소문자를 가리킵니다. 구현 지침 참조 [환경 글꼴](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont)합니다.  
  
### <a name="text-casing"></a>텍스트 대/소문자  
  
#### <a name="all-caps"></a>모두 대문자  
 Visual Studio에서 레이블 또는 타이틀에 대 한 모두 대문자를 사용 하지 마십시오.  
  
#### <a name="all-lowercase"></a>모든 소문자  
 사용 하지 마십시오 모두 소문자 Visual Studio에서 레이블 또는 타이틀에 대 한.  
  
#### <a name="sentence-and-title-case"></a>문장 및 제목 대/소문자  
 Visual Studio의 텍스트 제목 대/소문자 또는 상황에 따라 문장 대/소문자를 사용 해야 합니다.  
  
|에 대 한 제목 대/소문자를 사용 합니다.|에 대 한 문장 대/소문자를 사용 합니다.|  
|-------------------------|----------------------------|  
|대화 상자 제목|레이블|  
|그룹 상자|확인란|  
|메뉴 항목|라디오 단추|  
|상황에 맞는 메뉴 항목|목록 상자 항목|  
|단추|상태 표시줄|  
|테이블 레이블||  
|열 머리글||  
|도구 설명||  
  
##### <a name="title-case"></a>제목 대/소문자  
 제목 대/소문자는 대부분 또는 모든 단어 구의 내에서 열의 첫 문자는 대문자로 표시 스타일입니다. Visual Studio에서 단어의 첫 글자는 많은 항목을 포함 하 여에 사용 됩니다.  
  
-   **도구 설명 합니다.** 예: "미리 보기 선택한 항목"  
  
-   **열 머리글입니다.** 예: "시스템 응답"  
  
-   **메뉴 항목입니다.** 예: "모두 저장"  
  
 제목 대/소문자를 사용할 때는 이러한은 소문자로 변경할지를 언제 단어를 대문자로 지정 하 고에 대 한 지침입니다.  
  
|대문자|설명 및 예제|  
|---------------|---------------------------|  
|모든 명사||  
|모든 동사|"Is" 및 다른 형태의 "를 be"를 포함 하 여|  
|모든 부사|"보다" 및 "When"을 포함 하 여|  
|모든 형용사|"는" 및 "This"를 포함 하 여|  
|모든 대명사|소유격이 포함 하 여 "의"도 그대로"," 대명사의 축약 된 것 "it" 및 동사 "is"|  
|문장 요소에 관계 없이 첫 번째 및 마지막 단어||  
|전치사 동사 구의 일부인|"모든 창을 아웃 closing" 또는 "시스템 종료"|  
|글자어의 모든 문자|HTML, XML, URL, IDE, RGB|  
|명사 또는 형용사 적절 한 경우 나 동일한 가중치 단어는 경우 두 번째 복합 단어에서 단어|상호 참조, 사전 Microsoft 소프트웨어의 경우 읽기/쓰기 액세스, 실행 시간|  
  
|소문자|예제|  
|---------------|--------------|  
|다른 음성 부분 또는 첫 번째 단어 수정 분사 경우에 복합 단어의 두 번째 단어|오프 라인 사용 방법|  
|항목 제목에 첫 번째 단어 하나가 아닌 경우|a, 프로그램,|  
|접속사 조정|하지만, nor, 또는|  
|단어의 4 개 이하의 문자가 동사 구 외부 전치사|대상으로를 벗어난의 상단에서|  
|"To" 무한 구문에서 사용 될 때|"하드 디스크를 포맷 하는 방법"|  
  
##### <a name="sentence-case"></a>문장  
 문장 대/소문자만 문장의 첫 번째 단어는 대문자로 시작, 모든 명사 및 대명사 함께 작성에 대 한 표준 대/소문자 방법은 "I" 합니다. 일반적으로 문장의 전세계 고객에 게 특히 때 콘텐츠 번역 될 컴퓨터에서 읽기가 더 쉽습니다. 에 대 한 문장 대/소문자를 사용 합니다.  
  
1.  **상태 표시줄 메시지입니다.** 이들 단순, 즉, 되며만 상태 정보를 제공 합니다. 예: "프로젝트 파일을 로드"  
  
2.  **다른 모든 UI 요소**고, 레이블, 확인란, 라디오 단추를 포함 하 여 상자 항목을 나열 합니다. 예: "모든 항목 선택 목록에"  
  
### <a name="text-formatting"></a>텍스트 서식 지정  
 Visual Studio 2013에서 서식 지정 하는 기본 텍스트에 의해 제어 됩니다 [환경 글꼴](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont)합니다. 이 서비스를 사용 하면 IDE (통합된 개발 환경), 전체에서 일관 된 글꼴 모양 및 사용자를 위한 일관 된 환경을 보장 하기 위해 사용 해야 합니다.  
  
 Visual Studio 글꼴 서비스에서 사용 되는 기본 크기는 Windows에서 제공 하며 9 pt 표시 됩니다.  
  
 환경 글꼴에 서식을 적용할 수 있습니다. 이 항목에서는 방법과 위치 스타일을 사용 하도록 합니다. 구현 정보에 대 한 참조 [환경 글꼴](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont)합니다.  
  
#### <a name="bold-text"></a>굵은 텍스트  
 굵은 텍스트로 Visual Studio에서 자주 사용 되 고에 예약 되어야 합니다.  
  
-   마법사에서 질문 레이블  
  
-   솔루션 탐색기에서 활성 프로젝트를 지정합니다.  
  
-   속성 도구 창에서 값을 재정의  
  
-   Visual Basic 편집기 드롭 다운 목록에서 특정 이벤트  
  
-   웹 페이지에 대 한 문서 개요의 서버에서 생성 된 콘텐츠  
  
-   복잡 한 대화 또는 디자이너 UI 섹션 헤더  
  
#### <a name="italics"></a>기울임꼴  
 Visual Studio는 굵게 또는 기울임꼴 기울임꼴 텍스트를 사용 하지 않습니다.  
  
#### <a name="color"></a>색  
  
-   파랑은 하이퍼링크 (탐색 및 명령 실행)에 대 한 예약 및 방향에 대해 사용 하지 말아야 합니다.  
  
-   이러한 용도로 큰 머리글 (환경 글꼴 155 %5x 이상)를 색칠 할 수 있습니다.:  
  
    -   눈에 띄는 서명 Visual Studio UI를 제공 하려면  
  
    -   특정 영역을 강조할  
  
    -   표준 짙은 회색/검은색 환경 텍스트 색을 제공 하려면  
  
-   머리글에 있는 색 기존 Visual Studio 브랜드 색, 주 자주색 주로 #FF68217A 활용 해야 합니다.  
  
-   머리글에서 색을 사용할 때 따라야는 [Windows 색 지침](https://msdn.microsoft.com/en-us/library/dn742482.aspx), 비율 및 기타 내게 필요한 옵션 고려 사항을 포함 합니다.  
  
### <a name="font-size"></a>글꼴 크기  
 Visual Studio UI 디자인 흰색 공간이 더 많은 밝은 모양을 제공합니다. 가능한 경우, chrome 및 제목 표시줄 감소 되거나 제거 된 합니다. 정보 밀도 Visual Studio에서 요구 사항 이지만, 입력 체계 보다 개방적 줄 간격 및 글꼴 크기 및 중량의 변형에 중점을 두어 중요 한 것으로 계속 됩니다.  
  
 다음 표에서 디자인 세부 정보 및 Visual Studio에서 사용 되는 디스플레이 글꼴에 대 한 시각적 예제가 포함 되어 있습니다. 일부 표시 글꼴 변형의 크기와 semilight를 권장 또는 모양은에 코딩 Light와 같은 가중치 있어야 합니다.  
  
 모든 디스플레이 글꼴에 대 한 구현 코드 조각에 나와 있습니다 [(확장/굵게 표시) 참조 서식을](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_Formatting)합니다.  
  
#### <a name="375-environment-font--light"></a>375% 환경 글꼴 + Light  
  
|||  
|-|-|  
|**사용법:** 드물게 발생 합니다. 고유 브랜드 UI만 합니다.<br /><br /> **수행 합니다.**<br /><br /> -문장 대/소문자를 사용 합니다.<br />-항상 경량 사용<br /><br /> **안 함:**<br /><br /> -사용 하 여 UI에 대 한 서명 시작 페이지와 같은 UI 이외의<br />-굵게, 기울임꼴 또는 bold italic<br />본문 텍스트에 대 한 사용<br />-도구 창에서 사용 합니다.|**로 표시:** 34 pt 맑은 고딕, Segoe UI Light<br /><br /> **Visual 예:**<br /><br /> *현재 사용 되지 않습니다. 시작 페이지에서 사용할 수 있습니다.*|  
  
#### <a name="310-environment-font--light"></a>310% 환경 글꼴 + Light  
  
|||  
|-|-|  
|**사용법:**<br /><br /> -큰 서명 대화 상자에 제목<br />-주 보고서 제목<br /><br /> **수행 합니다.**<br /><br /> -문장 대/소문자를 사용 합니다.<br />-항상 경량 사용<br /><br /> **안 함:**<br /><br /> -사용 하 여 UI에 대 한 서명 시작 페이지와 같은 UI 이외의<br />-굵게, 기울임꼴 또는 bold italic<br />본문 텍스트에 대 한 사용<br />-도구 창에서 사용 합니다.|**로 표시:** 28 pt 맑은 고딕, Segoe UI Light<br /><br /> **Visual 예:**<br /><br /> ![310% 환경 글꼴 &#43;의 예 Light 제목](../../extensibility/ux-guidelines/media/0202-a_ef310.png "0202-a_EF310")|  
  
#### <a name="200-environment-font--semilight"></a>200% 환경 글꼴 + semilight를 권장  
  
|||  
|-|-|  
|**사용법:**<br /><br /> -부제목<br />-소형 및 중간 규모 대화 상자에서 제목<br /><br /> **수행 합니다.**<br /><br /> -문장 대/소문자를 사용 합니다.<br />-항상 semilight를 권장 가중치를 사용 하 여<br /><br /> **안 함:**<br /><br /> -굵게, 기울임꼴 또는 bold italic<br />본문 텍스트에 대 한 사용<br />-도구 창에서 사용 합니다.|**로 표시:** 18 포인트 맑은 고딕, Segoe UI Semillight<br /><br /> **Visual 예:**<br /><br /> ![200% 환경 글꼴 &#43;의 예 Semilight를 권장](../../extensibility/ux-guidelines/media/0202-b_ef200.png "0202-b_EF200")|  
  
#### <a name="155-environment-font"></a>155% 환경 글꼴  
  
|||  
|-|-|  
|**사용법:**<br /><br /> -Section 머리글 문서에 잘 UI<br />-보고서<br /><br /> **방법:** 문장 대/소문자를 사용 하 여<br /><br /> **안 함:**<br /><br /> -굵게, 기울임꼴 또는 bold italic<br />본문 텍스트에 대 한 사용<br />-표준 Visual Studio 컨트롤에서 사용 합니다.<br />-도구 창에서 사용 합니다.|**로 표시:** 14pt 맑은 고딕, Segoe UI<br /><br /> **Visual 예:**<br /><br /> ![155% 환경 글꼴 제목의 예](~/extensibility/ux-guidelines/media/0202-c_ef155.png "0202-c_EF155")|  
  
#### <a name="133-environment-font"></a>133% 환경 글꼴  
  
|||  
|-|-|  
|**사용법:**<br /><br /> 서명 대화 상자에서 더 작은 부제목<br />문서에 더 작은 부제목 잘 UI<br /><br /> **방법:** 문장 대/소문자를 사용 하 여<br /><br /> **안 함:**<br /><br /> -굵게, 기울임꼴 또는 bold italic<br />본문 텍스트에 대 한 사용<br />-표준 Visual Studio 컨트롤에서 사용 합니다.<br />-도구 창에서 사용 합니다.|**로 표시:** 12 포인트 맑은 고딕, Segoe UI<br /><br /> **Visual 예:**<br /><br /> ![133% 환경 글꼴 제목의 예](../../extensibility/ux-guidelines/media/0202-d_ef133.png "0202-d_EF133")|  
  
#### <a name="122-environment-font"></a>122% 환경 글꼴  
  
|||  
|-|-|  
|**사용법:**<br /><br /> -서명 대화 상자에서 섹션 제목<br />-트리 뷰의 노드 위쪽<br />-세로 탭 탐색<br /><br /> **방법:** 문장 대/소문자를 사용 하 여<br /><br /> **안 함:**<br /><br /> -굵게, 기울임꼴 또는 bold italic<br />본문 텍스트에 대 한 사용<br />-표준 Visual Studio 컨트롤에서 사용 합니다.<br />-도구 창에서 사용 합니다.|**로 표시:** 11 pt 맑은 고딕, Segoe UI<br /><br /> **Visual 예:**<br /><br /> ![122% 환경 글꼴 제목의 예](../../extensibility/ux-guidelines/media/0202-e_ef122.png "0202-e_EF122")|  
  
#### <a name="environment-font--bold"></a>환경 글꼴 + 굵게 표시  
  
|||  
|-|-|  
|**사용법:**<br /><br /> -레이블 및 부제목 서명 대화 상자에서<br />-레이블을 지정 하 고 보고서에 부제목<br />-레이블 및 문서에 부제목 변경과 UI<br /><br /> **수행 합니다.**<br /><br /> -문장 대/소문자를 사용 합니다.<br />-B o l 가중치를 사용 합니다.<br /><br /> **안 함:**<br /><br /> -기울임꼴 또는 bold italic<br />본문 텍스트에 대 한 사용<br />-표준 Visual Studio 컨트롤에서 사용 합니다.<br />-도구 창에서 사용 합니다.|**로 표시:** 굵게 표시 된 9 포인트 맑은 고딕, Segoe UI<br /><br /> **Visual 예:**<br /><br /> ![환경 글꼴 &#43;의 예 굵게 제목](../../extensibility/ux-guidelines/media/0202-f_efb.png "0202-f_EFB")|  
  
#### <a name="environment-font"></a>환경 글꼴  
  
|||  
|-|-|  
|**사용법:** 다른 모든 텍스트<br /><br /> **방법:** 문장 대/소문자를 사용 하 여<br /><br /> **안 함:** 기울임꼴 굵게 기울임꼴 또는|**로 표시:** 9 포인트 맑은 고딕, Segoe UI<br /><br /> **Visual 예:**<br /><br /> ![환경 글꼴의 예](../../extensibility/ux-guidelines/media/0202-g_ef.png "0202-g_EF")|  
  
### <a name="padding-and-spacing"></a>안쪽 여백 및 간격  
 머리글에는 주위에 적절 한 강조를 지정 하는 공간이 필요 합니다. 이 공간은 포인트 크기와 환경 글꼴의 텍스트의 줄 또는 단락 구분선 등 머리글 이라는 다른 작업에 따라 달라 집니다.  
  
-   단독으로 제목에 대 한 이상적인 안쪽 여백 문자 자본 높이 공간을 90% 이어야 합니다. 예를 들어 한 28 pt 42 포인트 Segoe UI Light 머리글에 26 포인트의 대문자 높이 하며 23 pt 또는 약 31 픽셀의 안쪽 여백을 약 여야 합니다.  
  
-   제목 주위에 최소 공간 자본 문자 높이의 50% 이어야 합니다. 규칙 또는 다른 긴밀 하 게 맞춤 요소 제목 함께 적은 공간을 사용할 수 있습니다.  
  
-   환경 글꼴 텍스트를 굵게 표시 된 기본 선 높이 간격 및 안쪽 여백 따라야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MSDN: 글꼴 (Windows)](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742483\(v=vs.85\).aspx)   
 [MSDN: 사용자 인터페이스 텍스트 (Windows)](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx)
