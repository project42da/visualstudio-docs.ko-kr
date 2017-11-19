---
title: IDebugExtendedProperty::EnumExtendedMembers | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugExtendedProperty.EnumExtendedMembers
apilocation: scrobj.dll
helpviewer_keywords: IDebugExtendedProperty::EnumExtendedMembers
ms.assetid: 27cdb091-da4e-44d2-a631-31ae00468b98
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 81b1cbb9b36d7ae237551aad2677f9480c615b88
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugextendedpropertyenumextendedmembers"></a>IDebugExtendedProperty::EnumExtendedMembers
확장된 속성의 멤버를 열거 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumExtendedMembers(  
   EX_DBGPROP_INFO_FLAGS  dwFieldSpec,  
   UINT  nRadix,  
   IEnumDebugExtendedPropertyInfo**  ppeepi  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwFieldSpec`  
 [in] 필드에 열거 된 확장 디버그 속성 구조를 결정 하는 EX_DBGPROP_INFO_FLAGS 상수는 채워지도록 지정 합니다.  
  
 `nRadix`  
 [in] 모든 숫자 정보를 해석 하는 데 사용할 기 수입니다.  
  
 `ppeepi`  
 [out] 반환 된 `IEnumDebugExtendedPropertyInfo` 멤버 속성을 열거 하는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExtendedProperty 인터페이스](../../winscript/reference/idebugextendedproperty-interface.md)   
 [EX_DBGPROP_INFO_FLAGS](../../winscript/reference/ex-dbgprop-info-flags.md)   
 [ExtendedDebugPropertyInfo 구조체](../../winscript/reference/extendeddebugpropertyinfo-structure.md)