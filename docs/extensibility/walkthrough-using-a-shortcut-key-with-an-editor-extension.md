---
title: '연습: 바로 가기 키를 사용 하 여 편집기 확장명이 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - link keystrokes to commands
ms.assetid: cf6cc6c6-5a65-4f90-8f14-663decf74672
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f8f8a310832f0691b4bc4056baddeb1fbbad78f8
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="walkthrough-using-a-shortcut-key-with-an-editor-extension"></a>연습: 바로 가기 키를 사용 하 여 편집기 확장명이
편집기 확장에 바로 가기 키에 응답할 수 있습니다. 다음 바로 가기 키를 사용 하 여 보기 장식 텍스트 보기에 추가 하는 방법을 보여 줍니다. 이 연습에서는 뷰포트 장식 편집기 템플릿을 기반으로 하며 장식을 사용 하 여 추가할 수는 + 문자가 있습니다.  
  
## <a name="prerequisites"></a>전제 조건  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-a-managed-extensibility-framework-mef-project"></a>MEF(Managed Extensibility Framework) 프로젝트 만들기  
  
1.  C# VSIX 프로젝트를 만듭니다. (에 **새 프로젝트** 대화 상자에서 **Visual C# / 확장성**, 다음 **VSIX 프로젝트**.) 솔루션 이름을 `KeyBindingTest`합니다.  
  
2.  편집기 텍스트 장식 항목 템플릿을 프로젝트에 추가 하 고 이름을 `KeyBindingTest`합니다. 자세한 내용은 참조 [편집기 항목 템플릿을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-an-editor-item-template.md)합니다.  
  
3.  다음 참조를 추가 하 고 설정 **CopyLocal** 를 `false`:  
  
     Microsoft.VisualStudio.Editor  
  
     Microsoft.VisualStudio.OLE.Interop  
  
     Microsoft.VisualStudio.Shell.14.0  
  
     Microsoft.VisualStudio.TextManager.Interop  
  
 KeyBindingTest 클래스 파일에서 클래스 이름을 PurpleCornerBox로 바꿉니다. 왼쪽된 여백에 표시 된 전구를 사용 하 여 적절 하 게 다른 변경 합니다. 생성자 내부 장식 계층의 이름을 변경 **KeyBindingTest** 를 **PurpleCornerBox**:  
  
```csharp  
this.layer = view.GetAdornmentLayer("PurpleCornerBox");  
```  

KeyBindingTestTextViewCreationListener.cs 클래스 파일에서에서 AdornmentLayer의 이름을 변경 **KeyBindingTest** 를 **PurpleCornerBox**:
  
    ```csharp  
    [Export(typeof(AdornmentLayerDefinition))]  
    [Name("PurpleCornerBox")]  
    [Order(After = PredefinedAdornmentLayers.Selection, Before = PredefinedAdornmentLayers.Text)]  
    public AdornmentLayerDefinition editorAdornmentLayer;  
    ```  

## <a name="handling-typechar-command"></a>TYPECHAR 명령 처리
Visual Studio 2017 버전 15.6 편집기 확장에서 명령을 처리 하는 유일한 방법은 구현 하기 전에 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 명령 필터를 기반으로 합니다. Visual Studio 2017 버전 15.6 편집기 명령 처리기에 따라 최신 간단한 접근 방법을 도입 되었습니다. 다음 두 섹션 모두 레거시 및 최신 접근 방식을 사용 하 여 명령을 처리 하는 방법을 보여 줍니다.

## <a name="defining-the-command-filter-prior-to-visual-studio-2017-version-156"></a>(이전 Visual Studio 2017 버전 15.6) 명령 필터를 정의합니다.

 명령 필터는의 구현 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>, 장식 인스턴스화하여 명령을 처리 합니다.  
  
1.  클래스 파일을 추가 하 고 이름을 `KeyBindingCommandFilter`합니다.  
  
2.  다음 using 문을 추가합니다.  
  
    ```csharp  
    using System;  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio.OLE.Interop;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Text.Editor;  
  
    ```  
  
3.  KeyBindingCommandFilter 이름의 클래스에서 상속 해야 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>합니다.  
  
    ```csharp  
    internal class KeyBindingCommandFilter : IOleCommandTarget  
    ```  
  
4.  명령 체인 및 명령 필터가 이미 추가 되어 있는지 여부를 나타내는 플래그의 텍스트 보기에 대 한 전용 필드, 다음 명령을 추가 합니다.  
  
    ```csharp  
    private IWpfTextView m_textView;  
    internal IOleCommandTarget m_nextTarget;  
    internal bool m_added;  
    internal bool m_adorned;  
    ```  
  
5.  텍스트 보기를 설정 하는 생성자를 추가 합니다.  
  
    ```csharp  
    public KeyBindingCommandFilter(IWpfTextView textView)  
    {  
        m_textView = textView;  
        m_adorned = false;  
    }  
    ```  
  
