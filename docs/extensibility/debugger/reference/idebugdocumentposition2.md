---
title: IDebugDocumentPosition2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugDocumentPosition2
helpviewer_keywords:
- IDebugDocumentPosition2 interface
ms.assetid: 0e838ced-12bb-4efc-b811-2b7c034b77b0
caps.latest.revision: 13
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ba9aaf9b0d23aed99397a6c52ca443a9477bc20a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdocumentposition2"></a>IDebugDocumentPosition2
이 인터페이스는 소스 파일에는 추상 위치를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugDocumentPosition2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 Visual Studio는 일반적으로이 인터페이스를 구현합니다. 디버그 엔진 (DE)는 자체 소스 코드를 제공 해야 하는 경우에이 인터페이스를 구현 (으로 DE 구현할 때는 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) 인터페이스).  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스는 인수로 전달 된 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)합니다. 에서도의 일부로 제공 되는 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) union (특히는 [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md) 구조) 차례로의 일부인는 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 구조 보류 중인 중단점을 만들기에 사용 되는 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugDocumentPosition2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetFileName](../../../extensibility/debugger/reference/idebugdocumentposition2-getfilename.md)|이 문서 위치를 포함 하는 소스 파일의 파일 이름을 가져옵니다.|  
|[GetDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-getdocument.md)|포함 하는 문서를 가져옵니다.|  
|[IsPositionInDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-ispositionindocument.md)|이 위치는 특정된 문서에 포함 되어 있으면 결정 합니다.|  
|[GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)|이 문서에 대 한 범위를 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md)