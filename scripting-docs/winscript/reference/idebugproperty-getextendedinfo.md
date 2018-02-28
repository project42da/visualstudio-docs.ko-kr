---
title: IDebugProperty::GetExtendedInfo | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugProperty.GetExtendedInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugProperty::GetExtendedInfo
ms.assetid: a989ade5-16d5-4ee6-8d8a-8dcbfad24034
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cc549ecc4cfa3b3cbbb754585c751b16df2fd8a6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugpropertygetextendedinfo"></a>IDebugProperty::GetExtendedInfo
확장 속성에 대 한 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetExtendedInfo (  
   ULONG  cInfos,  
   GUID*  rgguidExtendedInfo,  
   VARIANT* pExtendedInfo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cInfos`  
 [in] 확장된 정보 개체의 수입니다.  
  
 `rgguidExtendedInfo`  
 [in] 배열 `GUID`동시에 여러 항목의 확장된 정보를 검색할 수 있도록 s 전달 됩니다.  
  
 `pExtendedInfo`  
 [out] 배열을 반환 `VARIANT`s 확장된 속성 정보를 검색 하는 데 사용할 수 있는 합니다.  
  
## <a name="return-value"></a>반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`합니다.  
  
## <a name="remarks"></a>설명  
 이 인터페이스는이 개체에 대 한 정보를 확장 가져옵니다. API를 사용 하 여 검색을 충족 하지 않는 정보 검색 않으려는 경우에 존재 `IDebugProperty::GetPropertyInfo`).  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)