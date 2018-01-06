---
title: IDebugThread2::SetNextStatement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugThread2::SetNextStatement
helpviewer_keywords: IDebugThread2::SetNextStatement
ms.assetid: 9e2834dd-4ecf-45af-8e6c-f9318ebdac06
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 6c70c1c1d3e525ccc676554d3b40df224423e313
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugthread2setnextstatement"></a>IDebugThread2::SetNextStatement
지정 된 코드 컨텍스트를 현재 명령 포인터를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetNextStatement (   
   IDebugStackFrame2*  pStackFrame,  
   IDebugCodeContext2* pCodeContext  
);  
```  
  
```csharp  
int SetNextStatement (   
   IDebugStackFrame2  pStackFrame,  
   IDebugCodeContext2 pCodeContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pStackFrame`  
 나중에 사용 됩니다. null 값으로 설정 합니다.  
  
 `pCodeContext`  
 [in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 실행 될 코드 위치를 설명 하는 개체 및 컨텍스트.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 다음 표에서 가능한 다른 값을 보여 줍니다.  
  
|값|설명|  
|-----------|-----------------|  
|E_CANNOT_SET_NEXT_STATEMENT_ON_NONLEAF_FRAME|다음 문은 프레임 스택에 깊은 스택 프레임에 수 없습니다.|  
|E_CANNOT_SETIP_TO_DIFFERENT_FUNCTION|다음 문이 스택의 프레임에 연관 되어 있습니다.|  
|E_CANNOT_SET_NEXT_STATEMENT_ON_EXCEPTION|일부 디버깅 엔진이 예외가 발생 한 후 다음 문을 설정할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 명령 포인터는 다음 명령이 나 문을 실행할 수를 나타냅니다. 이 메서드는 소스 코드 줄을 다시 시도 하거나 예를 들어 다른 함수에서 계속 실행을 강제로 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)