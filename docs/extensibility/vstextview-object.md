---
title: "VSTextView 개체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VSTextView
helpviewer_keywords:
- VSTextView object, reference
- views [Visual Studio SDK], reference
ms.assetid: 78272ddc-9718-4c65-a94e-a44a2e8d54f4
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e3b7cdc698a169150560b2a924cd6f3317fa78ed
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="vstextview-object"></a>VSTextView 개체
텍스트 보기에는 사용자가을 보고 텍스트 버퍼의 유니코드 텍스트를 편집할 수 있는 창입니다. 기본적으로 뷰는, 대부분의 사용자가 참조 작업 편집기로 합니다. 버퍼에서 다양 한 텍스트 계층 (줄 바꿈, 개요 텍스트 및 등)에 의해 뷰의 구분 때문에 보기는 정확한 버퍼에서 텍스트 표시 되도록 보장 되지 않습니다. 텍스트 보기에 대 한 자세한 내용은 참조 하세요. [레거시 API를 사용 하 여 텍스트 보기에 액세스](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)  
  
 다음 표에서 인터페이스에는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> 개체입니다.  
  
|인터페이스|설명|  
|---------------|-----------------|  
|[IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071)|표준 OLE 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IDropTarget>|표준 OLE 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite>|표준 OLE 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|표준 OLE 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|복합 작업 (즉, 단일 실행 취소/다시 실행 단위로 그룹화 하는 작업)를 만들 수 있도록 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>|관리 및 보기에 액세스 하기 위한 기본 메서드를 제공 합니다. `IVsTextView`하지 스레드로부터 안전 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|만들고 된 창 도킹 창을 관리 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView>|텍스트 계층 상호 작용합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsThreadSafeTextView>|다른 스레드에서 보기에 대 한 작업을 수행합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [숫자 값 편집](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)   
 [VSTextBuffer 개체](../extensibility/vstextbuffer-object.md)   
 [레거시 API를 사용 하 여 텍스트 보기에 액세스](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)