---
title: IDebugStackFrame2::GetDocumentContext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugStackFrame2::GetDocumentContext
helpviewer_keywords:
- IDebugStackFrame2::GetDocumentContext
ms.assetid: 69e81439-1238-4f18-9028-6fd1c1ba5e4a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 14e7374fbea697b86d9ee838a6b8a76a57f920ff
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugstackframe2getdocumentcontext"></a>IDebugStackFrame2::GetDocumentContext
이 스택 프레임에 대 한 문서 컨텍스트를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDocumentContext (   
   IDebugDocumentContext2** ppCxt  
);  
```  
  
```csharp  
int GetDocumentContext (   
   out IDebugDocumentContext2 ppCxt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppCxt`  
 [out] 반환 된 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 소스 문서에서 현재 위치를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 호출 보다 빠르게는 [GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md) 메서드와 호출 하는 [GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md) 메서드 코드 컨텍스트를 합니다. 그러나 보장할 수는 없습니다 모든 디버그 엔진 (DE)가이 메서드를 구현 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)