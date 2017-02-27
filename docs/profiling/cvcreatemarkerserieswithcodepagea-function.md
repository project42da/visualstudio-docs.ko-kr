---
title: "CvCreateMarkerSeriesWithCodePageA 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cvmakers/CvCreateMarkerSeriesWithCodePageA"
helpviewer_keywords: 
  - "CvCreateMarkerSeriesWithCodePageA 메서드"
ms.assetid: 3d7ed601-2222-4be9-a557-f217db008753
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# CvCreateMarkerSeriesWithCodePageA 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지정된 된 공급자와 지정 된 코드 페이지에 대 한 표식 계열을 만듭니다.  텍스트 마커 API ANSI 함수 작성에 대 한 명시적으로 코드 페이지를 지정 하려면이 함수를 사용할 수 있습니다.  코드 페이지를 설정할 경우 추적이 캡처되고 다국어 로케일을 사용하여 다른 컴퓨터에서 다음 분석에 유용할 수 있습니다.  GetACP\(\) 함수에 의해 반환 되는 코드 페이지는 기본적으로 사용 됩니다.  
  
## 구문  
  
```  
HRESULT CvCreateMarkerSeriesWithCodePageA(  
   _In_ PCV_PROVIDER pProvider,  
   _In_ LPCSTR pSeriesName,  
   _In_ UINT nTextCodePage,  
   _Out_ PCV_MARKERSERIES* ppMarkerSeries  
);  
```  
  
#### 매개 변수  
 `pProvider`  
 이전에 CvInitProvider에 의해 초기화 되는 공급자 개체입니다.  NULL 일 수 없습니다.  
  
 `pSeriesName`  
 표식 계열 이름입니다.  NULL 일 수 없지만 빈 문자열을 사용할 수 있습니다.  
  
 `nTextCodePage`  
 코드 페이지가 잘못되었습니다.  
  
 `ppMarkerSeries`  
 표식이 계열 컨텍스트를 저장할 출력 변수의 주소입니다.  NULL 일 수 없습니다.  
  
## 반환 값  
 S\_OK 마커 시리즈가 성공적으로 만들어졌거나 이 경우 오류 코드에는 오류가 발생 했습니다.  성공\/실패 매크로를 사용하여 오류 조건을 확인할 수 있습니다.  
  
## 요구 사항  
 **헤더:** cvmarkers.h  
  
## 참고 항목  
 [C\+\+ 라이브러리 참조](../profiling/cpp-library-reference.md)