---
title: "방법: 프로파일러 데이터 파일 비교 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vsperf.choosediffbinaries"
helpviewer_keywords: 
  - "프로파일러 결과 파일, 비교 방법"
  - "프로파일링 도구, 프로파일러 결과 파일 비교 방법"
ms.assetid: 1905b45d-c6b3-43c8-87b1-1aee734f37f9
caps.latest.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 20
---
# 방법: 프로파일러 데이터 파일 비교
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

비교\("Diff"\) 보고서나 뷰를 만들어 두 개의 서로 다른 프로파일러 데이터 파일\(.vsp 또는 .vsps\)의 결과를 비교할 수 있습니다.  비교를 통해 프로파일링 세션 간에 나타나는 차이점, 성능 재발 및 향상을 볼 수 있습니다.  
  
 diff 보고서에는 데이터가 테이블 뷰로 표시됩니다.  테이블에는 델타가 표시되거나 기준에서 변경된 값이 표시됩니다.  이 값은 이전 값, 기준 값, 새 분석의 결과 값 간의 차이를 확인하여 계산됩니다.  
  
 프로파일러 데이터는 코드의 함수, 응용 프로그램의 모듈, 줄, IP\(명령 포인터\) 및 형식을 기준으로 비교될 수 있습니다.  
  
 노이즈를 줄이고 행의 테이블 뷰에서 지정된 크기만큼 변경되지 않은 데이터를 필터링하여 제외하도록 임계값을 설정할 수 있습니다.  
  
### 성능 탐색기에서 프로젝트에 대한 비교 파일 뷰를 만들려면  
  
1.  **보고서**의 **성능 탐색기**에서 비교 시 기준 값으로 사용할 .vsp 또는 .vsps 보고서 파일을 선택합니다.  
  
2.  비교할 .vsp 또는 .vsps 보고서 파일을 선택합니다.  
  
3.  선택한 파일 중 하나를 마우스 오른쪽 단추로 클릭한 다음 **보고서 비교**를 클릭합니다.  
  
### 값을 비교하려면  
  
1.  보고서 뷰 창에서 **비교 보고서** 탭을 선택합니다.  
  
2.  **테이블** 드롭다운 목록에서 비교할 함수나 모듈을 선택합니다.  
  
3.  **열** 드롭다운 목록에서 비교할 값을 선택합니다.  
  
4.  \(선택 사항\) **임계값**으로 사용할 값을 입력합니다.  
  
5.  **적용**을 클릭합니다.  
  
### 보고서 파일을 비교하려면  
  
1.  **분석** 메뉴에서 **성능 보고서 비교**를 선택합니다.  
  
2.  **비교할 분석 파일을 선택합니다.** 창에서 **기본 파일** 분석 파일\(.vsp 또는 .vsps\) 및 **비교 파일**\(.vsp 또는 .vsps\)을 찾아 선택합니다.  
  
3.  **확인**을 클릭합니다.