---
title: 'Idiasymbol:: Get_timestamp | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_timeStamp method
ms.assetid: 5d707b76-dbaa-4d88-86c3-6f3672cc6d4c
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6e64673e1e073464df806df52f8096d233de6e7e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgettimestamp"></a>IDiaSymbol::get_timeStamp
내부 실행 파일의 타임 스탬프를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_timeStamp (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 내부 실행 파일의 타임 스탬프를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 의미는 속성은 해당 기호를 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)