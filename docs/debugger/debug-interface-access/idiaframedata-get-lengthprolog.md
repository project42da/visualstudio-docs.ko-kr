---
title: 'Idiaframedata:: Get_lengthprolog | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_lengthProlog method
ms.assetid: 5f042ff1-e74e-430a-be34-d2cf1b18eff2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8033e0f769c0222dc8c3ee90d680ea6f2de279fa
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaframedatagetlengthprolog"></a>IDiaFrameData::get_lengthProlog
블록의 프롤로그 코드의 바이트 수를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_lengthProlog (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 프롤로그 코드의 바이트 수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 프롤로그 코드는 레지스터를 유지 하 고 CPU 상태를 설정 하는 함수에 대 한 설정 하는 일련의 명령입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)