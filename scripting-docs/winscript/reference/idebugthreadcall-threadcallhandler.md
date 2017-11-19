---
title: IDebugThreadCall::ThreadCallHandler | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugThreadCall.ThreadCallHandler
apilocation: jscript.dll
helpviewer_keywords: IDebugThreadCall::ThreadCallHandler
ms.assetid: c6d5d9db-bfed-44ec-90bc-46637f7de0ab
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e2b7a22026090c8b3b8b7ded4c960ebf92689cd4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugthreadcallthreadcallhandler"></a>IDebugThreadCall::ThreadCallHandler
코드가 다른 스레드에서 실행에 대 한 호출을 처리 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ThreadCallHandler(  
   DWORD_PTR  dwParam1,  
   DWORD_PTR  dwParam2,  
   DWORD_PTR  dwParam3  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwParam1`  
 [in] 첫 번째 매개 변수입니다.  
  
 `dwParam2`  
 [in] 두 번째 매개 변수입니다.  
  
 `dwParam3`  
 [in] 세 번째 매개 변수입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드 코드를 실행 하는 디버거 스레드에서 호출을 처리 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugThreadCall 인터페이스](../../winscript/reference/idebugthreadcall-interface.md)   
 [IDebugApplication::SynchronousCallInDebuggerThread](../../winscript/reference/idebugapplication-synchronouscallindebuggerthread.md)   
 [IDebugApplicationThread::SynchronousCallIntoThread](../../winscript/reference/idebugapplicationthread-synchronouscallintothread.md)