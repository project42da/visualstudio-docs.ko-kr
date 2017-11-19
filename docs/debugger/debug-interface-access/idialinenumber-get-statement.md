---
title: 'Idialinenumber:: Get_statement | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaLineNumber::get_statement method
ms.assetid: 22b8ee29-79ef-427f-bd05-00d255ab836b
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 05cb3f85fe2f1ea82622a4537b89895a44eebf63
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idialinenumbergetstatement"></a>IDiaLineNumber::get_statement
프로그램 소스에 식을 보다는 문의 시작 부분이 줄 정보를 설명 한다는 사실을 나타내는 플래그를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_statement (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 반환 `TRUE` 이 줄 정보 프로그램 소스에서 문의 시작 부분에 대해 설명 하는 경우.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 문은 여러 줄에 걸쳐 있을 수 있습니다. 이 메서드는 연결 된 줄 번호 여러 줄 문의 시작을 표시 하는 경우를 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)