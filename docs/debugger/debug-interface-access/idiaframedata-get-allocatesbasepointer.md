---
title: 'Idiaframedata:: Get_allocatesbasepointer | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_allocatesBasePointer method
ms.assetid: 8a33db5d-008c-4fe5-b64f-210c9b77f686
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e577a5a9723f388d829a70f51cd0a917abf157a1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idiaframedatagetallocatesbasepointer"></a>IDiaFrameData::get_allocatesBasePointer
이 주소 범위에는 코드에 대 한 기본 포인터 할당 되었는지 여부를 나타내는 플래그를 검색 합니다. 이 메서드는 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_allocatesBasePointer (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 반환 `TRUE` 기본 포인터를 할당 하 고; 그렇지 않으면 반환 `FALSE`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 이 속성에서 반환 되는 프로그램 문자열 또는 FPO_DATA, 이전 액세스 하는 코드를 통해서만 사용할 수 해야는 [idiaframedata:: Get_program](../../debugger/debug-interface-access/idiaframedata-get-program.md) 방법은 `NULL`합니다. 그렇지 않은 경우 프로그램 문자열 이전 레지스터 값을 계산 하는 데 필요한 모든 정보를 포함 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaFrameData::get_program](../../debugger/debug-interface-access/idiaframedata-get-program.md)