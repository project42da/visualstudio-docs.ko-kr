---
title: "연습: 셸 명령을 사용 하 여 편집기 확장명이 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - add a menu command
ms.assetid: 08526848-a442-4cd4-afa1-b2eac2005adb
caps.latest.revision: "46"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b83fe23b830594ac81b489b8f43095c24b29dd7a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-using-a-shell-command-with-an-editor-extension"></a>연습: 셸 명령을 사용 하 여 편집기 확장명이
VSPackage에서 편집기로 메뉴 명령과 같은 기능을 추가할 수 있습니다. 이 연습에 메뉴 명령을 호출 하 여 편집기에서 텍스트 보기로 adornment를 추가 하는 방법을 보여 줍니다.  
  
 이 연습에서는 프레임 워크 MEF (Managed Extensibility) 구성 요소 부분 함께 VSPackage의 사용법을 보여줍니다. Visual Studio 셸을 사용 하 여 메뉴 명령을 등록 하는 VSPackage를 사용 해야 하 고 명령을 사용 하 여 MEF 구성 요소 부분에 액세스할 수 있습니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-an-extension-with-a-menu-command"></a>메뉴 명령을 사용 하 여 확장 만들기  
 명명 된 메뉴 명령을 배치 하는 VSPackage 만들기 **추가 장식** 에 **도구** 메뉴.  
  
1.  라는 C# VSIX 프로젝트를 `MenuCommandTest`, 항목 템플릿 사용자 지정 명령 이름 추가 **AddAdornment**합니다. 자세한 내용은 참조 [메뉴 명령을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-a-menu-command.md)합니다.  
  
2.  MenuCommandTest 라는 솔루션이 열립니다. MenuCommandTestPackage 파일에 메뉴 명령을 만들고에 저장 하는 코드는 **도구** 메뉴. 이 시점에서 명령 메시지 상자를 표시할 수만 하면 됩니다. 이후 단계에는이 주석 장식 표시를 변경 하는 방법을 보여 줍니다.  
  
3.  VSIX 매니페스트 편집기에서 source.extension.vsixmanifest 파일을 엽니다. `Assets` 탭은 Microsoft.VisualStudio.VsPackage MenuCommandTest 명명 된 한 행이 있어야 합니다.  
  
4.  저장 하 고 Source.extension.vsixmanifest 파일을 닫습니다.  
  
## <a name="adding-a-mef-extension-to-the-command-extension"></a>MEF 확장 명령 확장을 추가  
  
1.  **솔루션 탐색기**솔루션 노드를 마우스 오른쪽 단추로 클릭 하 여 **추가**, 클릭 하 고 **새 프로젝트**합니다. 에 **새 프로젝트 추가** 대화 상자를 클릭 **확장성** 아래 **Visual C#**, 다음 **VSIX 프로젝트**합니다. 프로젝트 이름을 `CommentAdornmentTest`로 지정합니다.  
  
2.  이 프로젝트는 VSPackage 강력한 이름의 어셈블리와 상호 작용을 하기 때문에 어셈블리를 서명 해야 합니다. 이미 VSPackage 어셈블리에 대해 만든 키 파일을 다시 사용할 수 있습니다.  
  
    1.  프로젝트 속성을 열고 선택 된 **서명** 탭 합니다.  
  
    2.  선택 **어셈블리에 서명**합니다.  
  
    3.  아래 **강력한 이름 키 파일 선택**, MenuCommandTest 어셈블리에 대 한 생성 된 Key.snk 파일을 선택 합니다.  
  
## <a name="referring-to-the-mef-extension-in-the-vspackage-project"></a>VSPackage 프로젝트에서 MEF 확장 참조  
 MEF 구성 요소를 추가 하는 VSPackage에 있으므로 매니페스트에 두 종류의 자산을 지정 해야 합니다.  
  
> [!NOTE]
>  MEF에 대 한 자세한 내용은 참조 [Framework MEF (Managed Extensibility)](/dotnet/framework/mef/index)합니다.  
  
#### <a name="to-refer-to-the-mef-component-in-the-vspackage-project"></a>VSPackage 프로젝트에 MEF 구성 요소를 참조 하려면  
  
