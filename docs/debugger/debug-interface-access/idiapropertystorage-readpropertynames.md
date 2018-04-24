---
title: IDiaPropertyStorage::ReadPropertyNames | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadPropertyNames
ms.assetid: f8bcab77-afca-4a8f-8710-697842f8a518
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a13ac0e3a1af8dc20fe63f832e7a19d7bf40c271
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiapropertystoragereadpropertynames"></a>IDiaPropertyStorage::ReadPropertyNames
에 대 한 문자열 이름에 해당 하는 검색 속성 식별자를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT ReadPropertyNames (  
   ULONG         cpropid,  
   PROPID const* rgpropid,  
   BSTR*         rglpwstrName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cpropid`  
 [in] 속성에는 id 수 `rgpropid`합니다.  
  
 `rgpropid`  
 [in] 이름을 가져올 속성 id의 배열 (`PROPID` 으로 WTypes.h에 정의 된 한 `ULONG`).  
  
 `rglpwstrName`  
 [out에서] 지정 된 속성 id에 대 한 속성 이름 배열입니다. 배열 미리 할당 요청 된 수의 속성 이름 이어야 하며 이상을 보유할 수 있어야 `cpropid``BSTR` 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 반환 된 속성 이름을 해제 해야 합니다 (호출 하 여는 `SysFreeString` 함수) 더 이상 필요 없는 경우.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)