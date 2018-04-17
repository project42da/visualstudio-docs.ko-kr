---
title: IDebugDocument2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDocument2
helpviewer_keywords:
- IDebugDocument2 interface
ms.assetid: 1bc58426-dbf5-4471-9aad-9d66cd80eef0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 36ac127e6cd6e25fd42c4859e723c883ecaffa82
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugdocument2"></a>IDebugDocument2
이 인터페이스는 소스 문서를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugDocument2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 일반적으로이 인터페이스를 구현합니다. 또한 디버그 엔진 (DE) 수는 소스 코드를 제공 해야 하 고 원본 디스크에 존재 하지 않는 경우이 인터페이스를 구현 해야 합니다.  이러한 경우에는 DE도 구현 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 및 [IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md) 인터페이스, 뿐만 아니라에 몇 가지 추가 메서드는 [ IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md) 및 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md) 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 에 대 한 메서드는 `IDebugDocumentContext2`, `IDebugDisassemblyStream2`, `IDebugDocumentPosition2`, 및 `IDebugActivateDocumentEvent2` 인터페이스는이 인터페이스를 반환 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugDocument2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)|여러 가지 형식 중 하나에 문서 이름을 가져옵니다.|  
|[GetDocumentClassID](../../../extensibility/debugger/reference/idebugdocument2-getdocumentclassid.md)|문서 클래스 식별자를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 DE 소스 코드를 제공 하는 경우에 구현 됩니다. 예를 들어 HTML 페이지에 스크립트를 디버깅 하는 경우는 DE 제공 소스 코드는 소스를 다운로드 하거나 동적으로 생성 하기 때문에 한 디스크 파일로 존재 하지 않습니다. C + +에서와 같은 일반적인 언어를 디버깅할 때이 인터페이스를 구현 해야 필요 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IsPositionInDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-ispositionindocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugdocumentcontext2-getdocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-getdocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md)