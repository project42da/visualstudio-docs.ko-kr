---
title: IEnumDebugExtendedPropertyInfo::Skip | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IEnumDebugExtendedPropertyInfo.Skip
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumDebugExtendedPropertyInfo::Skip
ms.assetid: a0b4a9fc-e122-482b-9384-b83c460b61fe
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cd7f686ccaa5a3195b82458cf3ee11f02be104f3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ienumdebugextendedpropertyinfoskip"></a>IEnumDebugExtendedPropertyInfo::Skip
지정 된 개수의 건너뜁니다 `ExtendedDebugPropertyInfo` 열거형 시퀀스에는 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 수가 `ExtendedDebugPropertyInfo` 건너뛸 열거 시퀀스에서 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`합니다. 반환 `S_FALSE` 경우 열거형의 끝에 현재 요소 포인터를 설정 하 고 `celt` 열거자에 왼쪽 요소의 개수 보다 큽니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugExtendedPropertyInfo 인터페이스](../../winscript/reference/ienumdebugextendedpropertyinfo-interface.md)   
 [ExtendedDebugPropertyInfo 구조체](../../winscript/reference/extendeddebugpropertyinfo-structure.md)