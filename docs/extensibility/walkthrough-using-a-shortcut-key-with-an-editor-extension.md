---
title: "연습: 편집기 확장에 바로 가기 키 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK], 명령에 키 입력을 신규-연결"
ms.assetid: cf6cc6c6-5a65-4f90-8f14-663decf74672
caps.latest.revision: 32
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 32
---
# 연습: 편집기 확장에 바로 가기 키 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

편집기 확장에 바로 가기 키에 응답할 수 있습니다. 다음 연습에서는 바로 가기 키를 사용 하 여 보기 장식 텍스트 뷰를 추가 하는 방법을 보여 줍니다. 이 연습에서는 뷰포트 장식 편집기 서식 파일에 기반으로 하며 장식을 사용 하 여 추가할 수는 \+ 문자입니다.  
  
## 사전 요구 사항  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하세요.  
  
## MEF\(Managed Extensibility Framework\) 프로젝트 만들기  
  
1.  C\# VSIX 프로젝트를 만듭니다. \(에 **새 프로젝트** 대화 상자에서 **Visual C\# \/ 확장성**, 다음 **VSIX 프로젝트**.\) 솔루션의 이름을 `KeyBindingTest`합니다.  
  
2.  편집기 텍스트 장식 항목 템플릿을 프로젝트에 추가 하 고 이름을 `KeyBindingTest`합니다. 자세한 내용은 [편집기 항목 템플릿을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-an-editor-item-template.md)을 참조하십시오.  
  
3.  다음 참조를 추가 하 고 설정 **{2\>copylocal** 를 `false`:  
  
     Microsoft.VisualStudio.Editor  
  
     Microsoft.VisualStudio.OLE.Interop  
  
     Microsoft.VisualStudio.Shell.14.0  
  
     Microsoft.VisualStudio.TextManager.Interop  
  
 KeyBindingTest 클래스 파일에서 PurpleCornerBox에 클래스 이름을 변경 합니다. 왼쪽된 여백에 표시 된 전구를 사용 하 여 적절 하 게 다른 변경 합니다. 생성자 내부에서 장식 계층의 이름을 변경 **KeyBindingTest** 를 **PurpleCornerBox**:  
  
```c#  
this.layer = view.GetAdornmentLayer("PurpleCornerBox");  
```  
  
## 명령 필터를 정의합니다.  
 명령 필터의 구현인 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>, 장식 인스턴스화하여 명령의 처리 합니다.  
  
1.  클래스 파일을 추가 하 고 이름을 `KeyBindingCommandFilter`합니다.  
  
2.  다음 using 문을 추가합니다.  
  
    ```c#  
    using System;  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio.OLE.Interop;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Text.Editor;  
  
    ```  
  
3.  KeyBindingCommandFilter 라는 클래스에서 상속 해야 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>합니다.  
  
    ```c#  
    internal class KeyBindingCommandFilter : IOleCommandTarget  
    ```  
  
4.  명령 체인 및 명령 필터가 이미 추가 되어 있는지 여부를 나타내는 플래그의 텍스트 보기에 대 한 전용 필드, 다음 명령을 추가 합니다.  
  
    ```c#  
    private IWpfTextView m_textView;  
    internal IOleCommandTarget m_nextTarget;  
    internal bool m_added;  
    internal bool m_adorned;  
    ```  
  
5.  텍스트 뷰를 설정 하는 생성자를 추가 합니다.  
  
    ```c#  
    public KeyBindingCommandFilter(IWpfTextView textView)  
    {  
        m_textView = textView;  
        m_adorned = false;  
    }  
    ```  
  
6.  구현 된 `QueryStatus()` 메서드를 다음과 같이 합니다.  
  
    ```vb  
    int IOleCommandTarget.QueryStatus(ref Guid pguidCmdGroup, uint cCmds, OLECMD[] prgCmds, IntPtr pCmdText)  
    {  
        return m_nextTarget.QueryStatus(ref pguidCmdGroup, cCmds, prgCmds, pCmdText);  
    }  
    ```  
  
7.  구현 된 `Exec()` 한다는 자주색 상자 보기에 추가 하는 경우 메서드는 \+ 문자를 입력 합니다.  
  
    ```c#  
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
  
## 명령 필터를 추가합니다.  
 텍스트 장식 공급자 명령 필터를 추가 해야 합니다. 이 예제에서는 공급자 구현 <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> 텍스트 보기 생성 이벤트를 수신 대기 합니다. 또한이 장식 공급자 장식의 Z 순서를 정의 하는 장식 계층을 내보냅니다.  
  
1.  KeyBindingTestTextViewCreationListener 파일에서 다음 추가 문을 사용 하 여:  
  
    ```c#  
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
  
2.  장식 계층 정의 AdornmentLayer의 이름을 변경 **KeyBindingTest** 를 **PurpleCornerBox**합니다.  
  
    ```c#  
    [Export(typeof(AdornmentLayerDefinition))]  
    [Name("PurpleCornerBox")]  
    [Order(After = PredefinedAdornmentLayers.Selection, Before = PredefinedAdornmentLayers.Text)]  
    public AdornmentLayerDefinition editorAdornmentLayer;  
    ```  
  
3.  텍스트 뷰 어댑터를 가져오려면 가져와야는 <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService>합니다.  
  
    ```c#  
    [Import(typeof(IVsEditorAdaptersFactoryService))]  
    internal IVsEditorAdaptersFactoryService editorFactory = null;  
  
    ```  
  
4.  변경 된 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener.TextViewCreated%2A> 추가 하도록 메서드는 `KeyBindingCommandFilter`합니다.  
  
    ```c#  
    public void TextViewCreated(IWpfTextView textView)  
    {  
        AddCommandFilter(textView, new KeyBindingCommandFilter(textView));  
    }  
    ```  
  
5.  `AddCommandFilter` 처리기가 텍스트 뷰 어댑터를 가져오고 명령 필터를 추가 합니다.  
  
    ```c#  
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
  
## 장식 만드는 모든 줄에 표시  
 모든 문자에 나타난 원래 장식 텍스트 파일에 ' a'입니다. 줄에 대해서만 장식 추가 장식 '\+' 문자에 대 한 응답에 추가 하는 코드를 변경 했습니다 했으므로 여기서는 '\+'를 입력 합니다. 장식 코드에 한 번 더 장식 표시 되도록 변경할 수 있습니다 모든 'a'입니다.  
  
 KeyBindingTest.cs 파일에서 'a' 문자를 데코레이팅하는 뷰에서 모든 줄을 반복 하 CreateVisuals\(\) 메서드를 변경 합니다.  
  
```c#  
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
  
## 코드 빌드 및 테스트  
  
1.  KeyBindingTest 솔루션을 빌드하고 실험적 인스턴스에서 실행 합니다.  
  
2.  텍스트 파일을 열거나 만듭니다. 문자를 포함 하는 일부 단어를 입력 'a', 다음을 입력 하 고 \+ 텍스트 보기에 위치 합니다.  
  
     자주색 사각형 파일의 모든 'a' 문자에 나타나야 합니다.