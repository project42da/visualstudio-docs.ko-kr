---
title: 'Idiasymbol:: Get_editandcontinueenabled | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_editAndContinueEnabled method
ms.assetid: cd703c64-9ff8-4654-8493-8cde9309cb22
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7d82b1ab1e02395dff213aef9ce7e7fe566b77a2
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasymbolgeteditandcontinueenabled"></a>IDiaSymbol::get_editAndContinueEnabled
검색 모듈을 사용 하 여 컴파일한 있는지 여부를 나타내는 플래그는 [/Z7, /Zi, /ZI (디버깅 정보 형식)](/cpp/build/reference/z7-zi-zi-debug-information-format) 컴파일러 스위치입니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_editAndContinueEnabled (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 반환 `TRUE` 컴파일;에서 편집 하며 계속 하기를 설정할 경우는 그렇지 않으면 반환 `FALSE`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성이 해당 기호를 사용할 수 있음을 의미 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v7.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [/Z7, /Zi, /ZI(디버깅 정보 형식)](/cpp/build/reference/z7-zi-zi-debug-information-format)