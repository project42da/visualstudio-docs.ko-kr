---
title: "메모리 및 페이징 성능 규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f37972b2-efe4-4a1c-a5d1-a246ccd76817
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 메모리 및 페이징 성능 규칙
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

메모리 및 페이징 범주의 성능 규칙은 응용 프로그램 성능과 반응성을 저하시킬 수 있는 프로파일링 실행에서 페이징 작업을 식별합니다.  
  
|||  
|-|-|  
|[DA0014: 활성 메모리를 디스크에 페이징하는 비율이 극도로 높습니다.](../Topic/DA0014:%20Extremely%20high%20rates%20of%20paging%20active%20memory%20to%20disk.md)|전체 프로파일링 실행 기간 중 디스크로 페이징되거나 디스크에서 페이징된 활성 메모리의 비율이 매우 높습니다.  이 수준의 페이징 비율은 대개 응용 프로그램 성능과 반응성에 영향을 미칩니다.  알고리즘을 수정하여 메모리 할당량을 줄여 보십시오.  응용 프로그램의 메모리 요구 사항을 고려해야 할 수도 있습니다.  메모리가 더 많은 컴퓨터에서 프로파일링을 다시 실행해 보십시오.  이 규칙은 페이징 작업의 양이 규칙 D0017의 상한 임계값을 초과할 때 적용됩니다.|  
|[DA0017: 디스크에 대한 높은 활성 메모리 페이징 비율](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md)|전체 프로파일링 실행 기간 중 디스크로 페이징되거나 디스크에서 페이징된 활성 메모리의 비율이 비교적 높습니다.  이 수준의 페이징 비율은 대개 응용 프로그램 성능과 반응성에 영향을 미칩니다.  알고리즘을 수정하여 메모리 할당량을 줄여 보십시오.  응용 프로그램의 메모리 요구 사항을 고려해야 할 수도 있습니다.  메모리가 더 많은 컴퓨터에서 프로파일링을 다시 실행해 보십시오.|