---
title: IDebugStackFrame2::GetCodeContext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugStackFrame2::GetCodeContext
helpviewer_keywords: IDebugStackFrame2::GetCodeContext
ms.assetid: 93d66159-a41d-49ef-982f-91bb4d073b74
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b7c2ec437f69f82f00295755606d66cfcacb6741
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugstackframe2getcodecontext"></a>IDebugStackFrame2::GetCodeContext
이 스택 프레임에 대 한 코드 컨텍스트를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCodeContext (   
   IDebugCodeContext2** ppCodeCxt  
);  
```  
  
```csharp  
int GetCodeContext (   
   out IDebugCodeContext2 ppCodeCxt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppCodeCxt`  
 [out] 반환 된 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 이 스택 프레임에서 현재 명령 포인터를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)