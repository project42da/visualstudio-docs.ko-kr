---
title: 'Idialinenumber:: Get_linenumber | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaLineNumber::get_lineNumber method
ms.assetid: 2dff3fd9-097d-4645-bc1b-cb65ecbc42a6
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3ff07d70f6f1e75cb12d53246d77da58610b224f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idialinenumbergetlinenumber"></a>IDiaLineNumber::get_lineNumber
소스 파일의 줄 번호를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_lineNumber (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 소스 파일의 줄 번호를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="example"></a>예제  
  
```C++  
CComPtr< IDiaLineNumber> pLine;  
DWORD linenum;  
pLine->get_lineNumber( &linenum );  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)