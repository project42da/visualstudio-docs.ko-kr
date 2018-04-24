---
title: 'Idiasymbol:: Get_isaggregated | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isAggregated method
ms.assetid: 24d280ef-6ea3-4958-9418-4ad3ca7c67c1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2ed27b239595034b55b66dfe71c261bb9f721371
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasymbolgetisaggregated"></a>IDiaSymbol::get_isAggregated
데이터 기호는 집계 또는 컬렉션 기호의;의 일부 인지 여부를 지정 하는 플래그를 검색 합니다. 컴파일러는 별도 엔터티로 집계 된 기호를 처리 하지만 단일 큰 기호의 일부는 실제로 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_isAggregated(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pFlag`  
 [out] 반환 `TRUE` 그렇지 않은 경우 반환 데이터 기호 부모 기호;에서 분할의 집계의 일부인 경우 `FALSE`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 의미는 속성은 해당 기호를 사용할 수 없습니다.  
  
## <a name="remarks"></a>설명  
 [idiasymbol:: Get_issplitted](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md) 방법은 `TRUE` 집계 된 기호의 부모 기호에 대 한 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v 8.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get_isSplitted](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md)