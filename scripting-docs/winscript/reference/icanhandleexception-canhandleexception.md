---
title: ICanHandleException::CanHandleException | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: ICanHandleException.CanHandleException
apilocation: scrobj.dll
helpviewer_keywords: ICanHandleException::CanHandleException
ms.assetid: 0fc703bf-9518-487e-af20-00e073b640f1
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 15612330f160f694202bb2158f970e0633fe53bd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="icanhandleexceptioncanhandleexception"></a>ICanHandleException::CanHandleException
호출자에 게 스크립트 엔진의 지정 된 예외를 처리할 수 있는지 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CanHandleException(  
   EXCEPINFO*  pExcepInfo,  
   VARIANT*    pvar  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pExcepInfo`  
 [in] 에 대 한 포인터는 `EXCEPINFO` 예외 핸들러가 발견 되는 경우 보고 되는 정보가 포함 된 구조입니다.  
  
 `pvar`  
 [in] throw 된 값과 같은 예외와 연결 된 값을 `throw` 문. 이 매개 변수는 `NULL`일 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|호출자가 예외를 처리할 수 있습니다.|  
|`E_FAIL`|호출자가 예외를 처리할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 호출 하는 경우 `IDispatchEx::InvokeEx`, 응용 프로그램 또는 비슷한 메서드 예외를 지 원하는 스크립트의 호출자가 체인의 호출자에 대 한 스크립트 엔진이 검사의 결과 `ICanHandleException` 인터페이스 및 예외를 처리할 수 있음을 나타냅니다. 호출자는 예외를 처리할 수 있는 스크립트 엔진 중단 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ICanHandleException 인터페이스](../../winscript/reference/icanhandleexception-interface.md)   
 [IDispatchEx::InvokeEx](../../winscript/reference/idispatchex-invokeex.md)