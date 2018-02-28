---
title: IDebugApplication::AddStackFrameSniffer | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugApplication.AddStackFrameSniffer
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::AddStackFrameSniffer
ms.assetid: a7a9684a-14c5-415a-ae63-a17397d58d07
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 89faa6481bd5e5934ae2d3b85a0bade83949633a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationaddstackframesniffer"></a>IDebugApplication::AddStackFrameSniffer
이 응용 프로그램에는 스택 프레임 열거자 공급자를 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AddStackFrameSniffer(  
   IDebugStackFrameSniffer*  pdsfs,  
   DWORD*                    pdwCookie  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdsfs`  
 [in] 이 응용 프로그램에 추가할 스택 프레임 열거자 공급자입니다.  
  
 `pdwCookie`  
 [out] 응용 프로그램에서이 스택 프레임 열거자 공급자를 제거 하는 데 사용 되는 쿠키입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 언어 엔진에서 일반적으로 해당 스택 프레임이 하 고 디버거를 노출 하려면이 메서드를 호출 하지만 다른 엔터티의 스택 프레임을 노출 하는 것이 같습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [IDebugApplication::RemoveStackFrameSniffer](../../winscript/reference/idebugapplication-removestackframesniffer.md)   
 [IDebugStackFrameSniffer 인터페이스](../../winscript/reference/idebugstackframesniffer-interface.md)