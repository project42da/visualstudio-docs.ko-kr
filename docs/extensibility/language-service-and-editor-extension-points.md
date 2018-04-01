---
title: 언어 서비스 및 편집기 확장점 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], new - extension points
ms.assetid: 91a6417e-a6fe-4bc2-9d9f-5173c634a99b
caps.latest.revision: 33
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7e62f1f3cac8f279dedbc79f283b908119d66ff2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="language-service-and-editor-extension-points"></a>언어 서비스 및 편집기 확장 지점
편집기는 프레임 워크 MEF (Managed Extensibility) 구성 요소 부분을 대부분 언어 서비스 기능으로 확장할 수 있는 확장명 지점을 제공 합니다. 다음은 기본 확장 지점 범주입니다.  
  
-   콘텐츠 형식  
  
-   분류 종류와 분류 형식  
  
-   여백 및 스크롤 막대  
  
-   Tags  
  
-   장식  
  
-   마우스 프로세서  
  
-   처리기를 삭제 합니다.  
  
-   옵션  
  
-   IntelliSense  
  
## <a name="extending-content-types"></a>콘텐츠 형식 확장  
 콘텐츠 유형은 종류는 편집기에서 예를 들어 처리 하는 텍스트, "text", "code" 또는 "CSharp"의 정의입니다. 형식의 변수를 선언 하 여 새 콘텐츠 형식을 정의한 <xref:Microsoft.VisualStudio.Utilities.ContentTypeDefinition> 새 콘텐츠 형식에 고유한 이름을 지정 하 고 있습니다. 콘텐츠 형식 편집기를 등록 하려면 다음 특성 함께 내보냅니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>콘텐츠 형식 이름이입니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.BaseDefinitionAttribute>이 콘텐츠 형식 파생 되는 콘텐츠 형식의 이름이입니다. 콘텐츠 형식에서 다른 여러 개의 콘텐츠 형식을 상속할 수 있습니다.  
  
 때문에 <xref:Microsoft.VisualStudio.Utilities.ContentTypeDefinition> 클래스는 봉인 클래스, 형식 매개 변수가 없는 내보낼 수 있습니다.  
  
 다음 예제는 콘텐츠 형식 정의에 내보내기 특성입니다.  
  
```  
[Export]  
[Name("test")]  
[BaseDefinition("code")]  
[BaseDefinition("projection")]  
internal static ContentTypeDefinition TestContentTypeDefinition;  
```  
  
 콘텐츠 형식은 0 개 이상의 기존 콘텐츠 형식에 따라 만들어집니다. 다음은 기본 제공 형식입니다.  
  
-   모든: 기본 콘텐츠 형식입니다. 다른 모든 콘텐츠 형식의 부모입니다.  
  
-   Text: 비 프로젝션 콘텐츠에 대 한 기본 형식입니다. "Any"에서 상속합니다.  
  
-   일반 텍스트:에 대 한 비 코드 텍스트입니다. "Text"에서 상속합니다.  
  
-   코드: 모든 종류의 코드에 대 한 합니다. "Text"에서 상속합니다.  
  
-   기호: 모든 종류의 처리에서 텍스트를 제외합니다. 이 콘텐츠 형식의 텍스트에 적용 된 모든 확장을 갖지 않습니다.  
  
-   프로젝션:에 대 한 프로젝션 버퍼의 내용입니다. "Any"에서 상속합니다.  
  
-   Intellisense:에 대 한 IntelliSense의 내용입니다. "Text"에서 상속합니다.  
  
-   Sighelp: 서명 도움말입니다. "Intellisense"에서 상속합니다.  
  
-   Sighelp doc: 서명 도움말 설명서입니다. "Intellisense"에서 상속합니다.  
  
 다음은 Visual Studio에 의해 정의 된 콘텐츠 형식 중 일부와 Visual Studio에서 호스트 되는 언어의 일부입니다.  
  
-   Basic  
  
-   C/C++  
  
-   ConsoleOutput  
  
-   CSharp  
  
-   CSS  
  
-   ENC  
  
-   FindResults  
  
-   F#  
  