1.  MenuCommandTest 프로젝트에서 VSIX 매니페스트 편집기에서 source.extension.vsixmanifest 파일을 엽니다.  
  
2.  에 **자산** 탭을 클릭 **새로**합니다.  
  
3.  에 **형식** 목록에서 선택 **Microsoft.VisualStudio.MefComponent**합니다.  
  
4.  에 **소스** 목록에서 선택 **현재 솔루션의 프로젝트**합니다.  
  
5.  에 **프로젝트** 목록에서 선택 **CommentAdornmentTest**합니다.  
  
6.  저장 하 고 source.extension.vsixmanifest 파일을 닫습니다.  
  
7.  MenuCommandTest 프로젝트 CommentAdornmentTest 프로젝트에 대 한 참조에 있는지 확인 합니다.  
  
8.  CommentAdornmentTest 프로젝트에서 어셈블리를 생성 하려면 프로젝트를 설정 합니다. 에 **솔루션 탐색기**, 프로젝트를 선택 하 고 찾는 위치는 **속성** 창에는 **OutputDirectory 빌드 출력 복사** 속성을 로설정하고**true**합니다.  
  
## <a name="defining-a-comment-adornment"></a>주석 장식 정의  
 자체 주석 장식 이루어져는 <xref:Microsoft.VisualStudio.Text.ITrackingSpan> 선택한 텍스트와 만든이 및 텍스트에 대 한 설명을 표시 하는 일부 문자열을 추적 하는입니다.  
  
#### <a name="to-define-a-comment-adornment"></a>주석 장식을 정의 하려면  
  
1.  CommentAdornmentTest 프로젝트에서 새 클래스 파일을 추가 하 고 이름을 `CommentAdornment`합니다.  
  
2.  다음 참조를 추가 합니다.  
  
    1.  Microsoft.VisualStudio.CoreUtility  
  
    2.  Microsoft.VisualStudio.Text.Data  
  
    3.  Microsoft.VisualStudio.Text.Logic  
  
    4.  Microsoft.VisualStudio.Text.UI  
  
    5.  Microsoft.VisualStudio.Text.UI.Wpf  
  
    6.  System.ComponentModel.Composition  
  
    7.  PresentationCore  
  
    8.  PresentationFramework  
  
    9. WindowsBase  
  
3.  다음 추가 `using` 문.  
  
    ```vb  
    using Microsoft.VisualStudio.Text;  
    ```  
  
4.  파일 라는 클래스를 포함 해야 `CommentAdornment`합니다.  
  
    ```  
    internal class CommentAdornment  
    ```  
  
5.  세 개의 필드를 추가 하는 `CommentAdornment` 에 대 한 클래스는 <xref:Microsoft.VisualStudio.Text.ITrackingSpan>, 작성자, 설명 및 합니다.  
  
    ```csharp  
    public readonly ITrackingSpan Span;  
    public readonly string Author;  
    public readonly string Text;  
    ```  
  
6.  필드를 초기화 하는 생성자를 추가 합니다.  
  
    ```csharp  
    public CommentAdornment(SnapshotSpan span, string author, string text)  
    {  
        this.Span = span.Snapshot.CreateTrackingSpan(span, SpanTrackingMode.EdgeExclusive);  
        this.Author = author;  
        this.Text = text;  
    }  
    ```  
  
## <a name="creating-a-visual-element-for-the-adornment"></a>장식에 대 한 시각적 요소 만들기  
 도 장식 프로그램에 대 한 시각적 요소를 정의 해야 합니다. 이 연습에서는 Windows Presentation Foundation (WPF) 클래스에서 상속 되는 컨트롤을 정의 <xref:System.Windows.Controls.Canvas>합니다.  
  
1.  CommentAdornmentTest 프로젝트에서 클래스를 만들고 이름을 `CommentBlock`합니다.  
  
2.  다음 `using` 문을 추가합니다.  
  
    ```csharp  
    using Microsoft.VisualStudio.Text;  
    using System;  
    using System.Windows;  
    using System.Windows.Controls;  
    using System.Windows.Media;  
    using System.Windows.Shapes;  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.Utilities;  
    ```  
  
3.  확인 된 `CommentBlock` 클래스에서 상속 <xref:System.Windows.Controls.Canvas>합니다.  
  
    ```csharp  
    internal class CommentBlock : Canvas  
    { }  
    ```  
  
