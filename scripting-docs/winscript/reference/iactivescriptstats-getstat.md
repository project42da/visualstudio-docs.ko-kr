---
title: IActiveScriptStats::GetStat | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptStats.GetStat
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptStats::GetStat
ms.assetid: 31fd15b3-0713-4b55-b4f7-bfd7ea198493
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 35e791661de6d360f747f8d823ad073c2eb81115
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptstatsgetstat"></a>IActiveScriptStats::GetStat
표준 스크립트 통계 중 하나를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetStat(  
   DWORD   stid,  
   ULONG*  pluHi,  
   ULONG*  pluLo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stid`  
 [in] 반환할 통계를 지정 합니다. 값 이어야 합니다.  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|SCRIPTSTAT_STATEMENT_COUNT|1|스크립트 시작 되거나 통계를 다시 설정한 이후에 실행 된 문 수를 반환 합니다.|  
  
 `pluHi`  
 [out] 통계를 나타내는 64 비트 부호 없는 정수의 상위 32 비트입니다.  
  
 `pluLo`  
 [out] 통계를 나타내는 64 비트 부호 없는 정수의 하위 32 비트입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값은 포함 되지만 다음 표에 있는 값으로 제한 되지 않습니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 표준 스크립트 통계 중 하나를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptStats::GetStatEx](../../winscript/reference/iactivescriptstats-getstatex.md)   
 [IActiveScriptStats 인터페이스](../../winscript/reference/iactivescriptstats-interface.md)