---
title: IDiaSymbol::get_liveRangeStartAddressSection | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_liveRangeStartAddressSection
ms.assetid: 892b80ff-5957-4233-b4d7-6144167be289
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: db03df7c8181065849bd2fc61f0149f1df3694c3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetliverangestartaddresssection"></a>IDiaSymbol::get_liveRangeStartAddressSection
로컬 기호의 유효 범위 시작 주소 섹션 부분을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_liveRangeStartAddressSection (   
   DWORD* section  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `section`  
 [out] 시작 주소 범위의 섹션 부분을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
> [!NOTE]
>  반환 된 오류 코드는 기호 라이브 범위 정보가 없는 것을 의미 합니다.  
  
## <a name="remarks"></a>설명  
 오프셋 및는 섹션으로 구성 된 주소는 기호의 유효 범위 시작.  
  
 주소의 오프셋된 부분을 사용 [IDiaSymbol::get_liveRangeStartAddressOffset](../../debugger/debug-interface-access/idiasymbol-get-liverangestartaddressoffset.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia100.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)