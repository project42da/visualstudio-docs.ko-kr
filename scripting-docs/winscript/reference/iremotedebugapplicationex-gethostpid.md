---
title: IRemoteDebugApplicationEx:GetHostPid | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IRemoteDebugApplicationEx:GetHostPid
apilocation: scrobj.dll
helpviewer_keywords: IRemoteDebugApplicationEx:GetHostPid
ms.assetid: 4cf9f46c-29cf-4201-87f0-5b1ddbed2f2b
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ffb5ff1d23c832f5710abf6d97199afe3f777b67
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iremotedebugapplicationexgethostpid"></a>IRemoteDebugApplicationEx:GetHostPid
호스트 응용 프로그램에 대 한 프로세스 ID를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetHostPid(  
   DWORD*  dwHostPid  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwHostPid`  
 [out] 호스트 프로세스 식별자입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 IDE에서 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IRemoteDebugApplicationEx 인터페이스](http://msdn.microsoft.com/en-us/2f65fa67-06b7-4053-8945-22383ab66343)