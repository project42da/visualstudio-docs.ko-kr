---
title: IDiaSymbol::get_isCTypes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackWalker2 interface
ms.assetid: 00c73cf9-2933-472e-bc1d-d041f4d7e412
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 66474caf8b4008efcb4ee898b0275be4bf45bc1d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgetisctypes"></a>IDiaSymbol::get_isCTypes
C 형식 기호 파일에 포함 되는지 여부를 나타내는 플래그를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_isCTypes(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pFlag`  
 [out] 반환 `TRUE` 기호 파일에 있는 경우 C 형식, 그렇지 않으면 반환 `FALSE`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성이 해당 기호를 사용할 수 있음을 의미 합니다.  
  
## <a name="remarks"></a>설명  
 이 속성은에서 사용할 수는 `SymTagExe` 기호 형식을 (참조 [Exe](../../debugger/debug-interface-access/exe.md)).  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v 8.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [Exe](../../debugger/debug-interface-access/exe.md)