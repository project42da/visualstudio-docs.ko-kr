---
title: IDebugApplication::HandleRuntimeError | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugApplication.HandleRuntimeError
apilocation: pdm.dll
helpviewer_keywords: IDebugApplication::HandleRuntimeError
ms.assetid: f8f3bbaf-09e5-4d01-8a35-f380bc7ff8ed
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eead4780ff061ff9c7280aeee0936c8f64741981
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationhandleruntimeerror"></a>IDebugApplication::HandleRuntimeError
현재 스레드를 차단 하 고 IDE 디버거 오류에 대 한 알림을 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT HandleRuntimeError(  
   IActiveScriptErrorDebug*  pErrorDebug,  
   IActiveScriptSite*        pScriptSite,  
   BREAKRESUMEACTION*        pbra,  
   ERRORRESUMEACTION*        perra,  
   BOOL*                     pfCallOnScriptError  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pErrorDebug`  
 [in] 오류가 발생 한 경우  
  
 `pScriptSite`  
 [in] 스레드의 스크립트 사이트입니다.  
  
 `pbra`  
 [out] 디버거에서 응용 프로그램을 다시 시작 될 때 수행할 동작입니다.  
  
 `perra`  
 [out] 디버거는 동안 오류가 발생 하는 경우 응용 프로그램을 다시 시작 될 때 수행할 동작입니다.  
  
 `pfCallOnScriptError`  
 [out] 플래그는 `TRUE` 엔진 호출 해야 하는 경우는 `IActiveScriptSite::OnScriptError` 메서드.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 런타임 오류를 발생 시키는 스레드에의 컨텍스트에서이 메서드를 호출 하는 언어 엔진입니다. 이 메서드는 현재 스레드를 차단 하 고 디버거 IDE에 보낼 오류 알림을 보냅니다. IDE 디버거 응용 프로그램 다시 시작 되 면이 메서드는 수행할 동작을 반환 합니다.  
  
> [!NOTE]
>  런타임 오류에서 스택 프레임을 열거 하거나 포함 된 식을 평가 하는 대로 이러한 작업을 수행 하는 스레드에 의해 언어 엔진을 호출할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [IActiveScriptErrorDebug 인터페이스](../../winscript/reference/iactivescripterrordebug-interface.md)   
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)   
 [BREAKRESUMEACTION 열거형](../../winscript/reference/breakresumeaction-enumeration.md)   
 [ERRORRESUMEACTION 열거형](../../winscript/reference/errorresumeaction-enumeration.md)