---
title: "VSTextView 개체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VSTextView"
helpviewer_keywords: 
  - "VSTextView 개체 참조"
  - "뷰 [Visual Studio SDK] 참조"
ms.assetid: 78272ddc-9718-4c65-a94e-a44a2e8d54f4
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# VSTextView 개체
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

텍스트 뷰는 사용자가 보고 하 고 텍스트 버퍼의 유니코드 텍스트를 편집할 수 있는 창입니다. 기본적으로, 보기를 편집기로 대부분의 사용자에서 참조할 기능입니다. 버퍼에서 다양 한 텍스트 계층 \(줄 바꿈, 개요 텍스트 및 등\)에 의해 보기도 구분 하기 때문에 뷰는 버퍼에 있는 텍스트의 정확한 표시 되도록 보장 되지 않습니다. 텍스트 보기에 대 한 자세한 내용은 참조 하십시오. [텍스트 보기에 액세스 하는 레거시 API를 사용 하 여](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)  
  
 다음 표에서 인터페이스에는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> 개체입니다.  
  
|인터페이스|설명|  
|-----------|--------|  
|[IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071)|표준 OLE 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IDropTarget>|표준 OLE 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite>|표준 OLE 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|표준 OLE 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|복합 작업 \(즉, 단일 실행 취소\/다시 실행 단위로 그룹화 된 작업\)를 만들 수 있습니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>|관리 및 보기에 액세스 하기 위한 기본 메서드를 제공 합니다.`IVsTextView` 하지 스레드로부터 안전 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|만들고 관리 창을 선택 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView>|텍스트 계층 상호 작용합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsThreadSafeTextView>|다른 스레드에서 보기에 대 한 작업을 수행합니다.|  
  
## 참고 항목  
 [Figures Edit](http://msdn.microsoft.com/ko-kr/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)   
 [VSTextBuffer 개체](../extensibility/vstextbuffer-object.md)   
 [텍스트 보기에 액세스 하는 레거시 API를 사용 하 여](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)