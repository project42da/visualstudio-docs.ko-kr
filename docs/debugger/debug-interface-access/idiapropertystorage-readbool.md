---
title: IDiaPropertyStorage::ReadBOOL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaPropertyStorage::ReadBOOL
ms.assetid: ad1822db-4572-48f7-9919-f8137f6701f2
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9632ada4b3e19013f05006d22770c08e83eac5ba
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiapropertystoragereadbool"></a>IDiaPropertyStorage::ReadBOOL
읽고 `BOOL` 속성 집합에 있는 값입니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT ReadBOOL (   
   PROPID id,  
   BOOL*  pValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `id`  
 [in] 읽을 속성의 식별자 (`PROPID` 으로 WTypes.h에 정의 되어 있는 한 `ULONG`).  
  
 `pValue`  
 [out] 속성 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드가 반환 됩니다. 반환 `E_INVALIDARG` 형식의 속성이 없으면 `BOOL`합니다.  
  
## <a name="remarks"></a>설명  
 일관 된 결과 대 한 해석 된 `BOOL` 값을 0이 아닌 값은 `TRUE` 0이 고 `FALSE`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)