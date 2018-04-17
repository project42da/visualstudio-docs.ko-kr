---
title: 'Idiasymbol:: Get_typeids | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_typeIds method
ms.assetid: 5166e647-fde5-4efe-92bf-77f8ae3fbc9b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 21c0aad37f51ca388c73ada62512887ff67e3e9a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgettypeids"></a>IDiaSymbol::get_typeIds
이 기호에 대 한 컴파일러 관련 형식 식별자 값의 배열을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_typeIds (   
   DWORD  cTypeIds,  
   DWORD* pcTypeIds,  
   DWORD  typeIds[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cTypeIds`  
 [in] 데이터를 보유 하는 버퍼의 크기입니다.  
  
 `pcTypeIds`  
 [out] 수를 반환 `typeIds` 를 작성 하거나, 있는 경우 `typeIds` 은 `NULL`, 유형 식별자를 사용할 수 있는 다음 총 수입니다.  
  
 `typeIds[]`  
 [out] 배열 유형 식별자를 채울 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 의미는 속성은 해당 기호를 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)