6.  구현 된 `QueryStatus()` 메서드를 다음과 같이 합니다.  
  
    ```csharp  
    int IOleCommandTarget.QueryStatus(ref Guid pguidCmdGroup, uint cCmds, OLECMD[] prgCmds, IntPtr pCmdText)  
    {  
        return m_nextTarget.QueryStatus(ref pguidCmdGroup, cCmds, prgCmds, pCmdText);  
    }  
    ```  
  
7.  구현 된 `Exec()` 추가 하도록 자주색 상자 보기로 경우 메서드는 + 문자를 입력 합니다.  
  
    ```csharp  
    int IOleCommandTarget.Exec(ref Guid pguidCmdGroup, uint nCmdID, uint nCmdexecopt, IntPtr pvaIn, IntPtr pvaOut)  
    {  
        if (m_adorned == false)  
        {  
            char typedChar = char.MinValue;  
  
            if (pguidCmdGroup == VSConstants.VSStd2K && nCmdID == (uint)VSConstants.VSStd2KCmdID.TYPECHAR)  
            {  
                typedChar = (char)(ushort)Marshal.GetObjectForNativeVariant(pvaIn);  
                if (typedChar.Equals('+'))  
                {  
                    new PurpleCornerBox(m_textView);  
                    m_adorned = true;  
                }  
            }  
        }  
        return m_nextTarget.Exec(ref pguidCmdGroup, nCmdID, nCmdexecopt, pvaIn, pvaOut);  
    }  
  
    ```  
  
## <a name="adding-the-command-filter-prior-to-visual-studio-2017-version-156"></a>Visual Studio 2017 버전 15.6) (이전 명령 필터 추가
 텍스트 보기 장식 공급자 명령 필터를 추가 해야 합니다. 이 예제에서는 공급자 구현 <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> 텍스트 보기 생성 이벤트를 수신 대기 하도록 합니다. 또한이 장식 공급자 장식의 Z 순서를 정의 하는 장식 계층을 내보냅니다.  
  
