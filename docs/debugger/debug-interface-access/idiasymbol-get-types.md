---
title: 'Idiasymbol:: Get_types | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_types method
ms.assetid: 5f056e0c-e15b-4e00-8f78-aadc8574f7ea
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c53a8866856288aa039c0e23b6244da80184285d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgettypes"></a>IDiaSymbol::get_types
이 기호에 대 한 컴파일러 특정 형식의 배열을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_types (   
   DWORD       cTypes,  
   DWORD*      pcTypes,  
   IDiaSymbol* types[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cTypes`  
 [in] 데이터를 보유 하는 버퍼의 크기입니다.  
  
 `pcTypes`  
 [out] 를 작성 하는 형식의 수를 반환 하거나, 있는 경우는 `types` 매개 변수는 `NULL`, 한 다음 사용할 수 있는 유형의 총 수입니다.  
  
 `types[]`  
 [out] 사용 하 여 입력할 수 있는 배열은 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 이 기호에 대 한 모든 형식을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 의미는 속성은 해당 기호를 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)