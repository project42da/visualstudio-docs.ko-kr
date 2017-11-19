---
title: "JsDebugReadMemoryFlags 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: JsDebugReadMemoryFlags
apilocation: jscript9diag.dll
ms.assetid: 0d98d154-9cb1-49de-b2df-a2d029d343b7
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7efb5170bf0314e95b1acded39a897c2236a29ff
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsdebugreadmemoryflags-enumeration"></a>JsDebugReadMemoryFlags 열거형
메모리를 읽을 때의 동작을 지정하는 플래그입니다.  
  
## <a name="syntax"></a>구문  
  
```  
enum JsDebugReadMemoryFlags{   None = 0,   JsDebugAllowPartialRead= 0x1} JsDebugReadMemoryFlags;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="values"></a>값  
  
|이름|설명|  
|----------|-----------------|  
|`JsDebugAllowPartialRead`|호출자에 게 읽기 작업이 성공 하는 경우에 메모리의 일부 읽기 성공를 원한다는 것을 나타냅니다. 이 설정 된 경우 'Address' 유효 하지 않을 경우 E_JsDEBUG_INVALID_MEMORY_ADDRESS 오류가 발생만 합니다. 이 플래그가 명확 이면 일부 요청된 된 메모리를 읽을 수 없습니다. E_JsDEBUG_INVALID_MEMORY_ADDRESS 오류가 발생 합니다.|  
|`None`|호출자에 게 ReadMemory에 대 한 기본 동작을 원한다는 것을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [Windows 스크립트 인터페이스 참조](../../winscript/reference/windows-script-interfaces-reference.md)