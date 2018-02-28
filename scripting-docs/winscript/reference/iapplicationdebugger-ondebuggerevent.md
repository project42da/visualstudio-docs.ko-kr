---
title: IApplicationDebugger::onDebuggerEvent | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IApplicationDebugger.onDebuggerEvent
apilocation:
- scrobj.dll
helpviewer_keywords:
- IApplicationDebugger::onDebuggerEvent
ms.assetid: 82a5faaa-1222-4bf1-8569-10439dbdf16d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 754c56b8474a5e21a05c1399540391197c373118
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iapplicationdebuggerondebuggerevent"></a>IApplicationDebugger::onDebuggerEvent
사용자 지정 응용 프로그램 이벤트를 처리합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT onDebuggerEvent(  
   REFIID     riid,  
   IUnknown*  punk  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `riid`  
 [in] 개체에 대 한 인터페이스 식별자입니다.  
  
 `punk`  
 [in] 에 정의 된 인터페이스를 구현 하는 이벤트 개체를 `riid`합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|메서드가 현재 구현 되지 않습니다.|  
  
## <a name="remarks"></a>설명  
 의미 체계는 `IUnknown` 은 전적으로 응용 프로그램/디버거 정의 합니다.  
  
 즉, 디버거 모델의 사용자 지정 확장 프로그램에 대 한이 방법을 사용 하면 이 현재 구현 되지 않습니다.  
  
 이 메서드를 호출한 경우 `IDebugApplication::FireDebuggerEvent` 라고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IApplicationDebugger 인터페이스](../../winscript/reference/iapplicationdebugger-interface.md)   
 [IDebugApplication::FireDebuggerEvent](../../winscript/reference/idebugapplication-firedebuggerevent.md)