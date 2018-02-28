---
title: IDebugExtendedProperty::GetExtendedPropertyInfo | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugExtendedProperty.GetExtendedPropertyInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugExtendedProperty::GetExtendedPropertyInfo
ms.assetid: 56edf538-5082-4653-82b6-e6640d6f61ba
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7109346dd8189395cfdd366ff622dfac00744382
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugextendedpropertygetextendedpropertyinfo"></a>IDebugExtendedProperty::GetExtendedPropertyInfo
보다 단순한 보다 더 많은 정보는 확장된 속성에 대 한 확장된 정보 인출 `IDebugProperty`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetExtendedPropertyInfo(  
   EX_DBGPROP_INFO_FLAGS  dwFieldSpec,  
   UINT  nRadix,  
   ExtendedDebugPropertyInfo*  pExtendedPropertyInfo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwFieldSpec`  
 [in] 필드에서 채울 수를 결정 하는 EX_DBGPROP_INFO_FLAGS 상수를 지정 된 `ExtendedDebugPropertyInfo` 구조입니다.  
  
 `nRadix`  
 [in] 모든 숫자 정보를 해석 하는 데 사용할 기 수입니다.  
  
 `pExtendedPropertyInfo`  
 [out] 반환 된 `ExtendedDebugPropertyInfo` 속성을 설명 하는 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExtendedProperty 인터페이스](../../winscript/reference/idebugextendedproperty-interface.md)   
 [EX_DBGPROP_INFO_FLAGS](../../winscript/reference/ex-dbgprop-info-flags.md)   
 [ExtendedDebugPropertyInfo 구조체](../../winscript/reference/extendeddebugpropertyinfo-structure.md)