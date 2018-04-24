---
title: BasicType | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BasicType enumeration
ms.assetid: 19ae53ba-cd6e-47b6-9f94-27ae663ce955
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cfccb444eab802f7caa5cf83faff0ddc7a51c389
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="basictype"></a>BasicType
심볼의 기본 유형을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
enum BasicType {   
   btNoType   = 0,  
   btVoid     = 1,  
   btChar     = 2,  
   btWChar    = 3,  
   btInt      = 6,  
   btUInt     = 7,  
   btFloat    = 8,  
   btBCD      = 9,  
   btBool     = 10,  
   btLong     = 13,  
   btULong    = 14,  
   btCurrency = 25,  
   btDate     = 26,  
   btVariant  = 27,  
   btComplex  = 28,  
   btBit      = 29,  
   btBSTR     = 30,  
   btHresult  = 31  
};  
```  
  
## <a name="elements"></a>요소  
 btNoType  
 기본 형식이 지정 됩니다.  
  
 btVoid  
 기본 형식이 `void`합니다.  
  
 btChar  
 기본 형식이 `char` (C/c + + 형식).  
  
 btWChar  
 기본 형식이 와이드 (유니코드) 문자 (`WCHAR`).  
  
 btInt  
 기본 형식이 `signed int` (C/c + + 형식).  
  
 btUInt  
 기본 형식이 `unsigned int` (C/c + + 형식).  
  
 btFloat  
 기본 형식이 부동 소수점 수 (`FLOAT`).  
  
 btBCD  
 이진 코딩 decimal 기본 형식입니다 (`BCD`).  
  
 btBool  
 기본 형식은 부울 (`BOOL`).  
  
 btLong  
 기본 형식이 `long int` (C/c + + 형식).  
  
 btULong  
 기본 형식이 `unsigned long int` (C/c + + 형식).  
  
 btCurrency  
 기본 유형에 통화입니다.  
  
 btDate  
 기본 형식은 날짜/시간 (`DATE`).  
  
 btVariant  
 기본 형식이 변수 형식이 구조 임 (`VARIANT`).  
  
 btComplex  
 기본 유형은 복소수입니다.  
  
 btBit  
 기본 형식은 비트입니다.  
  
 btBSTR  
 기본 유형은 기본 또는 이진 문자열입니다 (`BSTR`).  
  
 btHresult  
 기본 형식이 `HRESULT`합니다.  
  
## <a name="remarks"></a>설명  
 이 열거형의 값을 반환 된 [idiasymbol:: Get_basetype](../../debugger/debug-interface-access/idiasymbol-get-basetype.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: cvconst.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasymbol:: Get_basetype](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)   
 [IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)