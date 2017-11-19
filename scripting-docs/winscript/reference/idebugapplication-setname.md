---
title: IDebugApplication::SetName | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugApplication.SetName
apilocation: pdm.dll
helpviewer_keywords: IDebugApplication::SetName
ms.assetid: 7b0ddc58-6f20-4ce3-9bdf-81a6c1d64256
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ad54c1c9ba950c7f1b98d393bec2bf65c385ec60
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationsetname"></a>IDebugApplication::SetName
응용 프로그램의 이름을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetName(  
   LPCOLESTR  pstrName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pstrName`  
 [in] 응용 프로그램의 이름입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드에 제공 된 이름에 대 한 후속 호출에서 반환 됩니다는 `IRemoteDebugApplication::GetName` 메서드.  
  
 이 메서드를 호출 하기 전에 호출 해야는 `IProcessDebugManager::AddApplication` 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [IProcessDebugManager::AddApplication](../../winscript/reference/iprocessdebugmanager-addapplication.md)