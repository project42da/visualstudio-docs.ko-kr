---
title: "Ijsdebugdatatarget:: Readmemory 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IJsDebugDataTarget.ReadMemory
apilocation: jscript9diag.dll
ms.assetid: 664e0f7d-2007-45f4-b993-36fe8b1944e5
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fc1b67b33e17761a675d6ced9e175b4206ede2e1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugdatatargetreadmemory-method"></a>IJsDebugDataTarget::ReadMemory 메서드
대상 프로세스의 메모리를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ReadMemory(  
   UINT64 address,  
   JsDebugReadMemoryFlags flags,  
   BYTE *pBuffer,  
   DWORD size,  
   DWORD *pBytesRead  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `address`  
 [in] 대상 프로세스의 메모리를 읽을 수 있는 기본 주소입니다.  
  
 `flags`  
 [in] ReadMemory의 동작을 제어 하는 플래그입니다.  
  
 `pBuffer`  
 [out] 대상 프로세스의 주소 공간에서 콘텐츠를 수신 하는 버퍼입니다. 실패 한 경우,이 버퍼의 내용을 지정 되지 않았습니다.  
  
 `size`  
 [in] 프로세스에서 읽을 바이트 수입니다.  
  
 `pBytesRead`  
 [out] 대상 프로세스에서 읽은 바이트 수를 나타냅니다. JsDebugAllowPartialRead 지우기 이면 성공이 값은 항상 입력된 크기가 같아야 합니다. 성공할 경우 JsDebugAllowPartialRead를 지정 하는 경우이 값이 0 보다 큰 됩니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 모든 오류에 대 한 반환 s_ok이 고, 성공 및 오류 코드에 사용 됩니다. 주소는 유효 하지 않을 경우 E_JsDEBUG_INVALID_MEMORY_ADDRESS를 반환 합니다. 자세한 내용은 JsDebugAllowPartialRead 참조 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)