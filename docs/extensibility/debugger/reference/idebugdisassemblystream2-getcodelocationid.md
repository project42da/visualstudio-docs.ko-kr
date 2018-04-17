---
title: IDebugDisassemblyStream2::GetCodeLocationId | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDisassemblyStream2::GetCodeLocationId
helpviewer_keywords:
- IDebugDisassemblyStream2::GetCodeLocationId
ms.assetid: 567adfb8-2f54-499a-a027-e4ecb82277ef
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 86682bb64f041cd8ee1b08bbec02c28492cac7a9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugdisassemblystream2getcodelocationid"></a>IDebugDisassemblyStream2::GetCodeLocationId
특정 코드 컨텍스트에 대 한 코드 위치 식별자를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCodeLocationId(   
   IDebugCodeContext2* pCodeContext,  
   UINT64*             puCodeLocationId  
);  
```  
  
```csharp  
int GetCodeLocationId(   
   IDebugCodeContext2 pCodeContext,  
   out ulong          puCodeLocationId  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pCodeContext`  
 [in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 식별자로 변환 될 개체입니다.  
  
 `puCodeLocationId`  
 [out] 코드 위치 식별자를 반환합니다. 설명 부분을 참조하세요.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 반환 `E_CODE_CONTEXT_OUT_OF_SCOPE` 코드 컨텍스트가 유효 하지만 범위 밖에 있습니다.  
  
## <a name="remarks"></a>설명  
 코드 위치 식별자 디스어셈블리를 지 원하는 디버그 엔진 (DE)에 해당 됩니다. 이 위치 식별자 코드의 위치를 추적 하는 DE에서 내부적으로 사용 이며 일반적으로 된 주소 또는 특정 종류의 오프셋입니다. 유일한 요구 사항은 있으면를 한 곳의 코드 컨텍스트 코드 컨텍스트를 다른 위치를 보다 작은 경우 해당 코드 위치 식별자의 첫 번째 코드 컨텍스트의 두 번째 코드 컨텍스트의 코드 위치 식별자 보다 작을 수 또한 해야 합니다.  
  
 코드 위치 식별자의 코드 컨텍스트를 검색 하려면는 [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)