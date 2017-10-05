---
title: "연습: 전구 제안을 표시 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99e5566d-450e-4660-9bca-454e1c056a02
caps.latest.revision: 16
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
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 1096b04fee06415e65a93b0ecd8a6257de64edfc
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="walkthrough-displaying-light-bulb-suggestions"></a>연습: 전구 제안 표시
전구는 일련의 작업을 표시 하도록 확장, 예를 들어 기본 제공 코드 분석기 또는 코드 리팩터링에 의해 식별 된 문제를 해결 하는 Visual Studio 편집기에서 사용 되는 아이콘입니다.  
  
 Visual C# 및 Visual Basic 편집기에서 작성 하 고 패키지 전구를 자동으로 표시 되는 작업에 사용자 고유의 코드 분석기.NET 컴파일러 플랫폼 ("Roslyn")을 사용할 수 있습니다. 자세한 내용은 다음을 참조하세요.  
  
-   [방법: C# 진단 및 코드 수정 프로그램 작성](https://github.com/dotnet/roslyn/wiki/How-To-Write-a-C%23-Analyzer-and-Code-Fix)  
  
-   [방법: Visual Basic 진단 및 코드 수정 프로그램 작성](https://github.com/dotnet/roslyn/wiki/How-To-Write-a-Visual-Basic-Analyzer-and-Code-Fix)  
  
 또한 c + +와 같은 다른 언어는 해당 함수에 대 한 스텁 구현을 만들 한 제안 사항 등의 일부 빠른 동작에 대 한 전구를 제공 합니다.  
  
 다음은 전구가 표시 되는 모양입니다. Visual Basic 또는 Visual C# 프로젝트에서 유효 하지 않을 때 변수 이름 아래에 빨간색 물결이 나타납니다. 잘못 된 식별자 위로 마우스 커서 옆 전구가 표시 됩니다.  
  
 ![전구](../extensibility/media/lightbulb.png "전구")  
  
 전구에서 아래쪽 화살표를 클릭 하면 선택한 동작의 미리 보기 함께 제안 된 작업 집합이 표시 됩니다. 이 경우 작업을 실행 하는 경우 코드에 적용 될 변경 내용을 보여 줍니다.  
  
 ![전구 미리 보기](../extensibility/media/lightbulbpreview.png "LightBulbPreview")  
  
 사용자 고유의 제안 된 작업을 제공 하도록 전구를 사용할 수 있습니다. 예를 들어 여 중괄호를 새 줄으로 이동 하거나 앞 줄의 끝으로 이동 하는 작업을 제공할 수 있습니다. 다음 연습에서는 현재 단어에 표시 된 전구를 만드는 방법을 보여주며, 두 개의 제안 동작: **대문자로 변환** 및 **를 소문자로 변환**합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-a-managed-extensibility-framework-mef-project"></a>MEF(Managed Extensibility Framework) 프로젝트 만들기  
  
1.  C# VSIX 프로젝트를 만듭니다. (에 **새 프로젝트** 대화 상자에서 **Visual C# / 확장성**, 다음 **VSIX 프로젝트**.) 솔루션 이름을 `LightBulbTest`합니다.  
  
2.  추가 **편집기 분류자** 항목 템플릿을 프로젝트에 있습니다. 자세한 내용은 참조 [편집기 항목 템플릿을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-an-editor-item-template.md)합니다.  
  
3.  기존 클래스 파일을 삭제합니다.  
  
4.  프로젝트에 다음 참조를 추가 하 고 설정 **로컬 복사** 를 `False`:  
  
     Microsoft.VisualStudio.Language.Intellisense  
  
5.  새 클래스 파일을 추가 하 고 이름을 **LightBulbTest**합니다.  
  
6.  다음 추가 문을 사용 하 여:  
  
    ```csharp  
    using System;  
    using System.Linq;  
    using System.Collections.Generic;  
    using System.Threading.Tasks;  
    using Microsoft.VisualStudio.Language.Intellisense;  
    using Microsoft.VisualStudio.Text;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.Text.Operations;  
    using Microsoft.VisualStudio.Utilities;  
    using System.ComponentModel.Composition;  
    using System.Threading;  
  
    ```  
  
## <a name="implementing-the-light-bulb-source-provider"></a>전구 소스 공급자 구현  
  
1.  LightBulbTest.cs 클래스 파일에서 LightBulbTest 클래스를 삭제 합니다. 라는 클래스를 추가 **TestSuggestedActionsSourceProvider** 를 구현 하는 <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSourceProvider>합니다. 이름으로 내보내기 **테스트 권장 조치** 및 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "text"입니다.  
  
    ```csharp  
    [Export(typeof(ISuggestedActionsSourceProvider))]  
    [Name("Test Suggested Actions")]  
    [ContentType("text")]  
    internal class TestSuggestedActionsSourceProvider : ISuggestedActionsSourceProvider  
    ```  
  
2.  원본 공급자 클래스의 내부 가져오기는 <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> 속성으로 추가 합니다.  
  
    ```csharp  
    [Import(typeof(ITextStructureNavigatorSelectorService))]  
    internal ITextStructureNavigatorSelectorService NavigatorService { get; set; }  
    ```  
  
3.  구현 된 <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSourceProvider.CreateSuggestedActionsSource%2A> 반환 하는 메서드는 <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource> 개체입니다. 다음 섹션에서 소스를 설명 합니다.  
  
    ```csharp  
    public ISuggestedActionsSource CreateSuggestedActionsSource(ITextView textView, ITextBuffer textBuffer)  
    {  
        if (textBuffer == null && textView == null)  
        {  
            return null;  
        }  
        return new TestSuggestedActionsSource(this, textView, textBuffer);  
    }  
    ```  
  
## <a name="implementing-the-isuggestedactionsource"></a>ISuggestedActionSource 구현  
 적절된 한 조치 소스는 제안 된 작업의 집합을 수집 하 고 오른쪽 컨텍스트에 추가한 하는 일을 담당 합니다. 이 경우 컨텍스트는 현재 단어 및 권장된 조치는 **UpperCaseSuggestedAction** 및 **LowerCaseSuggestedAction**, 다음 섹션에서 설명 합니다.  
  
1.  클래스를 추가 **TestSuggestedActionsSource** 를 구현 하는 <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource>합니다.  
  
    ```csharp  
    internal class TestSuggestedActionsSource : ISuggestedActionsSource  
    ```  
  
2.  적절된 한 조치 소스 공급자, 텍스트 버퍼 및 텍스트 보기에 대 한 전용 읽기 전용 필드를 추가 합니다.  
  
    ```csharp  
    private readonly TestSuggestedActionsSourceProvider m_factory;  
    private readonly ITextBuffer m_textBuffer;  
    private readonly ITextView m_textView;  
    ```  
  
3.  전용 필드를 설정 하는 생성자를 추가 합니다.  
  
    ```csharp  
    public TestSuggestedActionsSource(TestSuggestedActionsSourceProvider testSuggestedActionsSourceProvider, ITextView textView, ITextBuffer textBuffer)  
    {  
        m_factory = testSuggestedActionsSourceProvider;  
        m_textBuffer = textBuffer;  
        m_textView = textView;  
    }  
    ```  
  
4.  현재 커서 아래에 있는 단어를 반환 하는 개인 메서드를 추가 합니다. 다음 메서드는 커서의 현재 위치 찾은 단어 범위에 대 한 텍스트 구조 탐색기를 요청 합니다. 커서가 단어에 있는 경우는 <xref:Microsoft.VisualStudio.Text.Operations.TextExtent> out 매개 변수에서 반환 되 고, 그렇지 않으면는 `out` 매개 변수는 `null` 메서드에서 반환 `false`합니다.  
  
    ```csharp  
    private bool TryGetWordUnderCaret(out TextExtent wordExtent)  
    {  
        ITextCaret caret = m_textView.Caret;  
        SnapshotPoint point;  
  
        if (caret.Position.BufferPosition > 0)  
        {  
            point = caret.Position.BufferPosition - 1;  
        }  
        else  
        {  
            wordExtent = default(TextExtent);  
            return false;  
        }  
  
        ITextStructureNavigator navigator = m_factory.NavigatorService.GetTextStructureNavigator(m_textBuffer);  
  
        wordExtent = navigator.GetExtentOfWord(point);  
        return true;  
    }  
    ```  
  
5.  <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource.HasSuggestedActionsAsync%2A> 메서드를 구현합니다. 편집기의 전구 표시 여부를 확인 하려면이 메서드를 호출 합니다. 이 호출이 오류 표시선 위로 마우스를 이동할 때 또는 다른 커서를 한 줄에서 이동할 때마다 예를 들어 경우가 매우 자주 생성 됩니다. 이 메서드가 작동 하는 동안 수행 하기 위해 다른 UI 작업을 허용 하기 위해 비동기 됩니다. 따라서이 메서드를 일부 구문 분석 및 현재 줄의 분석을 수행 해야 합니다. 대부분의 경우에서 처리 시간이 걸릴 수 있습니다.  
  
     이 구현에서 비동기적으로 가져옵니다는 <xref:Microsoft.VisualStudio.Text.Operations.TextExtent> 범위 중요 한지 여부, 즉, 공백이 아닌 일부 텍스트 있는지 여부를 결정 합니다.  
  
    ```csharp  
    public Task<bool> HasSuggestedActionsAsync(ISuggestedActionCategorySet requestedActionCategories, SnapshotSpan range, CancellationToken cancellationToken)  
    {  
        return Task.Factory.StartNew(() =>  
        {  
            TextExtent extent;  
            if (TryGetWordUnderCaret(out extent))  
            {  
                // don't display the action if the extent has whitespace  
                return extent.IsSignificant;  
              }  
            return false;  
        });  
    }  
    ```  
  
6.  구현 된 <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource.GetSuggestedActions%2A> 의 배열을 반환 하 <xref:Microsoft.VisualStudio.Language.Intellisense.SuggestedActionSet> 여러 가지를 포함 하는 개체 <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedAction> 개체입니다. 이 메서드는 전구 확장 될 때 호출 됩니다.  
  
    > [!WARNING]
    >  확인 해야 하는의 구현 `HasSuggestedActionsAsync()` 및 `GetSuggestedActions()` ; 일관 된 되는 경우, `HasSuggestedActionsAsync()` 반환 `true`, 다음 `GetSuggestedActions()` 표시할 일부 작업에 있어야 합니다. 대부분의 경우에서 `HasSuggestedActionsAsync()` 직전에 호출 `GetSuggestedActions()`, 하지만 항상 대/소문자는 없습니다. 예를 들어 사용자 키를 눌러 전구 작업을 호출 하는 경우 (CTRL +.)만 `GetSuggestedActions()` 라고 합니다.  
  
    ```csharp  
    public IEnumerable<SuggestedActionSet> GetSuggestedActions(ISuggestedActionCategorySet requestedActionCategories, SnapshotSpan range, CancellationToken cancellationToken)  
    {  
        TextExtent extent;  
        if (TryGetWordUnderCaret(out extent) && extent.IsSignificant)  
        {  
            ITrackingSpan trackingSpan = range.Snapshot.CreateTrackingSpan(extent.Span, SpanTrackingMode.EdgeInclusive);  
            var upperAction = new UpperCaseSuggestedAction(trackingSpan);  
            var lowerAction = new LowerCaseSuggestedAction(trackingSpan);  
            return new SuggestedActionSet[] { new SuggestedActionSet(new ISuggestedAction[] { upperAction, lowerAction }) };  
        }  
        return Enumerable.Empty<SuggestedActionSet>();  
    }   
    ```  
  
7.  정의 `SuggestedActionsChanged` 이벤트입니다.  
  
    ```csharp  
    public event EventHandler<EventArgs> SuggestedActionsChanged;  
    ```  
  
8.  구현을 완료 하려면에 대 한 구현을 추가 `Dispose()` 및 `TryGetTelemetryId()` 메서드. 원격 분석을 수행 하 고, false를 반환 하므로, Empty로 GUID를 설정할 하려고 하지 않습니다.  
  
    ```csharp  
    public void Dispose()  
    {  
    }  
  
    public bool TryGetTelemetryId(out Guid telemetryId)  
    {  
        // This is a sample provider and doesn't participate in LightBulb telemetry  
        telemetryId = Guid.Empty;  
        return false;  
    }  
    ```  
  
## <a name="implementing-light-bulb-actions"></a>전구 동작 구현  
  
1.  프로젝트에서 Microsoft.VisualStudio.Imaging.Interop.14.0.DesignTime.dll 및 설정에 대 한 참조를 추가 **로컬 복사** 를 `False`합니다.  
  
2.  두 개의 클래스를 만드는 첫 번째 라는 `UpperCaseSuggestedAction` 및 두 번째 명명 된 `LowerCaseSuggestedAction`합니다. 두 클래스 모두 <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedAction>를 구현합니다.  
  
    ```csharp  
    internal class UpperCaseSuggestedAction : ISuggestedAction   
    internal class LowerCaseSuggestedAction : ISuggestedAction  
    ```  
  
     하나를 호출 한다는 점을 제외 하면 두 클래스는 유사 <xref:System.String.ToUpper%2A> 및 기타 호출 <xref:System.String.ToLower%2A>합니다. 다음 단계에서는 대문자 동작 클래스만 설명하지만 두 클래스를 모두 구현해야 합니다. 대문자 동작 구현 단계를 소문자 동작 구현 패턴으로 사용합니다.  
  
3.  다음 추가 이러한 클래스에 대 한 문을 사용 하 여:  
  
    ```csharp  
    using Microsoft.VisualStudio.Imaging.Interop;  
    using System.Windows;  
    using System.Windows.Controls;  
    using System.Windows.Documents;  
    using System.Windows.Media;  
  
    ```  
  
4.  전용 필드 집합을 선언합니다.  
  
    ```csharp  
    private ITrackingSpan m_span;  
    private string m_upper;  
    private string m_display;  
    private ITextSnapshot m_snapshot;  
    ```  
  
5.  필드를 설정하는 생성자를 추가합니다.  
  
    ```csharp  
    public UpperCaseSuggestedAction(ITrackingSpan span)  
    {  
        m_span = span;  
        m_snapshot = span.TextBuffer.CurrentSnapshot;  
        m_upper = span.GetText(m_snapshot).ToUpper();  
        m_display = string.Format("Convert '{0}' to upper case", span.GetText(m_snapshot));  
    }  
    ```  
  
6.  구현 된 <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedAction.GetPreviewAsync%2A> 메서드 작업 미리 보기 표시 되도록 합니다.  
  
    ```csharp  
    public Task<object> GetPreviewAsync(CancellationToken cancellationToken)  
    {  
        var textBlock = new TextBlock();  
        textBlock.Padding = new Thickness(5);  
        textBlock.Inlines.Add(new Run() { Text = m_upper });  
        return Task.FromResult<object>(textBlock);  
    }  
    ```  
  
7.  구현 된 <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedAction.GetActionSetsAsync%2A> 메서드는 빈 반환 하도록 <xref:Microsoft.VisualStudio.Language.Intellisense.SuggestedActionSet> 열거 합니다.  
  
    ```csharp  
    public Task<IEnumerable<SuggestedActionSet>> GetActionSetsAsync(CancellationToken cancellationToken)  
    {  
        return Task.FromResult<IEnumerable<SuggestedActionSet>>(null);  
    }  
    ```  
  
8.  속성을 다음과 같이 구현합니다.  
  
    ```csharp  
    public bool HasActionSets  
    {  
        get { return false; }  
    }  
    public string DisplayText  
    {  
        get { return m_display; }  
    }  
    public ImageMoniker IconMoniker  
    {  
       get { return default(ImageMoniker); }  
    }  
    public string IconAutomationText  
    {  
        get  
        {  
            return null;  
        }  
    }  
    public string InputGestureText  
    {  
        get  
        {  
            return null;  
        }  
    }  
    public bool HasPreview  
    {  
        get { return true; }  
    }  
    ```  
  
9. 구현 된 <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedAction.Invoke%2A> 범위에서 텍스트를 해당 대문자로 바꾸어 메서드.  
  
    ```csharp  
    public void Invoke(CancellationToken cancellationToken)  
    {  
        m_span.TextBuffer.Replace(m_span.GetSpan(m_snapshot), m_upper);  
    }  
    ```  
  
    > [!WARNING]
    >  전구 동작 **Invoke** UI를 표시할 수 메서드를 사용할 수 없습니다.  액션 않습니다 새 UI (예를 들어 한 미리 보기 또는 선택 대화 상자)를 가져올 경우 UI 내에서 직접 표시 하지 않습니다는 **Invoke** 메서드 대신에서 반환 된 후 UI를 표시 하려면 예약 하지만 **Invoke**.  
  
10. 구현을 완료 하려면 추가 `Dispose()` 및 `TryGetTelemetryId()` 메서드.  
  
    ```csharp  
    public void Dispose()  
    {  
    }  
  
    public bool TryGetTelemetryId(out Guid telemetryId)  
    {  
        // This is a sample action and doesn't participate in LightBulb telemetry  
        telemetryId = Guid.Empty;  
        return false;  
    }  
    ```  
  
11. 에 대 한 동일한 작업을 수행 하도록 설정 `LowerCaseSuggestedAction` 표시 텍스트를 "' {'이 (0) 소문자로 변환"에 대 한 호출은 변경 <xref:System.String.ToUpper%2A> 를 <xref:System.String.ToLower%2A>합니다.  
  
## <a name="building-and-testing-the-code"></a>코드 빌드 및 테스트  
 이 코드를 테스트 하려면 LightBulbTest 솔루션을 빌드하고 실험적 인스턴스에서 실행 합니다.  
  
1.  솔루션을 빌드합니다.  
  
2.  디버거에서 이 프로젝트를 실행하면 Visual Studio의 두 번째 인스턴스가 인스턴스화됩니다.  
  
3.  텍스트 파일을 만들고 일부 텍스트를 입력합니다. 텍스트의 왼쪽에 전구가 나타납니다.  
  
     ![전구 테스트](../extensibility/media/testlightbulb.png "TestLIghtBulb")  
  
4.  전구를 가리키면 됩니다. 아래쪽 화살표를 표시 됩니다.  
  
5.  전구를 클릭 하면 두 가지 권장된 조치를 표시할지 선택한 동작의 미리 보기와 함께 합니다.  
  
     ![확장 된 전구 테스트](../extensibility/media/testlightbulbexpanded.gif "TestLIghtBulbExpanded")  
  
6.  첫 번째 동작을 클릭하면 현재 단어의 모든 텍스트가 대문자로 변환됩니다. 두 번째 동작을 클릭하면 모든 텍스트가 소문자로 변환됩니다.  
  