-   HTML  
  
-   JScript  
  
-   XAML  
  
-   XML  
  
 사용 가능한 콘텐츠 형식의 목록을 검색, 가져오기는 <xref:Microsoft.VisualStudio.Utilities.IContentTypeRegistryService>, 편집기에 대 한 콘텐츠 형식의 컬렉션을 유지 하 합니다. 다음 코드를 속성으로이 서비스를 가져옵니다.  
  
```  
[Import]  
internal IContentTypeRegistryService ContentTypeRegistryService { get; set; }  
```  
  
 콘텐츠 형식 파일 이름 확장명을 연결 하려면 사용 하 여 <xref:Microsoft.VisualStudio.Utilities.FileExtensionToContentTypeDefinition>합니다.  
  
> [!NOTE]
>  Visual Studio에서 파일 이름 확장명은 사용 하 여 등록 된 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageExtensionAttribute> 언어 서비스 패키지에 합니다. <xref:Microsoft.VisualStudio.Utilities.FileExtensionToContentTypeDefinition> MEF 콘텐츠 형식에는이 방식으로 등록 된 파일 이름 확장명으로 연결 합니다.  
  
 파일 이름 확장명 콘텐츠 형식 정의 내보내려면 다음 특성을 포함 해야 합니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.FileExtensionAttribute>: 파일 이름 확장명을 지정 합니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: 콘텐츠 형식을 지정 합니다.  
  
 때문에 <xref:Microsoft.VisualStudio.Utilities.FileExtensionToContentTypeDefinition> 클래스는 봉인 클래스, 형식 매개 변수가 없는 내보낼 수 있습니다.  
  
 다음 예제에서는 콘텐츠 형식 정의를 파일 이름 확장명에 내보내기 특성을 보여 줍니다.  
  
```  
[Export]  
[FileExtension(".test")]  
[ContentType("test")]  
internal static FileExtensionToContentTypeDefinition TestFileExtensionDefinition;  
```  
  
 <xref:Microsoft.VisualStudio.Utilities.IFileExtensionRegistryService> 파일 이름 확장명 및 콘텐츠 형식 간 연결을 관리 합니다.  
  
## <a name="extending-classification-types-and-classification-formats"></a>분류 유형 및 분류 확장 형식  
 서로 다른 처리 (예: 파란색 "키워드" 텍스트와 "주석" 텍스트를 녹색 색 지정)를 제공 하려는 텍스트의 종류를 정의 하는 분류 유형을 사용할 수 있습니다. 형식의 변수를 선언 하 여 새 분류 유형을 정의 <xref:Microsoft.VisualStudio.Text.Classification.ClassificationTypeDefinition> 고유 이름을 지정 하 고 있습니다.  
  
 분류 유형을 편집기를 등록 하려면 다음 특성 함께 내보냅니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: 분류 형식의 이름입니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.BaseDefinitionAttribute>:이 분류 유형을 상속 된 분류 형식의 이름입니다. 모든 분류 형식이 "text"에서 상속 하 고 분류 유형을 다른 여러 분류 형식에서 상속할 수 있습니다.  
  
 때문에 <xref:Microsoft.VisualStudio.Text.Classification.ClassificationTypeDefinition> 클래스는 봉인 클래스, 형식 매개 변수가 없는 내보낼 수 있습니다.  
  
 다음 예제에서는 분류 형식 정의에 내보내기 특성을 보여 줍니다.  
  
```  
[Export]  
[Name("csharp.test")]  
[BaseDefinition("test")]  
internal static ClassificationTypeDefinition CSharpTestDefinition;  
```  
  
 <xref:Microsoft.VisualStudio.Language.StandardClassification.IStandardClassificationService> 표준 분류에 대 한 액세스를 제공 합니다. 기본 제공 분류 유형을 다음과 같습니다.  
  
-   "text"  
  
-   "자연어" ("text"에서 파생 됨)  
  
-   "형식 언어" ("text"에서 파생 됨)  
  
-   "string" ("literal"에서 파생 됨)  
  
-   "character" ("literal"에서 파생 됨)  
  
