---
title: IRemoteDebugApplicationThread::GetDescription | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IRemoteDebugApplicationThread.GetDescription
apilocation: pdm.dll
helpviewer_keywords: IRemoteDebugApplicationThread::GetDescription
ms.assetid: 69842e9e-7c1c-4841-a6b2-31505fe85738
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 74d3f59648a5a6aa0f510e98b33c3c26b1f9db56
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iremotedebugapplicationthreadgetdescription"></a>IRemoteDebugApplicationThread::GetDescription
설명 및이 스레드의 상태를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetDescription(  
   BSTR*  pbstrDescription,  
   BSTR*  pbstrState  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrDescription`  
 [out] 이 스레드에 대 한 설명입니다.  
  
 `pbstrState`  
 [out] 스레드 상태 설명입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 설명 및이 스레드의 상태를 가져옵니다.  
  
## <a name="see-also"></a>참고 항목  
 [IRemoteDebugApplicationThread 인터페이스](../../winscript/reference/iremotedebugapplicationthread-interface.md)