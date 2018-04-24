---
title: 'Idiasymbol:: Get_interruptreturn | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_interruptReturn method
ms.assetid: 9665da6c-4cc0-41d7-b2e2-0d9e50174cf8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e62fd85e8c60910be0b88c3eb27532edd874563a
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasymbolgetinterruptreturn"></a>IDiaSymbol::get_interruptReturn
인터럽트 명령에서 반환 된 함수에 포함 되어 있는지 여부를 지정 하는 플래그를 검색 (예를 들어 X86 어셈블리 코드 `iret`).  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_interruptReturn(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pFlag`  
 [out] 반환 `TRUE` 함수는 인터럽트 명령;에서 반환 하는 경우는 그렇지 않으면 반환 `FALSE`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성이 해당 기호를 사용할 수 있음을 의미 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v 8.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)