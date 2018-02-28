---
title: IDebugApplication::HandleBreakPoint | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugApplication.HandleBreakPoint
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::HandleBreakPoint
ms.assetid: 97219bdf-a39a-4e69-81ac-4ca2afe77ce5
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 16b05533c566cb90529766d81fb7197dbc284664
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationhandlebreakpoint"></a>IDebugApplication::HandleBreakPoint
현재 스레드를 차단 하 고 IDE 디버거 중단점에 대 한 알림을 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT HandleBreakPoint(  
   BREAKREASON         br,  
   BREAKRESUMEACTION*  pbra  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `br`  
 [in] 나누기에 대 한 설명입니다.  
  
 `pbra`  
 [out] 디버거에서 응용 프로그램을 다시 시작 될 때 수행할 동작입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 중단점에 도달 하는 스레드의 컨텍스트에서이 메서드를 호출 하는 언어 엔진입니다. 이 메서드는 현재 스레드를 차단 하 고 디버거 IDE에 중단점 알림을 보냅니다. 디버거에서 응용 프로그램을 다시 시작 될 때의 `pbra` 매개 변수는 수행할 작업을 지정 합니다.  
  
> [!NOTE]
>  스레드 스택 열거와 같은 프레임 또는 중단점 중 포함 된 식을 평가 하는 작업을 수행 하 여 언어 엔진을 호출할 수 있습니다.  
  
 이 메서드를 사용 하면 `IApplicationDebugger::onHandleBreakPoint` 를 호출할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [IApplicationDebugger::onHandleBreakPoint](../../winscript/reference/iapplicationdebugger-onhandlebreakpoint.md)   
 [BREAKREASON 열거형](../../winscript/reference/breakreason-enumeration.md)   
 [BREAKRESUMEACTION 열거형](../../winscript/reference/breakresumeaction-enumeration.md)