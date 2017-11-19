---
title: 'Idialinenumber:: Get_columnnumber | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaLineNumber::get_columnNumber method
ms.assetid: e317f29a-6525-46a7-8421-33985392f8fd
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 03673b339336cc5c5cdb32b284cf3c7cc1b38998
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idialinenumbergetcolumnnumber"></a>IDiaLineNumber::get_columnNumber
식 또는 문 시작 되는 열 번호를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[C++]  
HRESULT get_columnNumber (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 식 또는 문 시작 되는 열 번호를 반환 합니다. 값이 0 인 경우 다음 열 정보가 나타나지 않습니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드에서 반환 된 열 값이 문의 줄에서 첫 번째 문자를 줄에 대 한 바이트 오프셋입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)