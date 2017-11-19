---
title: 'Idiasectioncontrib:: Get_informational | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSectionContrib::get_informational method
ms.assetid: 5351e89f-7db1-4f8e-9e57-2dd1c74002e0
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a6f3c664b670625b36f25d7ff582afccb7f155c0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasectioncontribgetinformational"></a>IDiaSectionContrib::get_informational
섹션 메모 또는 비슷한 정보에 포함 되는지 여부를 나타내는 플래그를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_informational(  
   BOOL* pRetVal  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 반환 `TRUE` 섹션에는 설명 또는 다른 정보를 포함 하는 경우는 그렇지 않으면 반환 `FALSE`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 일반적으로.directive 섹션에는 정보가 포함 되어 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)