---
title: 'Idiaframedata:: Get_program | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaFrameData::get_program method
ms.assetid: 9201409e-b4b1-4e2e-a9f8-d17678ac538b
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a26982c1827b9d9b4a7ed09e8aa3af61c9141c9f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaframedatagetprogram"></a>IDiaFrameData::get_program
현재 함수를 호출 하기 전에 설정 하는 레지스터를 계산 하는 데 사용 되는 프로그램 문자열을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_program (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 프로그램 문자열을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 프로그램 문자열은 프롤로그를 설정 하기 위해 해석 되는 시퀀스 매크로입니다. 일반적인 스택 프레임에서 프로그램 문자열을 사용할 수는 예를 들어 `"$T0 $ebp = $eip $T0 4 + ^ = $ebp $T0 ^ = $esp $T0 8 + ="`합니다. 형식은 역방향 폴란드어 표기법으로 연산자는 피연산자를 수행 하는 위치입니다. `T0`스택에 있는 임시 변수를 나타냅니다. 이 예에서는 다음 단계를 수행합니다.  
  
1.  레지스터의 내용을 이동 `ebp` 를 `T0`합니다.  
  
2.  추가 `4` व र `T0` 를 생성 하는 주소, 해당 주소에서 값을 가져올 고 레지스터에 값을 저장 `eip`합니다.  
  
3.  에 저장 된 주소에서 값 가져오기 `T0` 레지스터에 값을 저장 하 고 `ebp`합니다.  
  
4.  추가 `8` व र `T0` 레지스터에 값을 저장 하 고 `esp`합니다.  
  
 프로그램 문자열은 CPU 함수가 현재 스택 프레임에 대 한 설정 호출 규칙에 특정 유의 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)