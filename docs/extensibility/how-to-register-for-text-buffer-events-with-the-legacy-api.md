---
title: "방법: 레거시 API 사용 하 여 텍스트 버퍼 이벤트 등록 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - register for text buffer events
ms.assetid: 5fc00ced-882c-4b48-b46c-1fa5a2469f94
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 94f2e781c316f3891fdef0c324d54fa2f9742222
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-register-for-text-buffer-events-with-the-legacy-api"></a>방법: 레거시 API 사용 하 여 텍스트 버퍼 이벤트 등록
텍스트 버퍼에 레거시 API를 사용 하 여 액세스 하는 경우에 다음 절차에 표시 된 대로 텍스트 버퍼 이벤트에 등록 해야 합니다.  
  
### <a name="to-advise-text-buffer-events"></a>텍스트 버퍼 이벤트를 알리기 위해  
  
1.  에 인터페이스 중 하나에 대 한 포인터에서 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>, 호출 `QueryInterface` 에 대 한 포인터에 대 한 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>합니다.  
  
2.  호출 된 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer.FindConnectionPoint%2A> 메서드와 등록 하려는 이벤트의 인터페이스 ID 전달 합니다.  
  
     에 대 한 등록 하려는 경우 등 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents>, 인터페이스 IID_IVsTextLinesEvents ID에에서 전달 합니다.  
  
     텍스트 버퍼에 대 한 포인터를 반환 합니다.는 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> 적절 한 연결 지점 개체에 대 한 인터페이스입니다.  
  
3.  이 포인터를 사용 하 여 호출 된 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Advise%2A> 를 등록 하려면, 예를 들어 이벤트 인터페이스의 구현에 대 한 포인터에 전달 하는 메서드는 `IVsTextLinesEvents` 인터페이스입니다.  
  
     호출 하 여 이벤트를 수신 대기를 중지 한 다음 사용할 수 있는 쿠키를 반환 하는 환경에서 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Unadvise%2A> 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [레거시 API에서 텍스트 버퍼 이벤트](../extensibility/text-buffer-events-in-the-legacy-api.md)