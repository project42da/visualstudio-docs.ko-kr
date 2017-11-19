---
title: IRemoteDebugApplication::ResumeFromBreakPoint | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IRemoteDebugApplication.ResumeFromBreakPoint
apilocation: pdm.dll
helpviewer_keywords: IRemoteDebugApplication::ResumeFromBreakPoint
ms.assetid: a613cc2b-1d69-4713-a235-64372c253b4a
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5da5fdbaaf74f463161f1a98bbad7d4d147b418d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iremotedebugapplicationresumefrombreakpoint"></a>IRemoteDebugApplication::ResumeFromBreakPoint
중단점에 현재 있는 응용 프로그램을 계속 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ResumeFromBreakPoint(  
   IRemoteDebugApplicationThread*  prptFocus,  
   BREAKRESUMEACTION               bra,  
   ERRORRESUMEACTION               era  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `prptFocus`  
 [in] 단계별 실행 모드에 의해 영향을 받을 수 하는 스레드 모드를 단계별로 실행 합니다.  
  
 `bra`  
 [in] 수행할 동작을 응용 프로그램을 다시 시작 합니다.  
  
 `era`  
 [in] 오류 때문에 응용 프로그램을 중지 하는 경우 수행할 동작입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 현재 중단점에 있는 응용 프로그램을 계속 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IRemoteDebugApplication 인터페이스](../../winscript/reference/iremotedebugapplication-interface.md)   
 [BREAKRESUMEACTION 열거형](../../winscript/reference/breakresumeaction-enumeration.md)   
 [ERRORRESUMEACTION 열거형](../../winscript/reference/errorresumeaction-enumeration.md)