-   "숫자" ("literal"에서 파생 됨)  
  
 상속 하는 다른 오류 형식 집합이 <xref:Microsoft.VisualStudio.Text.Adornments.ErrorTypeDefinition>합니다. 이러한에 다음과 같은 오류 유형이 포함 됩니다.  
  
-   "구문 오류"  
  
-   "컴파일러 오류"  
  
-   "다른 오류"  
  
-   "경고"  
  
 사용 가능한 분류 형식의 목록을 검색, 가져오기는 <xref:Microsoft.VisualStudio.Text.Classification.IClassificationTypeRegistryService>, 편집기에 대 한 분류 형식의 컬렉션을 유지 하 합니다. 다음 코드를 속성으로이 서비스를 가져옵니다.  
  
```  
[Import]  
internal IClassificationTypeRegistryService ClassificationTypeRegistryService { get; set; }  
```  
  
 새 분류 유형에 대 한 분류 형식 정의 정의할 수 있습니다. 클래스를 파생 <xref:Microsoft.VisualStudio.Text.Classification.ClassificationFormatDefinition> 및 형식으로 내보내기 <xref:Microsoft.VisualStudio.Text.Classification.EditorFormatDefinition>다음과 같은 특성을 함께:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: 형식의 이름입니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.DisplayNameAttribute>: 형식 표시 이름입니다.  
  
-   <xref:Microsoft.VisualStudio.Text.Classification.UserVisibleAttribute>: 형식에 표시 되는지 여부를 지정 된 **글꼴 및 색** 의 페이지는 **옵션** 대화 상자.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: 형식 우선 순위입니다. 유효한 값은 <xref:Microsoft.VisualStudio.Text.Classification.Priority>합니다.  
  
-   <xref:Microsoft.VisualStudio.Text.Classification.ClassificationTypeAttribute>:이 형식은 매핑되는 분류의 이름을 입력 합니다.  
  
 다음 예제에서는 분류 형식 정의에 내보내기 특성을 보여 줍니다.  
  
```  
[Export(typeof(EditorFormatDefinition))]  
[ClassificationType(ClassificationTypeNames = "test")]  
[Name("test")]  
[DisplayName("Test")]  
[UserVisible(true)]  
[Order(After = Priority.Default, Before = Priority.High)]  
internal sealed class TestFormat : ClassificationFormatDefinition  
```  
  
 사용 가능한 형식 목록을 검색, 가져오기는 <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMapService>, 편집기에 대 한 서식의 컬렉션을 유지 하 합니다. 다음 코드를 속성으로이 서비스를 가져옵니다.  
  
```  
[Import]  
internal IEditorFormatMapService FormatMapService { get; set; }  
```  
  
## <a name="extending-margins-and-scrollbars"></a>여백 확장 하는 방법 및 스크롤 막대  
 여백 및 스크롤 막대는 텍스트 뷰 자체 외에도 편집기의 주 보기 요소. 텍스트 보기 주위에 표시 되는 표준 여백 외에도 여백 개수에 관계 없이 제공할 수 있습니다.  
  
 구현 된 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewMargin> 여백을 정의 하는 인터페이스입니다. 아울러 구현 해야 합니다는 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewMarginProvider> 인터페이스는 여백을 둘 수 있습니다.  
  
 편집기 여백 공급자를 등록 하려면 다음 특성 함께 공급자 내보내야:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: 여백의 이름입니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: 표시 되는 여백, 다른 여백을 기준으로 순서입니다.  
  
     다음은 기본 제공 여백입니다.  
  
    -   "Wpf 가로 스크롤 막대"  
  
    -   "Wpf 세로 스크롤 막대"  
  
    -   "Wpf 줄 번호 여백을"  
  
     특성의 순서 있는 가로 여백 `After="Wpf Horizontal Scrollbar"` 기본 제공 여백과의 순서 특성을 사용할 가로 여백 아래에 표시 `Before ="Wpf Horizontal Scrollbar"` 기본 제공 여백 위에 표시 됩니다. 오른쪽의 순서 특성을 사용할 세로 여백을 `After="Wpf Vertical Scrollbar"` 스크롤 막대의 오른쪽에 표시 됩니다. 왼쪽의 순서 특성을 사용할 세로 여백 `After="Wpf Line Number Margin"` (보이는 경우)의 줄 번호 여백 왼쪽에 나타납니다.  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.MarginContainerAttribute>: 여백 (왼쪽, 오른쪽, 위쪽, 아래쪽 또는)의 종류입니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: 사용자 여백 올바른지 콘텐츠 (예: "text" 또는 "코드")의 종류입니다.  
  
 다음 예제에 여백 공급자 줄 번호 여백 오른쪽에 나타나는 여백에 대 한 내보내기 특성입니다.  
  
