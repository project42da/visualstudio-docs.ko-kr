---
title: "IDebugDocument2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugDocument2"
helpviewer_keywords: 
  - "IDebugDocument2 인터페이스"
ms.assetid: 1bc58426-dbf5-4471-9aad-9d66cd80eef0
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDocument2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 원본 문서를 나타냅니다.  
  
## 구문  
  
```  
IDebugDocument2 : IUnknown  
```  
  
## 구현자 참고 사항  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]일반적으로이 인터페이스를 구현합니다.  또한 디버그 엔진 \(DE\)의 소스 코드를 제공 하는 데 필요한 원본 디스크에 존재 하지 않는 경우이 인터페이스를 구현할 수 있습니다.  이러한 경우에는 DE도 구현할 수 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 및 [IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md) 인터페이스, 뿐만 아니라 일부 추가 방법에는 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md) 및 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md) 인터페이스.  
  
## 호출자에 대 한 참고 사항  
 메서드는 `IDebugDocumentContext2`, `IDebugDisassemblyStream2`, `IDebugDocumentPosition2`, 및 `IDebugActivateDocumentEvent2` 인터페이스는이 인터페이스를 반환 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugDocument2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)|문서의 이름을 여러 형태 중 하나에서 가져옵니다.|  
|[GetDocumentClassID](../../../extensibility/debugger/reference/idebugdocument2-getdocumentclassid.md)|문서 클래스 id를 가져옵니다.|  
  
## 설명  
 만 DE 소스 코드를 제공 하면이 인터페이스를 구현 합니다.  HTML 페이지의 스크립트를 디버깅 하는 경우 소스를 다운로드 하거나 동적으로 생성 하기 때문에 예를 들어, DE는 소스 코드 제공 및 디스크 파일로 존재 하지 않습니다.  C \+ \+와 같은 전통적인 언어를 디버깅 하는 경우이 인터페이스를 구현 하지 않아도 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IsPositionInDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-ispositionindocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugdocumentcontext2-getdocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-getdocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md)