4.  장식의 시각적 측면을 정의 하는 일부 전용 필드를 추가 합니다.  
  
    ```csharp  
    private Geometry textGeometry;  
    private Grid commentGrid;  
    private static Brush brush;  
    private static Pen solidPen;  
    private static Pen dashPen;  
    ```  
  
5.  주석 장식을 정의 하 고 관련 텍스트를 추가 하는 생성자를 추가 합니다.  
  
    ```csharp  
    public CommentBlock(double textRightEdge, double viewRightEdge,   
            Geometry newTextGeometry, string author, string body)  
    {  
        if (brush == null)  
        {  
            brush = new SolidColorBrush(Color.FromArgb(0x20, 0x00, 0xff, 0x00));  
            brush.Freeze();  
            Brush penBrush = new SolidColorBrush(Colors.Green);  
            penBrush.Freeze();  
            solidPen = new Pen(penBrush, 0.5);  
            solidPen.Freeze();  
            dashPen = new Pen(penBrush, 0.5);  
            dashPen.DashStyle = DashStyles.Dash;  
            dashPen.Freeze();  
        }  
  
        this.textGeometry = newTextGeometry;  
  
        TextBlock tb1 = new TextBlock();  
        tb1.Text = author;  
        TextBlock tb2 = new TextBlock();  
        tb2.Text = body;  
  
        const int MarginWidth = 8;  
        this.commentGrid = new Grid();  
        this.commentGrid.RowDefinitions.Add(new RowDefinition());  
        this.commentGrid.RowDefinitions.Add(new RowDefinition());  
        ColumnDefinition cEdge = new ColumnDefinition();  
        cEdge.Width = new GridLength(MarginWidth);  
        ColumnDefinition cEdge2 = new ColumnDefinition();  
        cEdge2.Width = new GridLength(MarginWidth);  
        this.commentGrid.ColumnDefinitions.Add(cEdge);  
        this.commentGrid.ColumnDefinitions.Add(new ColumnDefinition());  
        this.commentGrid.ColumnDefinitions.Add(cEdge2);  
  
        System.Windows.Shapes.Rectangle rect = new System.Windows.Shapes.Rectangle();  
        rect.RadiusX = 6;  
        rect.RadiusY = 3;  
        rect.Fill = brush;  
        rect.Stroke = Brushes.Green;  
  
            Size inf = new Size(double.PositiveInfinity, double.PositiveInfinity);  
            tb1.Measure(inf);  
            tb2.Measure(inf);  
            double middleWidth = Math.Max(tb1.DesiredSize.Width, tb2.DesiredSize.Width);  
            this.commentGrid.Width = middleWidth + 2 * MarginWidth;  
  
        Grid.SetColumn(rect, 0);  
        Grid.SetRow(rect, 0);  
         Grid.SetRowSpan(rect, 2);  
        Grid.SetColumnSpan(rect, 3);  
        Grid.SetRow(tb1, 0);  
        Grid.SetColumn(tb1, 1);  
        Grid.SetRow(tb2, 1);  
        Grid.SetColumn(tb2, 1);  
        this.commentGrid.Children.Add(rect);  
        this.commentGrid.Children.Add(tb1);  
        this.commentGrid.Children.Add(tb2);  
  
        Canvas.SetLeft(this.commentGrid, Math.Max(viewRightEdge - this.commentGrid.Width - 20.0, textRightEdge + 20.0));  
         Canvas.SetTop(this.commentGrid, textGeometry.GetRenderBounds(solidPen).Top);  
  
        this.Children.Add(this.commentGrid);  
    }  
    ```  
  
6.  또한 구현는 <xref:System.Windows.Controls.Panel.OnRender%2A> 장식을 사용 하는 이벤트 처리기입니다.  
  
    ```csharp  
    protected override void OnRender(DrawingContext dc)  
    {  
        base.OnRender(dc);  
        if (this.textGeometry != null)  
        {  
            dc.DrawGeometry(brush, solidPen, this.textGeometry);  
            Rect textBounds = this.textGeometry.GetRenderBounds(solidPen);  
            Point p1 = new Point(textBounds.Right, textBounds.Bottom);  
            Point p2 = new Point(Math.Max(Canvas.GetLeft(this.commentGrid) - 20.0, p1.X), p1.Y);  
            Point p3 = new Point(Math.Max(Canvas.GetLeft(this.commentGrid), p1.X), (Canvas.GetTop(this.commentGrid) + p1.Y) * 0.5);  
            dc.DrawLine(dashPen, p1, p2);  
            dc.DrawLine(dashPen, p2, p3);  
        }  
    }  
    ```  
  
