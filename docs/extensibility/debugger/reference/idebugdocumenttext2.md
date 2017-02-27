---
title: "IDebugDocumentText2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugDocumentText2"
helpviewer_keywords: 
  - "IDebugDocumentText2 인터페이스"
ms.assetid: e85f50a3-211c-4220-a9f4-789950ba2782
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugDocumentText2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 텍스트 문서를 나타냅니다.  
  
## 구문  
  
```  
IDebugDocumentText2 : IDebugDocument2  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 텍스트 형태로 소스 코드를 제공 하는 데 필요한 경우이 인터페이스를 구현 합니다.  DE를 구현 하는 경우이 가장 일반적인 경우입니다 있기 때문에 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) 인터페이스를이 해야 합니다 구현할 수도 `IDebugDocumentText2` 인터페이스.  
  
## 호출자에 대 한 참고 사항  
 사용은 `QueryInterface` 이 인터페이스에서 얻을 수 있는 메서드는 `IDebugDocument2` 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 메서드 외에 `IDebugDocument2` 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetSize](../../../extensibility/debugger/reference/idebugdocumenttext2-getsize.md)|이 위치는 문서에서 텍스트의 크기를 검색합니다.|  
|[GetText](../../../extensibility/debugger/reference/idebugdocumenttext2-gettext.md)|문서의 지정 된 위치에서 텍스트를 검색합니다.|  
  
## 설명  
 이 인터페이스를 구현 하는 개체도 구현 해야는 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> 인터페이스는 소모품의 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> 의 인터페이스는 [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md) 개체입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)   
 [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)