---
title: 'Idiasymbol:: Get_locationtype | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_locationType method
ms.assetid: fbb09c43-ebb7-4b4f-be53-ccff86eb183a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0c6bcd1c204a68f9e139c12341b722bebb28cba5
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasymbolgetlocationtype"></a>IDiaSymbol::get_locationType
데이터 기호 위치 유형을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_locationType (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 값을 반환 된 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md) 와 같은 위치에 대 한 형태의 데이터 기호를 지정 하는 열거형 `static` 또는 `local`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 의미는 속성은 해당 기호를 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)