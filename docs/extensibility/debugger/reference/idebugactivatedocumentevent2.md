---
title: IDebugActivateDocumentEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugActivateDocumentEvent2
helpviewer_keywords: IDebugActivateDocumentEvent2 interface
ms.assetid: 6f37edd7-a48c-4b41-b160-dff9be63a284
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c6ace15a6e2a88aa214261d3d8ec137ebb6d7ebe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugactivatedocumentevent2"></a>IDebugActivateDocumentEvent2
디버그 엔진 (DE)이이 인터페이스를 사용 하 여 문서를 로드를 요청 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugActivateDocumentEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE 원본 파일을 열 수 해야 하는 경우이 인터페이스를 구현 합니다. 이 인터페이스를 사용 하거나 스크립트 번역기의 일부인 디버그 엔진에 의해서만 구현 됩니다. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 해당이 인터페이스와 같은 개체에 대해 인터페이스를 구현 해야 합니다 (은 SDM 사용 하 여 [QueryInterface](/cpp/atl/queryinterface) 액세스로는 `IDebugEvent2` 인터페이스).  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 DE을 만들어 원본 파일이 열려 있는 해야 할 때이 이벤트 개체를 보냅니다. 이벤트를 사용 하 여 보내집니다는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 은 SDM 디버깅 중인 프로그램에는 연결 된 경우 제공한 콜백 함수입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugActivateDocumentEvent2`합니다.  
  
|메서드|설명|  
|-------------|-----------------|  
|[GetDocument](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocument.md)|활성화 하려면 문서를 가져옵니다.|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocumentcontext.md)|문서 내에서 위치를 설명 하는 문서 컨텍스트를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스 사용 되는 일반적인 시나리오는 문서를 구문 분석 오류 표시 될 수 있도록 DE 스크립트의은 SDM에이 인터페이스 보내는 HTML 페이지에서 스크립트 코드에서 구문 분석 오류가 발생 하는 경우입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)