1.  KeyBindingTestTextViewCreationListener 파일에 다음 추가 문을 사용 하 여:  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.OLE.Interop;  
    using Microsoft.VisualStudio.Utilities;  
    using Microsoft.VisualStudio.Editor;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.TextManager.Interop;  
  
    ```  
  
2.  텍스트 보기 어댑터를 가져오려면 가져와야는 <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService>합니다.  
  
    ```csharp  
    [Import(typeof(IVsEditorAdaptersFactoryService))]  
    internal IVsEditorAdaptersFactoryService editorFactory = null;  
  
    ```  
  
3.  변경 된 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener.TextViewCreated%2A> 추가 하도록 하는 메서드는 `KeyBindingCommandFilter`합니다.  
  
    ```csharp  
    public void TextViewCreated(IWpfTextView textView)  
    {  
        AddCommandFilter(textView, new KeyBindingCommandFilter(textView));  
    }  
    ```  
  
4.  `AddCommandFilter` 처리기 텍스트 뷰 어댑터를 가져오고 명령 필터를 추가 합니다.  
  
    ```csharp  
    void AddCommandFilter(IWpfTextView textView, KeyBindingCommandFilter commandFilter)  
    {  
        if (commandFilter.m_added == false)  
        {  
            //get the view adapter from the editor factory  
            IOleCommandTarget next;   
            IVsTextView view = editorFactory.GetViewAdapter(textView);  
  
            int hr = view.AddCommandFilter(commandFilter, out next);  
  
            if (hr == VSConstants.S_OK)  
            {      
                commandFilter.m_added = true;  
                 //you'll need the next target for Exec and QueryStatus   
                if (next != null)  
                commandFilter.m_nextTarget = next;  
            }  
        }  
    }  
    ```  

## <a name="implement-a-command-handler-starting-in-visual-studio-2017-version-156"></a>(Visual Studio 2017 15.6 버전부터) 명령 처리기를 구현 합니다.

첫째, 최신 편집기 API를 참조 하는 프로젝트의 Nuget 참조를 업데이트 합니다.

1. 선택한 프로젝트를 마우스 오른쪽 단추로 클릭 **Nuget 패키지 관리**합니다.

2. **Nuget 패키지 관리자**선택는 **업데이트** 탭을는 **모든 패키지를 선택** 확인란을 선택한 후 **업데이트**합니다.

명령 처리기는의 구현 <xref:Microsoft.VisualStudio.Commanding.ICommandHandler%601>, 장식 인스턴스화하여 명령을 처리 합니다.  
  
1.  클래스 파일을 추가 하 고 이름을 `KeyBindingCommandHandler`합니다.  
  
2.  다음 using 문을 추가합니다.  
  
    ```csharp  
    using Microsoft.VisualStudio.Commanding;
    using Microsoft.VisualStudio.Text.Editor;
    using Microsoft.VisualStudio.Text.Editor.Commanding.Commands;
    using Microsoft.VisualStudio.Utilities;
    using System.ComponentModel.Composition;   
    ```  
  
3.  KeyBindingCommandHandler 이름의 클래스에서 상속 해야 `ICommandHandler<TypeCharCommandArgs>`를 및로 내보내기 <xref:Microsoft.VisualStudio.Commanding.ICommandHandler>:
  
    ```csharp  
    [Export(typeof(ICommandHandler))]
    [ContentType("text")]
    [Name("KeyBindingTest")]
    internal class KeyBindingCommandHandler : ICommandHandler<TypeCharCommandArgs>  
    ```  
  
4.  명령 처리기의 표시 이름을 추가 합니다.  
  
    ```csharp  
    public string DisplayName => "KeyBindingTest";
    ```  
    
5.  구현 된 `GetCommandState()` 메서드를 다음과 같이 합니다. 이 명령 처리기에서 코어 편집기 TYPECHAR 명령을 처리 하므로 코어 편집기 명령을 사용 하도록 설정 하기를 위임할 수 있습니다.
  
    ```csharp  
    public CommandState GetCommandState(TypeCharCommandArgs args)
    {
        return CommandState.Unspecified;
    } 
    ```  
  
6.  구현 된 `ExecuteCommand()` 추가 하도록 자주색 상자 보기로 경우 메서드는 + 문자를 입력 합니다. 
  
    ```csharp  
    public bool ExecuteCommand(TypeCharCommandArgs args, CommandExecutionContext executionContext)
    {
        if (args.TypedChar == '+')
        {
            bool alreadyAdorned = args.TextView.Properties.TryGetProperty(
                "KeyBindingTextAdorned", out bool adorned) && adorned;
            if (!alreadyAdorned)
            {
                new PurpleCornerBox((IWpfTextView)args.TextView);
                args.TextView.Properties.AddProperty("KeyBindingTextAdorned", true);
            }
        }

        return false;
    }
    ```  
 7. KeyBindingCommandHandler.cs을 장식 계층 정의 KeyBindingTestTextViewCreationListener.cs 파일에서 복사한 다음 KeyBindingTestTextViewCreationListener.cs 파일을 삭제 합니다.
 
    ```csharp  
    /// <summary>
    /// Defines the adornment layer for the adornment. This layer is ordered
    /// after the selection layer in the Z-order.
    /// </summary>
    [Export(typeof(AdornmentLayerDefinition))]
    [Name("PurpleCornerBox")]
    [Order(After = PredefinedAdornmentLayers.Selection, Before = PredefinedAdornmentLayers.Text)]
    private AdornmentLayerDefinition editorAdornmentLayer;    
    ```  

## <a name="making-the-adornment-appear-on-every-line"></a>장식 만드는 모든 줄에 표시  

모든 문자에 나타난 원래 장식 텍스트 파일에서 ' a'입니다. 줄에만 장식 추가 장식 '+' 문자에 대 한 응답에 추가 하는 코드를 변경 했습니다 했으므로 위치는 '+'를 입력 합니다. 한 번 더 장식에 나타나도록 장식 코드 변경할 수 있습니다 모든 'a'입니다.  
  
KeyBindingTest.cs 파일에서 'a' 문자를 데코레이팅하 보기에서 모든 줄을 반복 하 CreateVisuals() 메서드를 변경 합니다.  
  
```csharp  
private void CreateVisuals(ITextViewLine line)  
{  
    IWpfTextViewLineCollection textViewLines = this.view.TextViewLines;  
  
    foreach (ITextViewLine textViewLine in textViewLines)  
    {  
        if (textViewLine.ToString().Contains("a"))  
        {  
            // Loop through each character, and place a box around any 'a'   
            for (int charIndex = textViewLine.Start; charIndex < textViewLine.End; charIndex++)  
            {  
                if (this.view.TextSnapshot[charIndex] == 'a')  
                {  
                    SnapshotSpan span = new SnapshotSpan(this.view.TextSnapshot, Span.FromBounds(charIndex, charIndex + 1));  
                    Geometry geometry = textViewLines.GetMarkerGeometry(span);  
                    if (geometry != null)  
                    {  
                        var drawing = new GeometryDrawing(this.brush, this.pen, geometry);  
                        drawing.Freeze();  
  
                        var drawingImage = new DrawingImage(drawing);  
                        drawingImage.Freeze();  
  
                        var image = new Image  
                        {  
                            Source = drawingImage,  
                        };  
  
                        // Align the image with the top of the bounds of the text geometry  
                        Canvas.SetLeft(image, geometry.Bounds.Left);  
                        Canvas.SetTop(image, geometry.Bounds.Top);  
  
                        this.layer.AddAdornment(AdornmentPositioningBehavior.TextRelative, span, null, image, null);  
                    }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="building-and-testing-the-code"></a>코드 빌드 및 테스트  
  
1.  KeyBindingTest 솔루션을 빌드하고 실험적 인스턴스에서 실행 합니다.  
  
2.  텍스트 파일을 열거나 만듭니다. 문자를 포함 하는 일부 단어를 입력 합니다. 'a', 한 다음 입력 + 텍스트 보기에서 아무 곳 이나 합니다.  
  
     자주색 사각형 파일에서 'a' 모든 문자에 나타나야 합니다.
