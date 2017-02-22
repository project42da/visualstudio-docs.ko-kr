---
title: "레거시 API를 사용 하 여 코드를 사용자 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK]-레거시 코드 창"
ms.assetid: 5328ab2f-55cb-4680-9744-ec79f55acd1b
caps.latest.revision: 19
caps.handback.revision: 19
ms.author: "gregvanl"
manager: "ghogen"
---
# 레거시 API를 사용 하 여 코드를 사용자 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

코드 창에는 하나 이상의 텍스트 뷰를 지원 하는 문서 창 개체입니다. 코드 창의 정확한 기능 관련 된 언어 서비스에 따라 달라 집니다. 다중 문서 인터페이스 \(MDI\) 모드에서 코드 MDI 자식 프레임입니다.  
  
 언어 서비스에 의해 제어 되는 코드 창 및 각 언어 서비스는 자체 코드 창 관리자를 제공할 수 있습니다. 이 환경은 언어 서비스는 자체 장식을 물결 기호, 색 지정, 등의 코드 창에 추가 합니다. 핵심 윈도 만드는 방법에 대 한 자세한 내용은 참조 [코어 편집기 레거시 API를 사용 하 여 인스턴스화](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)합니다.  
  
 코드 창을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> 텍스트 뷰 및 개체에 있는 장식이 있는 개체입니다. 언어 서비스를 만들 때 코드 창 핵심 프로그램 인스턴스화하는 동안 편집기를 연결할 수는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> 코드 창에는 다음 그림에 표시 됩니다로 합니다.  
  
 ![CodeWindow 그래픽](../extensibility/media/vscodewindow.png "vscodewindow")  
코드 창  
  
 언어 서비스 코드 창 관리자를 구현 하 고 드롭다운 막대와 같은 도구 영역을 관리 합니다. 호출 하 여 코드 창에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.AddAdornments%2A> 코드 창 초기화 하는 동안 메서드. 이 호출 되 면 드롭다운 막대 또는 단추 표시줄에서 언어 서비스 추가할 수 \(<xref:Microsoft.VisualStudio.TextManager.Interop.IVsButtonBarClient>\)의 코드 창입니다.  
  
## 단원 내용  
 `Customizing Code Windows by Using the Legacy API`  
 기존 API를 사용 하 여 코드 창을 사용자 지정 하는 방법을 설명 합니다.  
  
 [방법: 다른 편집기에서 편집기를 호스트 합니다.](../extensibility/how-to-host-an-editor-in-another-editor.md)  
 편집기 창 내의 두 번째 편집기를 호스트 하는 방법을 설명 합니다.  
  
 [방법: 편집기 포커스를 잃을 때 이벤트를 발생 시키고](../extensibility/how-to-fire-events-when-the-editor-loses-focus.md)  
 문서 데이터 개체에는 문서 보기를 연결 하는 방법에 설명 합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 [코어 편집기 레거시 API를 사용 하 여 인스턴스화](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)   
 [텍스트 보기에 액세스 하는 레거시 API를 사용 하 여](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)