```  
[Export(typeof(IWpfTextViewMarginProvider))]  
[Name("TestMargin")]  
[Order(Before = "Wpf Line Number Margin")]  
[MarginContainer(PredefinedMarginNames.Left)]  
[ContentType("text")]   
```  
  
## <a name="extending-tags"></a>태그 확장  
 태그는 다른 종류의 텍스트와 데이터를 연결 하는 방법입니다. 대부분의 경우에서 연결 된 데이터 시각적 효과로 표시 되지만 모든 태그는 시각적 표시입니다. 구현 하 여 사용자 고유의 종류의 태그를 정의할 수 있습니다 <xref:Microsoft.VisualStudio.Text.Tagging.ITag>합니다. 구현 해야 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> 텍스트 범위의 지정된 된 집합에 대 한 태그를 제공 하는 및 <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider> 제공 된 태거 하기. 다음 특성 함께 태거 공급자를 내보내기를 수행 해야 합니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: 태그를 올바른지 콘텐츠 (예: "text" 또는 "코드")의 종류입니다.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute>: 종류의 태그입니다.  
  
 다음 예제에 태거 공급자 내보내기 특성입니다.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
 다음과 같은 종류의 태그는 기본 제공:  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.ClassificationTag>: 연관 된 <xref:Microsoft.VisualStudio.Text.Classification.IClassificationType>합니다.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.ErrorTag>: 연결 된 오류 유형입니다.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>: adornment 연관 됩니다.  
  
    > [!NOTE]
    >  에 대 한 예제는 <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>에 HighlightWordTag 정의 참조 [연습: 텍스트 강조 표시](../extensibility/walkthrough-highlighting-text.md)합니다.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag>: 확장 하거나 개요에서 축소할 수 있는 영역에 연결 된 합니다.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.SpaceNegotiatingAdornmentTag>: 텍스트 보기에서 adornment 차지 하는 공간을 정의 합니다. 장식 공간 협상 하는 방법에 대 한 자세한 내용은 다음 섹션을 참조 하십시오.  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.IntraTextAdornmentTag>: 자동 간격 및 크기 조정 장식을 제공 합니다.  
  
 찾아서 버퍼 및 뷰에 대 한 태그를 사용 하 여 가져올는 <xref:Microsoft.VisualStudio.Text.Tagging.IViewTagAggregatorFactoryService> 또는 <xref:Microsoft.VisualStudio.Text.Tagging.IBufferTagAggregatorFactoryService>를 제공 하는 한 <xref:Microsoft.VisualStudio.Text.Tagging.ITagAggregator%601> 요청 된 형식의 합니다. 다음 코드를 속성으로이 서비스를 가져옵니다.  
  
```  
[Import]  
internal IViewTagAggregatorFactoryService ViewTagAggregatorFactoryService { get; set; }  
```  
  
#### <a name="tags-and-markerformatdefinitions"></a>태그 및 MarkerFormatDefinitions  
 확장할 수 있습니다는 <xref:Microsoft.VisualStudio.Text.Classification.MarkerFormatDefinition> 태그의 모양을 정의 하는 클래스입니다. 클래스를 내보내야 (으로 <xref:Microsoft.VisualStudio.Text.Classification.EditorFormatDefinition>)는 다음과 같은 특성:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>:이 형식을 참조 하는 데 이름  
  
