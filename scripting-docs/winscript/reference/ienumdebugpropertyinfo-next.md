---
title: IEnumDebugPropertyInfo::Next | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IEnumDebugPropertyInfo.Next
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumDebugPropertyInfo::Next
ms.assetid: 052837ac-1599-49cc-9a5a-ba90f992eeff
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bc1e25a865ab1e21ab011e3a5bd0cc3b74f4abf2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ienumdebugpropertyinfonext"></a>IEnumDebugPropertyInfo::Next
지정된 된 수의 검색 `DebugPropertyInfo` 열거형 시퀀스에는 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Next (  
   ULONGcelt,  
   DebugPropertyInfo*rgelt,  
   ULONG* pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 수가 `DebugPropertyInfo`구조를 검색할 수 있습니다.  
  
 `rgelt`  
 [out] 배열 `DebugPropertyInfo` 구조를 검색 합니다.  
  
 `pceltFetched`  
 [out] 개수를 반환 `DebugPropertyInfo` 실제로 검색 된 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugPropertyInfo 인터페이스](../../winscript/reference/ienumdebugpropertyinfo-interface.md)   
 [DebugPropertyInfo 구조체](../../winscript/reference/debugpropertyinfo-structure.md)