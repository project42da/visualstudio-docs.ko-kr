---
title: IProcessDebugManager::CreateApplication | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IProcessDebugManager.CreateApplication
apilocation:
- pdm.dll
helpviewer_keywords:
- IProcessDebugManager::CreateApplication
ms.assetid: d6b646f2-8af0-445c-ae7e-a9772042b3a1
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a051462f32acae238ca5843e283fe6001ec43fc1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iprocessdebugmanagercreateapplication"></a>IProcessDebugManager::CreateApplication
이 응용 프로그램에 대 한 새 디버그 응용 프로그램 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateApplication(  
   IDebugApplication**  ppda  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppda`  
 [out] 이 응용 프로그램에 대 한 디버그 응용 프로그램 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드에 의해 생성 된 개체에는 이름이 없으며 실행에 추가 되지 않습니다 응용 프로그램 목록입니다. 사용 된 `IProcessDebugManager::AddApplication` 응용 프로그램 목록에 디버그 응용 프로그램을 추가 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IProcessDebugManager 인터페이스](../../winscript/reference/iprocessdebugmanager-interface.md)   
 [IProcessDebugManager::AddApplication](../../winscript/reference/iprocessdebugmanager-addapplication.md)