-   <xref:Microsoft.VisualStudio.Text.Classification.UserVisibleAttribute>:이 인해 UI에 표시 해야 하는 형식  
  
 생성자에서 표시 이름 및 태그의 모양을 정의합니다. <xref:Microsoft.VisualStudio.Text.Classification.EditorFormatDefinition.BackgroundColor%2A>채우기 색을 정의 하 고 <xref:Microsoft.VisualStudio.Text.Classification.EditorFormatDefinition.ForegroundColor%2A> 테두리 색을 정의 합니다. <xref:Microsoft.VisualStudio.Text.Classification.EditorFormatDefinition.DisplayName%2A> 형식 정의의 지역화 가능한 이름입니다.  
  
 다음은 형식 정의의 예제입니다.  
  
```  
[Export(typeof(EditorFormatDefinition))]  
[Name("MarkerFormatDefinition/HighlightWordFormatDefinition")]  
[UserVisible(true)]  
internal class HighlightWordFormatDefinition : MarkerFormatDefinition  
{  
    public HighlightWordFormatDefinition()  
    {  
        this.BackgroundColor = Colors.LightBlue;  
        this.ForegroundColor = Colors.DarkBlue;  
        this.DisplayName = "Highlight Word";   
        this.ZOrder = 5;  
    }  
}  
  
```  
  
 태그에이 형식 정의 적용 하려면 클래스 (표시 이름 아님)의 이름 특성에 설정 이름을 참조 합니다.  
  
> [!NOTE]
>  에 대 한 예제는 <xref:Microsoft.VisualStudio.Text.Classification.MarkerFormatDefinition>에서 HighlightWordFormatDefinition 클래스 참조 [연습: 텍스트 강조 표시](../extensibility/walkthrough-highlighting-text.md)합니다.  
  
## <a name="extending-adornments"></a>장식을 확장  
 장식은 텍스트 보기에 표시 되는 텍스트를 추가할 수 있습니다 또는 텍스트에 자체를 볼 수 있는 시각 효과 정의 합니다. 모든 형식으로 사용자 고유의 장식을 정의할 수 있습니다 <xref:System.Windows.UIElement>합니다.  
  
 장식 클래스에 선언 해야 합니다는 <xref:Microsoft.VisualStudio.Text.Editor.AdornmentLayerDefinition>합니다. 표시 계층을 등록 하려면 다음 특성 함께 내보냅니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: 장식의 이름입니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: 다른 장식 계층에 대해 장식의 순서를 지정 합니다. 클래스 <xref:Microsoft.VisualStudio.Text.Editor.PredefinedAdornmentLayers> 네 가지 기본 레이어 정의: 선택, 개요, 캐럿 및 텍스트입니다.  
  
 다음 예제에서는 장식 계층 정의에 내보내기 특성을 보여 줍니다.  
  
```  
[Export]  
[Name("TestEmbeddedAdornment")]  
[Order(After = PredefinedAdornmentLayers.Selection, Before = PredefinedAdornmentLayers.Text)]  
internal AdornmentLayerDefinition testLayerDefinition;  
```  
  
 구현 하는 두 번째 클래스를 만들어야 합니다 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener> 를 처리 하 고 해당 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener.TextViewCreated%2A> 장식 인스턴스화하여 이벤트입니다. 이 클래스는 다음과 같은 특성이 함께 내보내야 합니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: 장식 올바른지 콘텐츠 (예: "text" 또는 "코드")의 종류입니다.  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute>:이 장식 올바른지 텍스트 보기의 종류입니다. 클래스 <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles> 미리 정의 된 텍스트 보기 역할 집합이 포함 됩니다. 예를 들어 <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Document> 는 파일의 텍스트 보기에 주로 사용 됩니다. <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Interactive>사용자를 편집 하거나 마우스 및 키보드를 사용 하 여 탐색 텍스트 보기에 사용 됩니다. 몇 가지 <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Interactive> 뷰는 텍스트 편집기 보기 및 **출력** 창.  
  
 다음 예제에서는 장식 공급자에 내보내기 특성을 보여 줍니다.  
  
