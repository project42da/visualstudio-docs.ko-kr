---
title: "연습: 파일 이름 확장명에 콘텐츠 형식 연결 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "파일 이름 확장명을 신규-링크 콘텐츠 형식을 편집기 [Visual Studio SDK]"
ms.assetid: 21ee64ce-9afe-4b08-94a0-8389cc4dc67c
caps.latest.revision: 24
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 24
---
# 연습: 파일 이름 확장명에 콘텐츠 형식 연결
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

사용자 고유의 콘텐츠 형식을 정의할 수 있으며 편집기 프레임 워크 MEF \(Managed Extensibility\) 확장을 사용 하 여 파일 이름 확장명에 연결 수 있습니다. 경우에 따라 파일 이름 확장명 이미 정의 되어 언어 서비스입니다. 그럼에도 불구 하 고 MEF와 함께 사용 하 여 여전히 해야 연결 콘텐츠 형식.  
  
## 사전 요구 사항  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하세요.  
  
## MEF 프로젝트 만들기  
  
1.  C\# VSIX 프로젝트를 만듭니다. \(에 **새 프로젝트** 대화 상자에서 **Visual C\# \/ 확장성**, 다음 **VSIX 프로젝트**.\) 솔루션의 이름을 `ContentTypeTest`합니다.  
  
2.  에 **source.extension.vsixmanifest** 파일을 이동는 **자산** 탭을 설정의 **형식** 필드를 **Microsoft.VisualStudio.MefComponent**,  **소스** 필드를 **현재 솔루션의 프로젝트**, 및 **프로젝트** 필드를 프로젝트의 이름입니다.  
  
## 콘텐츠 형식 정의  
  
1.  클래스 파일을 추가 하 고 이름을 `FileAndContentTypes`합니다.  
  
2.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    1.  System.ComponentModel.Composition  
  
    2.  Microsoft.VisualStudio.Text.Logic  
  
    3.  Microsoft.VisualStudio.CoreUtility  
  
3.  다음 코드를 추가 `using` 지시문입니다.  
  
    ```c#  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio.Text.Classification;  
    using Microsoft.VisualStudio.Utilities;  
  
    ```  
  
4.  정의 포함 하는 정적 클래스를 선언 합니다.  
  
    ```c#  
    internal static class FileAndContentTypeDefinitions  
    {. . .}  
    ```  
  
5.  이 클래스에서 내보내기는 <xref:Microsoft.VisualStudio.Utilities.ContentTypeDefinition> "hid" 라는 및 해당 기본 정의를 "text"를 선언 합니다.  
  
    ```c#  
    internal static class FileAndContentTypeDefinitions  
    {  
        [Export]  
        [Name("hid")]  
        [BaseDefinition("text")]  
        internal static ContentTypeDefinition hidingContentTypeDefinition;  
    }  
    ```  
  
## 파일 이름 확장명을 콘텐츠 형식에 연결  
  
-   이 콘텐츠 형식을 파일 이름 확장명을 매핑하려면 내보내기는 <xref:Microsoft.VisualStudio.Utilities.FileExtensionToContentTypeDefinition> 확장명이 ".hid" 및 "hid" 콘텐츠 형식입니다.  
  
    ```c#  
    internal static class FileAndContentTypeDefinitions  
    {  
         [Export]  
         [Name("hid")]  
         [BaseDefinition("text")]  
        internal static ContentTypeDefinition hidingContentTypeDefinition;  
  
         [Export]  
         [FileExtension(".hid")]  
         [ContentType("hid")]  
        internal static FileExtensionToContentTypeDefinition hiddenFileExtensionDefinition;  
    }  
    ```  
  
## 편집기 내보내기에 콘텐츠 형식 추가  
  
1.  편집기 확장을 만듭니다. 예를 들어에 설명 된 여백 문자 모양 확장 사용 하 여 [연습: 여백 모양 만들기](../extensibility/walkthrough-creating-a-margin-glyph.md)합니다.  
  
2.  이 절차에서 정의한 클래스를 추가 합니다.  
  
3.  확장 클래스를 내보낼 때 추가 된 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> 를 "숨기지" 형식입니다.  
  
    ```c#  
    [Export]  
    [ContentType("hid")]  
    ```  
  
## 참고 항목  
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)