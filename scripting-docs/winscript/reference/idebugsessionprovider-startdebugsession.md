---
title: IDebugSessionProvider::StartDebugSession | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugSessionProvider.StartDebugSession
apilocation: scrobj.dll
helpviewer_keywords: IDebugSessionProvider::StartDebugSession
ms.assetid: 47697dfb-d4e1-492c-a14f-753e28195a76
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4e93d3bd48a544d5bb446e1bff102268a7624e85
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugsessionproviderstartdebugsession"></a>IDebugSessionProvider::StartDebugSession
지정한 응용 프로그램에서 디버그 세션을 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT StartDebugSession(  
   IRemoteDebugApplication*  pda  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pda`  
 [in] 디버그 응용 프로그램을 지정합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 지정한 응용 프로그램에서 디버그 세션을 시작합니다. 디버거를 호출 해야 `IRemoteDebugApplication::ConnectDebugger` 이 호출에서 반환 하기 전에.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugSessionProvider 인터페이스](../../winscript/reference/idebugsessionprovider-interface.md)   
 [IRemoteDebugApplication::ConnectDebugger](../../winscript/reference/iremotedebugapplication-connectdebugger.md)