```  
[Export(typeof(IWpfTextViewCreationListener))]  
[ContentType("csharp")]  
[TextViewRole(PredefinedTextViewRoles.Document)]  
internal sealed class TestAdornmentProvider : IWpfTextViewCreationListener  
```  
  
 공간 협상 장식 텍스트와 동일한 수준에서 공간을 차지 하는 하나입니다. 상속 되는 태그 클래스를 정의 해야 이러한 종류의 장식을 만들려면 <xref:Microsoft.VisualStudio.Text.Tagging.SpaceNegotiatingAdornmentTag>, 장식 차지 하는 공간의 크기를 정의 하는 합니다.  
  
 모든 장식을와 마찬가지로 장식 계층 정의 내보내야 합니다.  
  
```  
[Export]  
[Name("TestAdornment")]  
[Order(After = DefaultAdornmentLayers.Text)]  
internal AdornmentLayerDefinition testAdornmentLayer;  
```  
  
 공간 협상 장식 인스턴스화를 구현 하는 클래스 만들어야 <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider>를 구현 하는 클래스 뿐 아니라 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener> (다른 종류의 장식과 마찬가지로).  
  
 태거 공급자를 등록 하려면 다음 특성 함께 내보내기를 수행 해야 합니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: 사용자 장식 올바른지 콘텐츠 (예: "text" 또는 "코드")의 종류입니다.  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute>:이 대 한 텍스트 보기의 종류 태그 또는 장식 유효 합니다. 클래스 <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles> 미리 정의 된 텍스트 보기 역할 집합이 포함 됩니다. 예를 들어 <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Document> 는 파일의 텍스트 보기에 주로 사용 됩니다. <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Interactive>사용자를 편집 하거나 마우스 및 키보드를 사용 하 여 탐색 텍스트 보기에 사용 됩니다. 몇 가지 <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Interactive> 뷰는 텍스트 편집기 보기 및 **출력** 창.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute>: 태그 또는 사용자가 정의한 장식의 종류입니다. 두 번째 추가 해야 <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> 에 대 한 <xref:Microsoft.VisualStudio.Text.Tagging.SpaceNegotiatingAdornmentTag>합니다.  
  
 다음 예에서는 공간 협상 장식 태그 태거 공급자에 내보내기 특성을 보여 줍니다.  
  
```  
[Export(typeof(ITaggerProvider))]  
[ContentType("text")]  
[TextViewRole(PredefinedTextViewRoles.Document)]  
[TagType(typeof(SpaceNegotiatingAdornmentTag))]  
[TagType(typeof(TestSpaceNegotiatingTag))]  
internal sealed class TestTaggerProvider : ITaggerProvider  
```  
  
## <a name="extending-mouse-processors"></a>마우스 프로세서를 확장합니다.  
 마우스 입력에 대 한 특수 처리를 추가할 수 있습니다. 상속 되는 클래스를 만듭니다 <xref:Microsoft.VisualStudio.Text.Editor.MouseProcessorBase> 처리할 입력에 대 한 마우스 이벤트를 재정의 합니다. 구현 해야 <xref:Microsoft.VisualStudio.Text.Editor.IMouseProcessorProvider> 에 두 번째 클래스와 함께 내보낼는 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> 마우스 처리기 올바른지 콘텐츠 (예: "text" 또는 "코드")의 종류를 지정 하는 합니다.  
  
 다음 예제에 마우스 프로세서 공급자 내보내기 특성입니다.  
  
```  
[Export(typeof(IMouseProcessorProvider))]  
[Name("test mouse processor")]  
[ContentType("text")]  
[TextViewRole(PredefinedTextViewRoles.Interactive)]   
internal sealed class TestMouseProcessorProvider : IMouseProcessorProvider  
```  
  
