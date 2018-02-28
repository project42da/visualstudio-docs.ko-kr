---
title: IRemoteDebugApplicationThread::EnumStackFrames | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IRemoteDebugApplicationThread.EnumStackFrames
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplicationThread::EnumStackFrames
ms.assetid: 605ce83d-43d2-47ea-b066-ec8f0da50ca6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9c754ce92a342163acc07b69c097af5df4c226cf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iremotedebugapplicationthreadenumstackframes"></a>IRemoteDebugApplicationThread::EnumStackFrames
이 스레드와 관련 된 스택 프레임에 대 한 열거자를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumStackFrames(  
   IEnumDebugStackFrames**  ppedsf  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppedsf`  
 [out] 이 스레드와 관련 된 스택 프레임에 대 한 열거자입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 중단점 내에서 호출 되어야 합니다. 스택 프레임 열거자는 스택의 맨 위부터 프레임 가장 최근에 푸시된 프레임부터 반환 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IRemoteDebugApplicationThread 인터페이스](../../winscript/reference/iremotedebugapplicationthread-interface.md)