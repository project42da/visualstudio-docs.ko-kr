---
title: 'Idiasymbol:: Get_isdataaligned | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isDataAligned method
ms.assetid: ddd11a41-6c00-4829-acf4-aa1ace8c21a7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bc83909c398b7736c78f4eb2c3607578e40a9aa3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgetisdataaligned"></a>IDiaSymbol::get_isDataAligned
사용자 정의 형식 (UDT)에 몇 가지 특정 메모리 경계에 정렬 되어 있는지 여부를 지정 하는 플래그를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_isDataAligned(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pFlag`  
 [out] 반환 `TRUE` 일부 메모리 경계;에 UDT를 정렬 된가 같지 않으면, 반환 `FALSE`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성이 해당 기호를 사용할 수 있음을 의미 합니다.  
  
## <a name="remarks"></a>설명  
 이 속성은 기본이 아닌 데이터 정렬을 사용 하 여 실행 파일 컴파일될 때 일반적으로 설정 됩니다. Microsoft c + + 컴파일러 명령줄 옵션과 함께 데이터 맞춤을 변경할 수는 예를 들어 /Zp*#*여기서 *#* 는 바이트 값입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v 8.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)