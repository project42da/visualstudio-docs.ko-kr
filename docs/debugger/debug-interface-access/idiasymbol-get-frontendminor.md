---
title: 'Idiasymbol:: Get_frontendminor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_frontEndMinor method
ms.assetid: 40792153-827c-4859-be7c-6aa16d5abab6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2d0d7741d084a1adf8f7bdc7ac7c2e0f5e33cc72
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgetfrontendminor"></a>IDiaSymbol::get_frontEndMinor
프런트 엔드 부 버전 번호를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_frontEndMinor (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] Front.end 부 버전 번호를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 의미는 속성은 해당 기호를 사용할 수 없습니다.  
  
## <a name="remarks"></a>설명  
 컴파일러는 일반적으로 두 가지 기본 요소로 이루어져: 소스 코드를 중간 형식으로 구문 분석을 처리 하는 프런트 엔드 (파서) 및 백 엔드 (코드 생성기) 어셈블리로 중간 형식으로 변환 합니다. 프런트 엔드는 백 엔드에서 보다 다른 버전에 대 한 일반적이 지 않습니다.  
  
 프런트 엔드 또는 백 엔드 버전 번호는 세 부분으로 구성 됩니다: \<주요 >.\< 사소한 > 합니다. \<빌드 > 여기서 \<주요 > 주 버전 번호는 \<부 >은 부 버전 번호 및 \<빌드 >는 빌드 번호입니다. 예를 들어 13.10.3077 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v7.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)