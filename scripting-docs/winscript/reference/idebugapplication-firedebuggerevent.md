---
title: IDebugApplication::FireDebuggerEvent | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugApplication.FireDebuggerEvent
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::FireDebuggerEvent
ms.assetid: fd1f602e-fc15-4158-a6e7-497ff5b4a509
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c4cb02390602b6b93b8c233f245ede395833d67e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationfiredebuggerevent"></a>IDebugApplication::FireDebuggerEvent
디버거의 일반 이벤트가 발생 `IApplicationDebugger` 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT FireDebuggerEvent(  
   REFGUID    riid,  
   IUnknown*  punk  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `riid`  
 [in] 개체에 대 한 GUID입니다.  
  
 `punk`  
 [in] 디버거를 전달 하는 이벤트 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|메서드가 현재 구현 되지 않습니다.|  
  
## <a name="remarks"></a>설명  
 GUID의 의미 체계와 `IUnknown` 은 전적으로 응용 프로그램/디버거 정의 합니다.  
  
 즉, 디버거 모델의 사용자 지정 확장 프로그램에 대 한이 방법을 사용 하면 이 현재 구현 되지 않습니다.  
  
 이 메서드를 사용 하면 `IApplicationDebugger::onDebuggerEvent` 를 호출할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [IApplicationDebugger::onDebuggerEvent](../../winscript/reference/iapplicationdebugger-ondebuggerevent.md)