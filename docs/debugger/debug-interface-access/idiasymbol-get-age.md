---
title: 'Idiasymbol:: Get_age | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_age method
ms.assetid: 60d05654-e832-4a2e-a4a7-fe9922c459fe
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c7dfa9c7985a1944ebff625fae7fa6ec22200c78
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgetage"></a>IDiaSymbol::get_age
.Pdb 파일의 보존 기간 값을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_age (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] .Pdb 파일의 보존 기간 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 의미는 속성은 해당 기호를 사용할 수 없습니다.  
  
## <a name="remarks"></a>설명  
 알려진된 시간 값이 있으면; 나이 반드시 일치 하지 않습니다. .pdb 파일은.exe 파일을 해당와 동기화 하는 경우를 확인 하려면 일반적으로 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v7.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)