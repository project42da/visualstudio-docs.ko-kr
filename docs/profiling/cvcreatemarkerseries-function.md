---
title: "CvCreateMarkerSeries 함수 | Microsoft Docs"
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
  - "cvmarkers/CvCreateMarkerSeriesA"
  - "cvmarkers/CvCreateMarkerSeriesW"
helpviewer_keywords: 
  - "CvCreateMarkerSeriesA 메서드"
  - "CvCreateMarkerSeriesW 메서드"
ms.assetid: e280530b-137a-43a7-8643-aa514ab86ed7
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# CvCreateMarkerSeries 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지정된 공급자에 대한 표식 계열을 만듭니다.  
  
## 구문  
  
```  
_Check_return_ HRESULT CvCreateMarkerSeriesW(  
    _In_ PCV_PROVIDER  pProvider,  
    _In_ LPCWSTR pSeriesName,  
    _Out_ PCV_MARKERSERIES* ppMarkerSeries);  
  
_Check_return_ HRESULT CvCreateMarkerSeriesA(  
    _In_ PCV_PROVIDER  pProvider,  
    _In_ LPCSTR pSeriesName,  
    _Out_ PCV_MARKERSERIES* ppMarkerSeries);  
```  
  
#### 매개 변수  
 `pProvider`  
 이전에 CvInitProvider에 의해 초기화 되는 공급자 개체입니다.  NULL 일 수 없습니다.  
  
 `pSeriesName`  
 표식 계열 이름입니다.  NULL 일 수 없지만 빈 문자열을 사용할 수 있습니다.  
  
 `ppMarkerSeries`  
 표식이 계열 컨텍스트를 저장할 출력 변수의 주소입니다.  NULL 일 수 없습니다.  
  
## 반환 값  
 S\_OK 마커 시리즈가 성공적으로 만들어졌거나 이 경우 오류 코드에는 오류가 발생 했습니다.  성공\/실패 매크로를 사용하여 오류 조건을 확인할 수 있습니다.  
  
## 요구 사항  
 **헤더:** cvmarkers.h  
  
 **유니코드:** CvCreateMarkerSeriesW  
  
 **ANSI:** CvCreateMarkerSeriesA  
  
## 참고 항목  
 [C\+\+ 라이브러리 참조](../profiling/cpp-library-reference.md)