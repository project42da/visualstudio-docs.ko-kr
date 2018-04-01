---
title: IDebugExceptionEvent2::PassToDebuggee | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugExceptionEvent2::PassToDebuggee
helpviewer_keywords:
- IDebugExceptionEvent2::PassToDebuggee
ms.assetid: a20d0f0b-2ca0-4437-bd22-9213c81d2738
caps.latest.revision: 12
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: d10f01289fc0a5733586e19bb3b584fa0f95f4aa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugexceptionevent2passtodebuggee"></a>IDebugExceptionEvent2::PassToDebuggee
예외를 삭제 해야 하는 경우 또는 예외 실행이 다시 시작 하는 경우 디버깅 중인 프로그램에 전달 해야 하는지 여부를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT PassToDebuggee(  
   BOOL fPass  
);  
```  
  
```csharp  
int PassToDebuggee(  
   int fPass  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fPass`  
 [in] 0이 아닌 (`TRUE`) 예외 0 또는 실행이 다시 시작 하는 경우 디버깅 중인 프로그램에 전달 되어야 하는 경우 (`FALSE`) 예외를 삭제 해야 하는 경우.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 호출 해도 디버깅 중인 프로그램에서 실행 될 모든 코드 실제로 발생 하지 않습니다. 호출은 다음 코드 실행에 대 한 상태를 설정 하려면 단순히입니다. 예를 들어에 대 한 호출이 [CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) 반환 될 수 있으며 `S_OK` 와 [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)합니다.`dwState` 필드 설정 `EXCEPTION_STOP_SECOND_CHANCE`합니다.  
  
 IDE 나타날 수는 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md) 이벤트 및 호출 된 [계속](../../../extensibility/debugger/reference/idebugprogram2-continue.md) 메서드. 디버그 엔진 (DE) 경우를 처리 하는 기본 동작이 있어야는 `PassToDebuggee` 메서드가 호출 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)   
 [Continue](../../../extensibility/debugger/reference/idebugprogram2-continue.md)