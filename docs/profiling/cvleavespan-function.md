---
title: CvLeaveSpan 함수 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvLeaveSpan
helpviewer_keywords:
- CvLeaveSpan method
ms.assetid: 3bf65fdf-a471-4efd-ac7a-03e701bbae5d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 381a6742dbedbe50b350764ca9e2637895db7ae2
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="cvleavespan-function"></a>CvLeaveSpan 함수
범위의 끝을 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CvLeaveSpan(  
   _In_ PCV_SPAN pSpan  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pSpan`  
 CvEnterSpan*에 대한 이전 호출에서 반환한 개체를 확장합니다. NULL일 수 없습니다.  
  
## <a name="return-value"></a>반환 값  
 메시지가 성공적으로 작성되는 경우 S_OK입니다. 오류가 발생한 경우 오류 코드입니다. SUCCEEDED/FAILED 매크로를 사용하여 오류 조건을 확인할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** cvmarkers.h  
  
## <a name="see-also"></a>참고 항목  
 [C++ 라이브러리 참조](../profiling/cpp-library-reference.md)