## <a name="adding-an-iwpftextviewcreationlistener"></a>IWpfTextViewCreationListener 추가  
 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener> 는 MEF 구성 요소 파트 만들기 ग द ृ를 수신 대기 하는 데 사용할 수입니다.  
  
1.  CommentAdornmentTest 프로젝트에 클래스 파일을 추가 하 고 이름을 `Connector`합니다.  
  
2.  다음 `using` 문을 추가합니다.  
  
    ```csharp  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.Utilities;  
    ```  
  
3.  구현 하는 클래스 선언 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener>, 및 사용 하 여 내보내기는 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "text"와 <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute> 의 <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Document>합니다. 콘텐츠 형식 특성은 구성 요소가 적용 되는 콘텐츠의 종류를 지정 합니다. 텍스트 형식은 모든 이진이 아닌 파일 형식에 대 한 기본 형식이입니다. 따라서이 유형의 생성은 거의 모든 텍스트 보기가 됩니다. 텍스트 보기의 역할 속성 구성 요소가 적용 되는 텍스트 보기의 종류를 지정 합니다. 문서 텍스트 보기 역할에는 일반적으로 텍스트 줄의 구성 파일에 저장 되며를 보여 줍니다.  
  
     [!code-vb[VSSDKMenuCommandTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-using-a-shell-command-with-an-editor-extension_1.vb)]
     [!code-csharp[VSSDKMenuCommandTest#11](../extensibility/codesnippet/CSharp/walkthrough-using-a-shell-command-with-an-editor-extension_1.cs)]  
  
4.  구현 된 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener.TextViewCreated%2A> 메서드는 정적 호출한 `Create()` 의 이벤트는 `CommentAdornmentManager`합니다.  
  
    ```csharp  
    public void TextViewCreated(IWpfTextView textView)  
    {  
        CommentAdornmentManager.Create(textView);  
    }  
    ```  
  
5.  명령을 실행 하는 데 사용할 수 있는 메서드를 추가 합니다.  
  
    ```csharp  
    static public void Execute(IWpfTextViewHost host)  
    {  
        IWpfTextView view = host.TextView;  
        //Add a comment on the selected text.   
        if (!view.Selection.IsEmpty)  
        {  
            //Get the provider for the comment adornments in the property bag of the view.  
            CommentAdornmentProvider provider = view.Properties.GetProperty<CommentAdornmentProvider>(typeof(CommentAdornmentProvider));  
  
            //Add some arbitrary author and comment text.   
            string author = System.Security.Principal.WindowsIdentity.GetCurrent().Name;  
            string comment = "Four score....";  
  
            //Add the comment adornment using the provider.  
            provider.Add(view.Selection.SelectedSpans[0], author, comment);  
        }  
    }  
    ```  
  
## <a name="defining-an-adornment-layer"></a>표시 계층을 정의합니다.  
 새 장식을 추가 하려면 표시 계층을 정의 해야 합니다.  
  
#### <a name="to-define-an-adornment-layer"></a>표시 계층을 정의 하려면  
  
1.  에 `Connector` 클래스 형식의 공용 필드 선언 <xref:Microsoft.VisualStudio.Text.Editor.AdornmentLayerDefinition>, 및 사용 하 여 내보내기는 <xref:Microsoft.VisualStudio.Utilities.NameAttribute> 표시 계층에 대 한 고유 이름을 지정 하는 및 <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> 다른 텍스트이 표시 계층의 Z 순서 관계를 정의 하는 레이어 (텍스트, 캐럿 및 선택)를 봅니다.  
  
    ```csharp  
    [Export(typeof(AdornmentLayerDefinition))]  
    [Name("CommentAdornmentLayer")]  
    [Order(After = PredefinedAdornmentLayers.Selection, Before = PredefinedAdornmentLayers.Text)]  
    public AdornmentLayerDefinition commentLayerDefinition;  
  
    ```  
  
## <a name="providing-comment-adornments"></a>주석 장식을 제공합니다.  
 Adornment를 정의할 때에 주석 장식 공급자 및 주석 장식 관리자 구현도 합니다. 주석 장식 공급자 주석 장식의 목록을 유지를 수신 대기 <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> 내부 텍스트 버퍼 및 기본 텍스트 삭제 하면 삭제 주석 장식을에서 이벤트입니다.  
  
1.  CommentAdornmentTest 프로젝트에 새 클래스 파일을 추가 하 고 이름을 `CommentAdornmentProvider`합니다.  
  
2.  다음 `using` 문을 추가합니다.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Collections.ObjectModel;  
    using Microsoft.VisualStudio.Text;  
    using Microsoft.VisualStudio.Text.Editor;  
    ```  
  
3.  라는 클래스를 추가 `CommentAdornmentProvider`합니다.  
  
    ```csharp  
    internal class CommentAdornmentProvider  
    {  
    }  
    ```  
  
4.  텍스트 버퍼와 버퍼와 관련 된 주석 장식 목록에 대 한 전용 필드를 추가 합니다.  
  
    ```csharp  
    private ITextBuffer buffer;  
    private IList<CommentAdornment> comments = new List<CommentAdornment>();  
  
    ```  
  
5.  에 대 한 생성자를 추가 `CommentAdornmentProvider`합니다. 공급자에 의해 인스턴스화됩니다 때문에이 생성자 개인 액세스할 수 있어야는 `Create()` 메서드. 추가 하는 생성자는 `OnBufferChanged` 를 이벤트 처리기는 <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> 이벤트입니다.  
  
    ```csharp  
    private CommentAdornmentProvider(ITextBuffer buffer)  
    {  
        this.buffer = buffer;  
        //listen to the Changed event so we can react to deletions.   
        this.buffer.Changed += OnBufferChanged;  
    }  
  
    ```  
  
6.  `Create()` 메서드를 추가합니다.  
  
    ```csharp  
    public static CommentAdornmentProvider Create(IWpfTextView view)  
    {  
        return view.Properties.GetOrCreateSingletonProperty<CommentAdornmentProvider>(delegate { return new CommentAdornmentProvider(view.TextBuffer); });  
    }  
  
    ```  
  
7.  `Detach()` 메서드를 추가합니다.  
  
    ```csharp  
    public void Detach()  
    {  
        if (this.buffer != null)  
        {  
            //remove the Changed listener   
            this.buffer.Changed -= OnBufferChanged;  
            this.buffer = null;  
        }  
    }  
    ```  
  
8.  추가 된 `OnBufferChanged` 이벤트 처리기입니다.  
  
    ```csharp  
    private void OnBufferChanged(object sender, TextContentChangedEventArgs e)  
    {  
        //Make a list of all comments that have a span of at least one character after applying the change. There is no need to raise a changed event for the deleted adornments. The adornments are deleted only if a text change would cause the view to reformat the line and discard the adornments.  
        IList<CommentAdornment> keptComments = new List<CommentAdornment>(this.comments.Count);  
  
        foreach (CommentAdornment comment in this.comments)  
        {  
            Span span = comment.Span.GetSpan(e.After);  
            //if a comment does not span at least one character, its text was deleted.   
            if (span.Length != 0)  
            {  
                keptComments.Add(comment);  
            }  
        }  
  
        this.comments = keptComments;  
    }  
  
    ```  
  
     [!code-csharp[VSSDKMenuCommandTest#21](../extensibility/codesnippet/CSharp/walkthrough-using-a-shell-command-with-an-editor-extension_2.cs)]
     [!code-vb[VSSDKMenuCommandTest#21](../extensibility/codesnippet/VisualBasic/walkthrough-using-a-shell-command-with-an-editor-extension_2.vb)]  
  
9. 에 대 한 선언을 추가 `CommentsChanged` 이벤트입니다.  
  
    ```csharp  
    public event EventHandler<CommentsChangedEventArgs> CommentsChanged;  
    ```  
  
10. 만들기는 `Add()` 메서드를 장식을 추가 합니다.  
  
    ```csharp  
    public void Add(SnapshotSpan span, string author, string text)  
    {  
        if (span.Length == 0)  
            throw new ArgumentOutOfRangeException("span");  
        if (author == null)  
            throw new ArgumentNullException("author");  
        if (text == null)  
            throw new ArgumentNullException("text");  
  
        //Create a comment adornment given the span, author and text.  
        CommentAdornment comment = new CommentAdornment(span, author, text);  
  
        //Add it to the list of comments.   
        this.comments.Add(comment);  
  
        //Raise the changed event.  
        EventHandler<CommentsChangedEventArgs> commentsChanged = this.CommentsChanged;  
        if (commentsChanged != null)  
            commentsChanged(this, new CommentsChangedEventArgs(comment, null));  
    }  
  
    ```  
  
11. 추가 `RemoveComments()` 메서드.  
  
    ```csharp  
    public void RemoveComments(SnapshotSpan span)  
    {  
        EventHandler<CommentsChangedEventArgs> commentsChanged = this.CommentsChanged;  
  
        //Get a list of all the comments that are being kept   
        IList<CommentAdornment> keptComments = new List<CommentAdornment>(this.comments.Count);  
  
        foreach (CommentAdornment comment in this.comments)  
        {  
            //find out if the given span overlaps with the comment text span. If two spans are adjacent, they do not overlap. To consider adjacent spans, use IntersectsWith.   
            if (comment.Span.GetSpan(span.Snapshot).OverlapsWith(span))  
            {  
                //Raise the change event to delete this comment.   
                if (commentsChanged != null)  
                    commentsChanged(this, new CommentsChangedEventArgs(null, comment));  
            }  
            else  
                keptComments.Add(comment);  
        }  
  
        this.comments = keptComments;  
    }  
    ```  
  
12. 추가 `GetComments()` 주어진된 스냅숏 범위에서 모든 메모를 반환 하는 메서드.  
  
    ```csharp  
    public Collection<CommentAdornment> GetComments(SnapshotSpan span)  
    {  
        IList<CommentAdornment> overlappingComments = new List<CommentAdornment>();  
        foreach (CommentAdornment comment in this.comments)  
        {  
            if (comment.Span.GetSpan(span.Snapshot).OverlapsWith(span))  
                overlappingComments.Add(comment);  
        }  
  
        return new Collection<CommentAdornment>(overlappingComments);  
    }  
    ```  
  
13. 라는 클래스를 추가 `CommentsChangedEventArgs`다음과 같이 합니다.  
  
    ```csharp  
    internal class CommentsChangedEventArgs : EventArgs  
    {  
        public readonly CommentAdornment CommentAdded;  
  
        public readonly CommentAdornment CommentRemoved;  
  
        public CommentsChangedEventArgs(CommentAdornment added, CommentAdornment removed)  
        {  
            this.CommentAdded = added;  
            this.CommentRemoved = removed;  
        }  
    }  
    ```  
  
## <a name="managing-comment-adornments"></a>주석 장식을 관리  
 주석 장식 관리자 장식 만들고 표시 계층에 추가 합니다. 수신 하는 <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> 및 <xref:Microsoft.VisualStudio.Text.Editor.ITextView.Closed> 이벤트를 이동 하거나 장식 삭제할 수 있습니다. 또한를 수신 대기는 `CommentsChanged` 의견을 추가 하거나 제거할 때 주석 장식 공급자에 의해 발생 하는 이벤트입니다.  
  
1.  CommentAdornmentTest 프로젝트에 클래스 파일을 추가 하 고 이름을 `CommentAdornmentManager`합니다.  
  
2.  다음 `using` 문을 추가합니다.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Windows.Media;  
    using Microsoft.VisualStudio.Text;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.Text.Formatting;  
    ```  
  
3.  라는 클래스를 추가 `CommentAdornmentManager`합니다.  
  
    ```csharp  
    internal class CommentAdornmentManager  
        {  
        }  
    ```  
  
4.  일부 전용 필드를 추가 합니다.  
  
    ```csharp  
    private readonly IWpfTextView view;  
    private readonly IAdornmentLayer layer;  
    private readonly CommentAdornmentProvider provider;  
    ```  
  
5.  관리자를 구독 하는 생성자를 추가 <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> 및 <xref:Microsoft.VisualStudio.Text.Editor.ITextView.Closed> 이벤트도는 `CommentsChanged` 이벤트입니다. 관리자는 정적 인스턴스화될 때문에 생성자가 private `Create()` 메서드.  
  
    ```csharp  
    private CommentAdornmentManager(IWpfTextView view)  
    {  
        this.view = view;  
        this.view.LayoutChanged += OnLayoutChanged;  
        this.view.Closed += OnClosed;  
  
        this.layer = view.GetAdornmentLayer("CommentAdornmentLayer");  
  
        this.provider = CommentAdornmentProvider.Create(view);  
        this.provider.CommentsChanged += OnCommentsChanged;  
    }  
    ```  
  
6.  추가 된 `Create()` 를 공급자 가져오는 하거나 필요한 경우 새로 만듭니다.  
  
    ```csharp  
    public static CommentAdornmentManager Create(IWpfTextView view)  
    {  
        return view.Properties.GetOrCreateSingletonProperty<CommentAdornmentManager>(delegate { return new CommentAdornmentManager(view); });  
    }  
    ```  
  
7.  추가 된 `CommentsChanged` 처리기입니다.  
  
    ```csharp  
    private void OnCommentsChanged(object sender, CommentsChangedEventArgs e)  
    {  
        //Remove the comment (when the adornment was added, the comment adornment was used as the tag).   
        if (e.CommentRemoved != null)  
            this.layer.RemoveAdornmentsByTag(e.CommentRemoved);  
  
        //Draw the newly added comment (this will appear immediately: the view does not need to do a layout).   
        if (e.CommentAdded != null)  
            this.DrawComment(e.CommentAdded);  
    }  
    ```  
  
8.  추가 된 <xref:Microsoft.VisualStudio.Text.Editor.ITextView.Closed> 처리기입니다.  
  
    ```csharp  
    private void OnClosed(object sender, EventArgs e)  
    {  
        this.provider.Detach();  
        this.view.LayoutChanged -= OnLayoutChanged;  
        this.view.Closed -= OnClosed;  
    }  
    ```  
  
9. 추가 된 <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> 처리기입니다.  
  
    ```csharp  
    private void OnLayoutChanged(object sender, TextViewLayoutChangedEventArgs e)  
    {  
        //Get all of the comments that intersect any of the new or reformatted lines of text.  
        List<CommentAdornment> newComments = new List<CommentAdornment>();  
  
        //The event args contain a list of modified lines and a NormalizedSpanCollection of the spans of the modified lines.    
        //Use the latter to find the comments that intersect the new or reformatted lines of text.   
        foreach (Span span in e.NewOrReformattedSpans)  
        {  
            newComments.AddRange(this.provider.GetComments(new SnapshotSpan(this.view.TextSnapshot, span)));  
        }  
  
        //It is possible to get duplicates in this list if a comment spanned 3 lines, and the first and last lines were modified but the middle line was not.   
        //Sort the list and skip duplicates.  
        newComments.Sort(delegate(CommentAdornment a, CommentAdornment b) { return a.GetHashCode().CompareTo(b.GetHashCode()); });  
  
        CommentAdornment lastComment = null;  
        foreach (CommentAdornment comment in newComments)  
        {  
            if (comment != lastComment)  
            {  
                lastComment = comment;  
                this.DrawComment(comment);  
            }  
        }  
    }  
    ```  
  
10. 메모를 그릴 수 있는 전용 메서드에 추가 합니다.  
  
     [!code-csharp[VSSDKMenuCommandTest#35](../extensibility/codesnippet/CSharp/walkthrough-using-a-shell-command-with-an-editor-extension_3.cs)]
     [!code-vb[VSSDKMenuCommandTest#35](../extensibility/codesnippet/VisualBasic/walkthrough-using-a-shell-command-with-an-editor-extension_3.vb)]  
  
## <a name="using-the-menu-command-to-add-the-comment-adornment"></a>주석 장식 추가할 메뉴 명령을 사용 하 여  
 메뉴 명령을 사용 하 여 구현 하 여 주석 장식을 만들 수 있습니다는 `MenuItemCallback` vspackage 메서드.  
  
1.  MenuCommandTest 프로젝트에 다음 참조를 추가 합니다.  
  
    -   Microsoft.VisualStudio.TextManager.Interop  
  
    -   Microsoft.VisualStudio.Editor  
  
    -   Microsoft.VisualStudio.Text.UI.Wpf  
  
2.  AddAdornment.cs 파일을 열고 다음 추가 `using` 문.  
  
    ```csharp  
    using Microsoft.VisualStudio.TextManager.Interop;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.Editor;  
    using CommentAdornmentTest;  
    ```  
  
3.  ShowMessageBox() 메서드를 삭제 하 고 다음 명령 처리기를 추가 합니다.  
  
    ```csharp  
    private void AddAdornmentHandler(object sender, EventArgs e)  
    {  
    }  
    ```  
  
4.  현재 보기를 가져오는 코드를 추가 합니다. 가져와야 하는 `SVsTextManager` 활성을 얻으려고 하면 Visual Studio 셸을 `IVsTextView`합니다.  
  
    ```csharp  
    private void AddAdornmentHandler(object sender, EventArgs e)  
    {  
        IVsTextManager txtMgr = (IVsTextManager)ServiceProvider.GetService(typeof(SVsTextManager));  
        IVsTextView vTextView = null;  
        int mustHaveFocus = 1;  
        txtMgr.GetActiveView(mustHaveFocus, null, out vTextView);  
    }  
    ```  
  
5.  이 텍스트 보기는 편집기 텍스트 보기의 인스턴스를 캐스팅할 수 있습니다 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData> 인터페이스를 가져온 후의 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> 및 관련 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView>합니다. 사용 하 여는 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> 호출 하 여 `Connector.Execute()` 메서드를 장식 하 주석 장식 공급자를 가져옵니다. 명령 처리기는 이제 다음과 같이 표시 됩니다.  
  
    ```csharp  
    private void AddAdornmentHandler(object sender, EventArgs e)  
    {  
        IVsTextManager txtMgr = (IVsTextManager)ServiceProvider.GetService(typeof(SVsTextManager));  
        IVsTextView vTextView = null;  
        int mustHaveFocus = 1;  
        txtMgr.GetActiveView(mustHaveFocus, null, out vTextView);  
        IVsUserData userData = vTextView as IVsUserData;  
         if (userData == null)  
        {  
            Console.WriteLine("No text view is currently open");  
                            return;  
        }  
        IWpfTextViewHost viewHost;  
        object holder;  
        Guid guidViewHost = DefGuidList.guidIWpfTextViewHost;  
        userData.GetData(ref guidViewHost, out holder);  
        viewHost = (IWpfTextViewHost)holder;  
        Connector.Execute(viewHost);  
    }  
    ```  
  
6.  AddAdornmentHandler 메서드 AddAdornment 생성자에서 AddAdornment 명령에 대 한 처리기로 설정 합니다.  
  
    ```csharp  
    private AddAdornment(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException(nameof(package));  
        }  
  
        this.package = package;  
  
        OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            CommandID menuCommandID = new CommandID(MenuGroup, CommandId);  
            EventHandler eventHandler = this.AddAdornmentHandler;  
            MenuCommand menuItem = new MenuCommand(eventHandler, menuCommandID);  
            commandService.AddCommand(menuItem);  
        }  
    }  
    ```  
  
## <a name="building-and-testing-the-code"></a>코드 빌드 및 테스트  
  
1.  솔루션을 빌드하고 디버깅을 시작합니다. 실험적 인스턴스 표시 되어야 합니다.  
  
2.  텍스트 파일을 만듭니다. 텍스트를 입력 한 다음 선택 합니다.  
  
3.  에 **도구** 메뉴를 클릭 하 여 **추가 장식 호출**합니다. 풍선은 텍스트 창의 오른쪽에 표시 되 고 다음 텍스트와 비슷한 텍스트가 포함 되어야 합니다.  
  
     YourUserName  
  
     Fourscore...  
  
## <a name="see-also"></a>참고 항목  
 [연습: 파일 이름 확장명에 콘텐츠 형식 연결](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)