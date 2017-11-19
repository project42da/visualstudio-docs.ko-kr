---
title: 'Idiasymbol:: Get_hasseh | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_hasSEH method
ms.assetid: 1a709ded-22c8-464c-97be-eba5e464210c
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a0e2ffb58b62acd35fea209e2c0c66fc7f1a9cf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgethasseh"></a>IDiaSymbol::get_hasSEH
함수 하나 포함 되는지 여부를 지정 하는 플래그를 검색 [구조적 예외 처리 (C/c + +)](/cpp/cpp/structured-exception-handling-c-cpp) (예를 들어 __try /\__except 블록).  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_hasSEH(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pFlag`  
 [out] 반환 `TRUE` 함수에 있는 경우 모든 구조적된 예외 처리 블록이; 그렇지 않으면 반환 `FALSE`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 의미는 속성은 해당 기호를 사용할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v 8.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [구조적 예외 처리(C/C++)](/cpp/cpp/structured-exception-handling-c-cpp)