---
title: "SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b3aa4966-e110-4b30-b368-1281a9740dbd
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6fe5b308ea75956d9e5826b4daadaef3a823141f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="scripterrordebugexceptionthrownkind-enumeration"></a>SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND 열거형
Throw된 예외의 종류를 표시합니다. 이 열거형은에서 사용 된 [IActiveScriptErrorDebug110::GetExceptionThrownKind](../../winscript/reference/iactivescripterrordebug110-getexceptionthrownkind.md) 메서드.  
  
> [!IMPORTANT]
>  이러한 상수는 PDM 버전 11.0 이상에 의해 구현됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND  
```  
  
## <a name="members"></a>멤버  
  
|멤버|값|설명|  
|------------|-----------|-----------------|  
|ETK_FIRST_CHANCE|0x00000000|이 예외는 첫 번째로 발생할 가능성이 있는 예외입니다.|  
|ETK_USER_UNHANDLED|0x00000001|이 예외는 사용자 코드에서 처리되지 않습니다.|  
|ETK_UNHANDLED|0x00000002|이 예외는 코드에서 처리되지 않습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptErrorDebug110 인터페이스](../../winscript/reference/iactivescripterrordebug110-interface.md)