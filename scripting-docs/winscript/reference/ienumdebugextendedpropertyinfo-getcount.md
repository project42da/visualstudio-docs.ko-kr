---
title: IEnumDebugExtendedPropertyInfo::GetCount | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IEnumDebugExtendedPropertyInfo.GetCount
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumDebugExtendedPropertyInfo::GetCount
ms.assetid: 2c862f62-b57c-4cd4-ac4e-7d372fbda9a4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cb58bd6fef639091cec4cce1750833bd47e8763e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ienumdebugextendedpropertyinfogetcount"></a>IEnumDebugExtendedPropertyInfo::GetCount
개수를 가져옵니다 `ExtendedDebugPropertyInfo` 열거자에는 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCount (  
   ULONG* pcelt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcelt`  
 [out] 개수를 반환 `ExtendedDebugPropertyInfo` 열거자에는 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugExtendedPropertyInfo 인터페이스](../../winscript/reference/ienumdebugextendedpropertyinfo-interface.md)   
 [ExtendedDebugPropertyInfo 구조체](../../winscript/reference/extendeddebugpropertyinfo-structure.md)