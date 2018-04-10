---
title: 레거시 API를 사용 하 여 코드 창을 사용자 지정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - code windows
ms.assetid: 5328ab2f-55cb-4680-9744-ec79f55acd1b
caps.latest.revision: 19
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f0b00c31280b9471da99aea55118e25dd551ad96
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2018
---
# <a name="customizing-code-windows-by-using-the-legacy-api"></a>레거시 API를 사용 하 여 코드 창을 사용자 지정
코드 창에는 지 원하는 하나 이상의 텍스트 뷰 문서 창 개체입니다. 코드 창의 기능 관련 된 언어 서비스에 따라 달라 집니다. (Mdi 다중) 다중 문서 인터페이스 모드로 코드 MDI 자식 프레임입니다.  
  
 각 언어 서비스는 자체 코드 창 관리자를 제공할 수 있습니다 및 코드 windows 언어 서비스에 의해 제어 됩니다. 이 통해 언어 서비스 자체 장식을 물결선, 색 지정, 등 코드 창에 추가 합니다. 핵심 창을 만드는 방법에 대 한 자세한 내용은 참조 [레거시 API의 핵심 편집기 사용 하 여 인스턴스화](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)합니다.  
  
 코드 창을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> 텍스트 뷰 및 개체에 배치 되어 있는 장식을 개체입니다. 언어 서비스 연결할 수를 만들 때 코드 창의 핵심 사용자 인스턴스화하는 동안 편집기는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> 코드 창에는 다음 그림에 표시 됩니다 마찬가지로 합니다.  
  
 ![CodeWindow 그래픽](../extensibility/media/vscodewindow.gif "vscodewindow")  
코드 창  
  
 언어 서비스는 코드 창 관리자를 구현 하 고 드롭 다운 모음과 같은 장식을 관리 합니다. 코드 창 호출은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.AddAdornments%2A> 코드 창 초기화 하는 동안 메서드. 이 호출을 수행 하는 경우 언어 서비스 드롭 다운 모음 또는 단추 모음 추가할 수 (<xref:Microsoft.VisualStudio.TextManager.Interop.IVsButtonBarClient>)의 코드 창.  
  
## <a name="in-this-section"></a>섹션 내용  
 `Customizing Code Windows by Using the Legacy API`  
 레거시 API를 사용 하 여 코드 창을 사용자 지정 하는 방법에 설명 합니다.  
  
 [방법: 다른 편집기에서 편집기를 호스트 합니다.](../extensibility/how-to-host-an-editor-in-another-editor.md)  
 편집기 창 내 다른 사용자를 호스트 하는 방법에 설명 합니다.  
  
 [방법: 편집기 포커스를 잃을 때 이벤트 발생](../extensibility/how-to-fire-events-when-the-editor-loses-focus.md)  
 문서 데이터 개체에는 문서 보기를 연결 하는 방법에 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 [코어 편집기 레거시 API를 사용 하 여 인스턴스화](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)   
 [레거시 API를 사용 하 여 텍스트 보기에 액세스](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)