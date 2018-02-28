---
title: IActiveScriptStats::GetStatEx | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptStats.GetStatEx
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptStats::GetStatEx
ms.assetid: f526f51d-8ab5-49ef-a8f7-ae0ac1cb46e4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5cb8adf27811f3046de7b447e537443ef129a8c3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptstatsgetstatex"></a>IActiveScriptStats::GetStatEx
사용자 지정 스크립트 통계를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetStatEx(  
   REFGUID  guid,  
   ULONG*   pluHi,  
   ULONG*   pluLo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guid`  
 [in] 반환할 통계를 지정 합니다. 의미 체계는 특정에 해당 하는 통계의 GUID는 전적으로 정의 된 엔진입니다.  
  
 `pluHi`  
 [out] 통계를 나타내는 64 비트 부호 없는 정수의 상위 32 비트입니다.  
  
 `pluLo`  
 [out] 통계를 나타내는 64 비트 부호 없는 정수의 하위 32 비트입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|메서드가 구현 되지 않았습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 사용자 지정 호스트를 의미 있는 통계를 반환 하는 사용자 지정 스크립트 엔진을 수 있습니다.  
  
> [!NOTE]
>  이 메서드가 현재 구현 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptStats::GetStat](../../winscript/reference/iactivescriptstats-getstat.md)   
 [IActiveScriptStats 인터페이스](../../winscript/reference/iactivescriptstats-interface.md)