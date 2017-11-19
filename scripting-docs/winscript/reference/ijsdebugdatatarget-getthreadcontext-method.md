---
title: "Ijsdebugdatatarget:: Getthreadcontext 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IJsDebugDataTarget.GetThreadContext
apilocation: jscript9diag.dll
ms.assetid: faf2a689-6c49-4a7d-b5a6-2b323e2257a7
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4e2f858c66eda2ad09b04d7beab776c793b6f195
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugdatatargetgetthreadcontext-method"></a>IJsDebugDataTarget::GetThreadContext 메서드
에 대 한 검색 컨텍스트 스레드를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetThreadContext(  
   DWORD threadId,  
   ULONG32 contextFlags,  
   ULONG32 contextSize,  
   void *pContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `threadId`  
 [in] 대상 프로세스에서 실행 되는 스레드입니다.  
  
 `contextFlags`  
 [in] 상황에 맞는 플래그를 지정합니다. (자세한 내용은 참조 winnt.h CONTEXT_ALL 검색)에 대 한 컨텍스트 ContextFlags 필드와 같습니다.  
  
 `contextSize`  
 [in] PContext로 지정 된 버퍼의 크기입니다.  
  
 `pContext`  
 [out] PContext로 지정 된 버퍼에 플랫폼 관련 컨텍스트 구조를 수신 합니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)