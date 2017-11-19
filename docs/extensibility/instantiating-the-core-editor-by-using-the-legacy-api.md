---
title: "레거시 API를 사용 하 여 핵심 편집기 인스턴스화합니다 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - instantiating editor
ms.assetid: dda23b18-96ef-43c6-b0dc-06d15cbe5cbb
caps.latest.revision: "29"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a82f420203b88bb94531401d061493621f3eba93
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="instantiating-the-core-editor-by-using-the-legacy-api"></a>코어 편집기 레거시 API를 사용 하 여 인스턴스화
편집기는 텍스트 삽입, 삭제, 복사 및 붙여넣기 등의 기능을 편집 합니다. 텍스트 색 지정, 들여쓰기 및 IntelliSense 문 완성 등의 언어 서비스에서 제공 하는 설정과 이러한 함수를 결합 합니다.  
  
 다음 세 가지 방법 중 하나에 핵심 편집기의 인스턴스를 인스턴스화할 수 있습니다.  
  
-   명시적으로 창에서 코어의 인스턴스 편집기를 만듭니다.  
  
-   핵심 편집기의 인스턴스를 반환 하는 편집기 팩터리를 제공 합니다.  
  
-   프로젝트 계층 구조에서 파일을 엽니다.  
  
 다음 섹션에서는 레거시 API 인스턴스화할 편집기를 사용 하는 방법에 설명 합니다.  
  
## <a name="explicitly-opening-a-core-editor-instance"></a>코어 편집기 인스턴스를 명시적으로 열기  
 핵심 편집기의 인스턴스를 명시적으로 가져오지:  
  
-   가져올는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 편집 중인 문서 데이터 개체를 저장할 수 있습니다.  
  
-   문서 데이터 개체로의 지향 줄 표현을 만들어 만들는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> 에서 인터페이스는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 인터페이스입니다.  
  
-   설정 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> 인스턴스의 기본 구현에 대 한 문서 데이터 개체로 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> 인터페이스를 사용 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow.SetBuffer%2A> 메서드.  
  
     호스트는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> 인스턴스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> 인터페이스를 사용 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateToolWindow%2A> 메서드.  
  
 이 시점에서 표시 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> 인터페이스 코어 편집기의 인스턴스를 포함 하는 창을 제공 합니다.  
  
 그러나 바로 가기 키를 포함 하거나 고급 기능에 액세스 하지 않는 때문에 이것은 매우 유용한 인스턴스가 아닙니다. 바로 가기 키 및 고급 기능에 대 한 액세스를 얻으려고 합니다.  
  
-   사용 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> 언어 서비스 및 편집기를 사용 하는 문서 데이터 개체를 연결 하는 방법이 있습니다.  
  
-   만들기, 사용자 고유의 바로 가기 키 또는 시스템 기본값을 설정 하 여 사용 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> 개체 속성을 표시 합니다. 이 작업을 수행 하려면 호출는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetGuidProperty%2A> 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> 속성입니다.  
  
     구하고 비표준 바로 가기 키를 사용 하 여.vsct 파일을 사용 하 여를 생성 합니다. 자세한 내용은 [Visual Studio Command Table (.Vsct) Files](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)을 참조하세요.  
  
## <a name="how-to-use-an-editor-factory-to-obtain-the-core-editor"></a>코어 편집기 얻으려고 편집기 팩터리를 사용 하는 방법  
 핵심 편집기를 사용 하 여 편집기 팩터리를 구현 하는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 메서드를 명시적으로 호스트 하는 이전 섹션에 설명 된 모든 단계를 수행는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> 를 사용 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 문서 데이터 개체는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> 개체입니다.  
  
 텍스트를 표시 하려면 가져올는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 에서 인터페이스는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> 개체와 호출 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 메서드.  
  
 언어 서비스 편집기를 제공 하려면 호출는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> 내에서 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 메서드.  
  
 기본 바로 가기 키의 이전 섹션에서 달리 얻으려고 반환한 명령 컨텍스트를 사용는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 코어 편집기에서 가져올 때 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 메서드.  
  
 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 텍스트 편집기로 동일한 명령 GUID를 반환 하는 메서드, 핵심 편집기의 인스턴스를 자동으로 가져옵니다 기본 바로 가기 키입니다.  
  
 일반 정보를 참조 하십시오. [연습: 코어 편집기를 작성 및 편집기 파일 형식 등록](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [코어 편집기 내](../extensibility/inside-the-core-editor.md)   
 [열기 및 프로젝트 항목 저장](../extensibility/internals/opening-and-saving-project-items.md)   
 [연습: 코어 편집기 연결을 만들고 편집기 파일 형식 등록](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)