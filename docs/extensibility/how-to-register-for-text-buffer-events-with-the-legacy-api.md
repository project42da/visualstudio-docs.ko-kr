---
title: "방법: 레거시 API와 함께 텍스트 버퍼 이벤트에 등록 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-텍스트 버퍼 이벤트에 등록"
ms.assetid: 5fc00ced-882c-4b48-b46c-1fa5a2469f94
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# 방법: 레거시 API와 함께 텍스트 버퍼 이벤트에 등록
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

기존 API를 사용 하 여 텍스트 버퍼에 액세스 하는 경우 다음 절차에 나와 있는 것 처럼 텍스트 버퍼 이벤트에 대해 등록 해야 합니다.  
  
### 텍스트 버퍼 이벤트에 게 알리기 위해  
  
1.  에 있는 인터페이스 중 하나에 대 한 포인터를 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>를 호출 `QueryInterface` 에 대 한 포인터에 대 한 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>.  
  
2.  호출 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer.FindConnectionPoint%2A> 메서드 및 인터페이스 ID 등록 이벤트에 전달 합니다.  
  
     등록 하는 경우 예를 들어, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents>, 다음 ID의 IID\_IVsTextLinesEvents 인터페이스에 전달 됩니다.  
  
     텍스트 버퍼에 대 한 포인터를 반환 합니다. 해당 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> 해당 연결 지점 개체에 대 한 인터페이스입니다.  
  
3.  이 포인터를 사용 하 여 호출 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Advise%2A> 에 대 한 포인터를 등록 하려면 예를 들어, 이벤트 인터페이스의 구현에 전달 메서드를의 `IVsTextLinesEvents` 인터페이스.  
  
     환경을 호출 하 여 이벤트를 수신 대기를 중지 하 고 사용할 수 있는 쿠키를 반환의 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Unadvise%2A> 메서드가 있습니다.  
  
## 참고 항목  
 [레거시 API에서 텍스트 버퍼 이벤트](../extensibility/text-buffer-events-in-the-legacy-api.md)