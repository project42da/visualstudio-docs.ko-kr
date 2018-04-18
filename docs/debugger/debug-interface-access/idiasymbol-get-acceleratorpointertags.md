---
title: IDiaSymbol::get_acceleratorPointerTags | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 30e13cee-e511-49ec-affd-99b0097071b2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 159464305063fd2d40109ba000421f0e5cc72d09
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgetacceleratorpointertags"></a>IDiaSymbol::get_acceleratorPointerTags
C + + AMP 액셀러레이터 스텁 함수에 해당 하는 모든 액셀러레이터 포인터 태그 값을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_acceleratorPointerTags(   
   DWORD          cnt,  
   DWORD*         pcnt,  
   DWORD*         pPointerTags);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cnt`  
 [in] 출력 배열의 크기 `pPointerTags`합니다.  
  
 `pcnt`  
 [out] C + + AMP 액셀러레이터 스텁 함수에서 가속기 포인터 태그의 수입니다.  
  
 `pPointerTags`  
 [out] A `DWORD` c + + AMP 액셀러레이터 스텁 함수에서 가속기 포인터 태그 값으로 채워진 배열 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 프로그램 `IDiaSymbol` c + + AMP 액셀러레이터 스텁 함수에 해당 하는 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)