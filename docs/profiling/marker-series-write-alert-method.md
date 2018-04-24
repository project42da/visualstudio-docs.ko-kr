---
title: marker_series::write_alert 메서드 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic:marker_series::write_alert
helpviewer_keywords:
- Concurrency::diagnostic:marker_series::write_alert method
ms.assetid: 9d5465c7-f862-47a7-b249-4116605075a6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8072fbee78312a5b44bff076e563c638a35d1d64
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="markerserieswritealert-method"></a>marker_series::write_alert 메서드
동시성 시각화 도우미 추적 파일에 경고를 씁니다.  
  
## <a name="syntax"></a>구문  
  
```  
void write_alert(  
   _In_ LPCTSTR _Format,  
   ...  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `_Format`  
 인수 목록의 개체에 해당하는 0개 이상의 서식 항목과 결합된 텍스트를 포함하는 합성 서식 문자열입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** cvmarkersobj.h  
  
 **네임스페이스:** Concurrency::diagnostic  
  
## <a name="see-also"></a>참고 항목  
 [marker_series 클래스](../profiling/marker-series-class.md)