## <a name="extending-drop-handlers"></a>Drop 처리기 확장  
 구현 하는 클래스를 만들어 특정 종류의 텍스트에 대 한 drop 처리기의 동작을 사용자 지정할 수 있습니다 <xref:Microsoft.VisualStudio.Text.Editor.DragDrop.IDropHandler> 및 구현 하는 두 번째 클래스 <xref:Microsoft.VisualStudio.Text.Editor.DragDrop.IDropHandlerProvider> 놓기 처리기를 만듭니다. 놓기 처리기는 다음과 같은 특성이 함께 내보내기를 수행 해야 합니다.  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.DragDrop.DropFormatAttribute>:이 드롭 처리기 올바른지 텍스트 형식입니다. 다음과 같은 형식이 내림차순으로 최고 우선 순위 순서로 처리 됩니다.  
  
    1.  모든 사용자 지정 형식  
  
    2.  FileDrop  
  
    3.  EnhancedMetafile  
  
    4.  WaveAudio  
  
    5.  Riff  
  
    6.  Dif  
  
    7.  로캘  
  
    8.  색상표  
  
    9. PenData  
  
    10. 직렬화 가능  
  
    11. SymbolicLink  
  
    12. Xaml  
  
    13. XamlPackage  
  
    14. tiff  
  
    15. Bitmap  
  
    16. Dib  
  
    17. MetafilePicture  
  
    18. CSV  
  
    19. System.String  
  
    20. HTML 형식  
  
    21. UnicodeText  
  
    22. OEMText  
  
    23. 텍스트  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: drop 처리기의 이름입니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: 기본 놓기 처리기 전후 놓기 처리기의 순서입니다. Visual Studio에 대 한 기본 놓기 처리기 "DefaultFileDropHandler" 라고 합니다.  
  
 다음 예에서는 drop 처리기 공급자에 내보내기 특성을 보여 줍니다.  
  
```  
[Export(typeof(IDropHandlerProvider))]  
[DropFormat("Text")]   
[Name("TestDropHandler")]  
[Order(Before="DefaultFileDropHandler")]   
internal class TestDropHandlerProvider : IDropHandlerProvider  
```  
  
## <a name="extending-editor-options"></a>편집기 옵션을 확장합니다.  
 텍스트 보기에서 특정 범위를 예를 들어에 유효 하는 옵션을 정의할 수 있습니다. 이 미리 정의 된 옵션이 집합을 제공 하는 편집기: 편집기 옵션, 보기 옵션 및 Windows Presentation Foundation (WPF) 보기 옵션입니다. 이러한 옵션을 확인할 수 있습니다 <xref:Microsoft.VisualStudio.Text.Editor.DefaultOptions>, <xref:Microsoft.VisualStudio.Text.Editor.DefaultTextViewOptions>, 및 <xref:Microsoft.VisualStudio.Text.Editor.DefaultWpfViewOptions>합니다.  
  
 새 옵션을 추가 하려면이 옵션의 정의 클래스 중 하나에서 클래스를 파생 합니다.  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.EditorOptionDefinition%601>  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.ViewOptionDefinition%601>  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.WpfViewOptionDefinition%601>  
  
 다음 예에서는 부울 값을 갖는 옵션 정의 내보내는 방법을 보여 줍니다.  
  
```  
[Export(typeof(EditorOptionDefinition))]  
internal sealed class TestOption : EditorOptionDefinition<bool>  
```  
  
## <a name="extending-intellisense"></a>IntelliSense 확장  
 IntelliSense에 대 한 문 완성 및 구조화 된 텍스트에 대 한 정보를 제공 하는 기능 그룹에 대 한 일반적인 용어는입니다. 이러한 기능에는 문 완성, 서명 도움말, 요약 정보 및 전구 포함 됩니다. 문 완성 기능 사용자가 언어 키워드 또는 멤버 이름을 올바르게 입력 합니다. 서명 도움말 서명 또는 사용자가 방금 입력 한 메서드의 서명을 표시 합니다. 요약 정보 위에 마우스를 놓을 때 형식 또는 멤버 이름에 대 한 전체 시그니처를 표시 합니다. 전구는 한 항목의 이름이 변경 되는 변수의 모든 항목 이름 바꾸기 예를 들어 특정 컨텍스트에서 특정 식별자에 대 한 추가 작업을 제공 합니다.  
  
 IntelliSense 기능의 디자인은 모든 경우에에서 상당히 같습니다.  
  
