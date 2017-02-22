---
title: "CvReleaseMarkerSeries 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cvmarkers/CvReleaseMarkerSeries"
helpviewer_keywords: 
  - "CvReleaseMarkerSeries 메서드"
ms.assetid: 3b4711ee-e534-411d-9128-f69cd7932a48
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# CvReleaseMarkerSeries 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

마커 시리즈를 해제합니다.  중단 될 수 있습니다 그렇지 않으면 응용 프로그램을 해제 한 후 표식 series 개체를 사용 하지 마십시오.  마커 일련 해제 하지 않으면 메모리 누수가 발생 합니다.  
  
## 구문  
  
```  
HRESULT CvReleaseMarkerSeries(  
   _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries  
);  
```  
  
#### 매개 변수  
 `pMarkerSeries`  
 공급자 개체 변수의 주소입니다.  주소는 NULL 일 수 없습니다, 그리고 변수 값을 사용할 수 있습니다.  
  
## 반환 값  
 S\_OK 마커 시리즈가 성공적으로 만들어졌거나 이 경우 오류 코드에는 오류가 발생 했습니다.  성공\/실패 매크로를 사용하여 오류 조건을 확인할 수 있습니다.  
  
## 요구 사항  
 **헤더:** cvmarkers.h  
  
## 참고 항목  
 [C\+\+ 라이브러리 참조](../profiling/cpp-library-reference.md)