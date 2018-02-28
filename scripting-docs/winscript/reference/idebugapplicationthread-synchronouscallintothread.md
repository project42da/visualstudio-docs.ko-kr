---
title: IDebugApplicationThread::SynchronousCallIntoThread | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugApplicationThread.SynchronousCallIntoThread
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplicationThread::SynchronousCallIntoThread
ms.assetid: 8a91157f-dade-418a-ad02-5607ce12c95c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fdeb57380975f19424f8b7da783846b5aae976ed
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationthreadsynchronouscallintothread"></a>IDebugApplicationThread::SynchronousCallIntoThread
호출자에 게 응용 프로그램 스레드에서 코드를 실행 하는 메커니즘을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SynchronousCallIntoThread(  
   IDebugThreadCall*  pstcb,  
   DWORD_PTR          dwParam1,  
   DWORD_PTR          dwParam2,  
   DWORD_PTR          dwParam3  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pstcb`  
 [in] 호출 하는 개체입니다.  
  
 `dwParam1`  
 [in] 첫 번째 매개 변수를 전달 하는 `IDebugThreadCall::ThreadCallHandler` 메서드.  
  
 `dwParam2`  
 [in] 두 번째 매개 변수를 전달 하는 `IDebugThreadCall::ThreadCallHandler` 메서드.  
  
 `dwParam3`  
 [in] 세 번째 매개 변수를 전달 하는 `IDebugThreadCall::ThreadCallHandler` 메서드.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 호출자 디버거 스레드에서 코드를 실행 하는 메커니즘을 제공 합니다. 언어 엔진 및 호스트 자유 스레드 개체가 단일 스레드 구현 사항을 기반으로 구현 하려면 일반적으로이 방법을 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplicationThread 인터페이스](../../winscript/reference/idebugapplicationthread-interface.md)   
 [IDebugThreadCall 인터페이스](../../winscript/reference/idebugthreadcall-interface.md)