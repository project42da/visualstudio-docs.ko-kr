---
title: IPerPropertyBrowsing2::GetPredefinedStrings | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IPerPropertyBrowsing2.GetPredefinedStrings
apilocation: scrobj.dll
helpviewer_keywords: IPerPropertyBrowsing2::GetPredefinedStrings
ms.assetid: d2fa30f7-a566-4dbd-8b47-ffdc00419771
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e07d52eca9434acc7e54f3b35b111cf12af0a871
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iperpropertybrowsing2getpredefinedstrings"></a>IPerPropertyBrowsing2::GetPredefinedStrings
호출자에 게가 계산된 하는이 속성에 대 한 잠재적인 값을 나타내는 문자열 포인터 배열을 사용 하 여 목록 상자를 채울 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetPredefinedStrings(  
   DISPID  dispid,  
   CALPOLESTR*  pCaStrings,  
   CADWORD*  pCaCookies  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dispid`  
 [in] 디스패치를 호출자에 게 요청 하는 문자열 목록 속성의 식별자입니다.  
  
 `pCaStrings`  
 [out] 요소 수와 문자열 포인터 메서드가 할당 한 배열의 주소를 포함 하는 호출자 할당, 계산 배열 구조에 대 한 포인터입니다. 메서드가 실패 없는 메모리를 할당 하 고 구조체의 내용을 정의 되지 않습니다.  
  
 `pCaCookies`  
 [out] 요소 수와 Dword의 메서드가 할당 한 배열의 주소를 포함 하는 호출자 할당, 계산 배열 구조에 대 한 포인터입니다. 메서드가 실패 없는 메모리를 할당 하 고 구조체의 내용을 정의 되지 않습니다.  
  
## <a name="return-value"></a>반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IPerPropertyBrowsing2 인터페이스 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)