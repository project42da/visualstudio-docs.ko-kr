---
title: "CvCreateDefaultMarkerSeriesOfDefaultProvider 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cvmarkers/CvCreateDefaultMarkerSeriesOfDefaultProvider"
helpviewer_keywords: 
  - "CvCreateDefaultMarkerSeriesOfDefaultProvider 메서드"
ms.assetid: 24eb80f8-8fca-4c47-93b5-bb1eb8ffdffd
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# CvCreateDefaultMarkerSeriesOfDefaultProvider 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

기본 표식 계열을 기본 공급자를 만듭니다.  
  
## 구문  
  
```  
HRESULT CvCreateDefaultMarkerSeriesOfDefaultProvider(  
   _Out_ PCV_PROVIDER* ppProvider,  
   _Out_ PCV_MARKERSERIES* ppMarkerSeries  
);  
```  
  
#### 매개 변수  
 `ppProvider`  
 공급자 개체 변수의 주소입니다.  주소는 NULL 일 수 없습니다, 그리고 변수 값을 사용할 수 있습니다.  
  
 `ppMarkerSeries`  
 표식이 계열 개체 변수의 주소입니다.  주소는 NULL 일 수 없습니다, 그리고 변수 값을 사용할 수 있습니다.  
  
## 반환 값  
 S\_OK 공급자와 마커 시리즈는 만들었습니다 또는 경우의 오류 코드는 오류가 발생 했습니다.  성공\/실패 매크로를 사용하여 오류 조건을 확인할 수 있습니다.  
  
## 요구 사항  
 **헤더:** cvmarkers.h  
  
## 참고 항목  
 [C\+\+ 라이브러리 참조](../profiling/cpp-library-reference.md)