-   IntelliSense *브로커* 전체 프로세스를 담당 합니다.  
  
-   IntelliSense *세션* 발표자 동시 하거나 취소 된 선택의 트리거에 사이의 이벤트의 시퀀스를 나타냅니다. 일반적으로 세션 일부 사용자 제스처에 의해 트리거됩니다.  
  
-   IntelliSense *컨트롤러* 는 세션이 시작 되 고 끝날 때 결정 합니다. 또한 때 정보를 적용 해야 하 고 세션을 취소 해야 하는 경우를 결정 합니다.  
  
-   IntelliSense *소스* 내용을 제공 하 고 가장 일치 하는 결정 합니다.  
  
-   IntelliSense *발표자* 콘텐츠를 표시 합니다.  
  
 대부분의 경우에서 하나 이상의 소스와 컨트롤러를 제공 하는 것이 좋습니다. 표시를 사용자 지정 하려는 경우에 발표자를 제공할 수 있습니다.  
  
### <a name="implementing-an-intellisense-source"></a>IntelliSense 소스 구현  
 소스를 사용자 지정 하려면 하나 이상의 다음 소스 인터페이스를 구현 해야 합니다.  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSource>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSource>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource>  
  
> [!IMPORTANT]
>  <xref:Microsoft.VisualStudio.Language.Intellisense.ISmartTagSource>사용 되지 않습니다 기준 <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource>합니다.  
  
 또한 같은 종류의 공급자를 구현 해야 합니다.  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSourceProvider>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSourceProvider>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSourceProvider>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSourceProvider>  
  
> [!IMPORTANT]
>  <xref:Microsoft.VisualStudio.Language.Intellisense.ISmartTagSourceProvider>사용 되지 않습니다 기준 <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSourceProvider>합니다.  
  
 공급자는 다음과 같은 특성이 함께 내보내기를 수행 해야 합니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>:는 원본의 이름입니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: 소스 적용 되는 콘텐츠 (예: "text" 또는 "코드")의 종류입니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: (다른 원본의 경우)에 대해 소스를 표시할 순서입니다.  
  
-   다음 예제에서는 완성 소스 공급자에서 내보내기 특성을 보여 줍니다.  
  
```  
Export(typeof(ICompletionSourceProvider))]  
[Name(" Test Statement Completion Provider")]  
[Order(Before = "default")]  
[ContentType("text")]  
internal class TestCompletionSourceProvider : ICompletionSourceProvider  
```  
  
 IntelliSense 소스를 구현 하는 방법에 대 한 자세한 내용은 다음 연습을 참조 합니다.  
  
 [연습: QuickInfo 도구 설명 표시](../extensibility/walkthrough-displaying-quickinfo-tooltips.md)  
  
 [연습: 서명 도움말 표시](../extensibility/walkthrough-displaying-signature-help.md)  
  
 [연습: 문 완성 표시](../extensibility/walkthrough-displaying-statement-completion.md)  
  
### <a name="implementing-an-intellisense-controller"></a>IntelliSense 컨트롤러 구현  
 컨트롤러를 사용자 지정 하려면 구현 해야 합니다는 <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController> 인터페이스입니다. 또한 다음 특성 함께 컨트롤러 공급자를 구현 해야 합니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: 컨트롤러의 이름입니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: 컨트롤러 적용 되는 콘텐츠 (예: "text" 또는 "코드")의 종류입니다.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: (다른 컨트롤러)에 대해 표시할 컨트롤러는 순서입니다.  
  
 다음 예제에 완료 컨트롤러 공급자 내보내기 특성입니다.  
  
```  
Export(typeof(IIntellisenseControllerProvider))]  
[Name(" Test Controller Provider")]  
[Order(Before = "default")]  
[ContentType("text")]  
internal class TestIntellisenseControllerProvider : IIntellisenseControllerProvider  
```  
  
 IntelliSense 컨트롤러를 사용 하는 방법에 대 한 자세한 내용은 다음 연습을 참조 합니다.  
  
 [연습: QuickInfo 도구 설명 표시](../extensibility/walkthrough-displaying-quickinfo-tooltips.md)