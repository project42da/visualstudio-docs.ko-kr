---
title: IDiaPropertyStorage::ReadBSTR | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaPropertyStorage::ReadBSTR
ms.assetid: 7214643b-3286-48ed-90aa-0fe95b4cae5b
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 93ab7271ccef1819e16e4cdb4c690f82bfaeec35
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiapropertystoragereadbstr"></a>IDiaPropertyStorage::ReadBSTR
읽고 `BSTR` 속성 집합에 있는 값입니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT ReadBSTR (   
   PROPID id,  
   BSTR*  pValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `id`  
 [in] 읽을 속성의 식별자 (`PROPID` 으로 WTypes.h에 정의 되어 있는 한 `ULONG`).  
  
 `pValue`  
 [out] 속성 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드가 반환 됩니다. 반환 `E_INVALIDARG` 형식의 속성이 없으면 `BSTR`합니다.  
  
## <a name="remarks"></a>설명  
 A `BSTR` 를 0으로 끝나는 와이드 문자열로 Windows에 의해 정의 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)