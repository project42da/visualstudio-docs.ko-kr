---
title: "범위 표식 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.cv.markers.span"
ms.assetid: 736b7765-9c71-44d7-85e5-79787d13d91c
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 범위 표식
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

범위 표식을 응용 프로그램의 의미 있는 단계를 나타냅니다.  예를 들어, 특정 작업 항목 처리 되는 시간 간격을 나타내는 범위를 사용할 수 있습니다.  길이 해당 응용 프로그램의 기간을 나타냅니다.  동시성 시각화 도우미에서이 그림 범위를 보여 줍니다.  
  
 ![동시성 시각화 도우미의 범위 표식](../profiling/media/cvmarkerspan.png "CVMarkerSpan")  
동시성 시각화 도우미의 범위 마커  
  
## 범주를 확장 합니다.  
 범위 마커가 해당 범주에 따라 5 가지 색 중 하나로 표시 됩니다.  색 범주는 5개 종류 이상의 경우에 다시 사용 됩니다.  범주는 임의의 정수 될 수 있습니다.  이 그림 5 색을 보여 줍니다.  
  
 ![다양한 범주의 5가지 범위](../profiling/media/cvmarkerspancategory.png "CVMarkerSpanCategory")  
처음 다섯 개의 범위 범주의 색  
  
## 범위는 집계 표식이  
 플래그는 개별적으로 되지 않는 시각화 도우미에서 다른 하나와 가깝게 발생합니다.  이 경우는 *메시지 집계 마커* 를 나타내는 내부 메시지로 표시합니다.  이러한 아이콘 중 하나에 포인터를 놓으면 도구 설명이 표시 되는 기본 플래그 수를 나타냅니다.  범위를 보려면 확대 하십시오.  기본 표식 범위까지 확대 하 고 진심으는 범위 집합입니다[표식 보고서](../profiling/markers-report.md).  이 그림과 범위 집합입니다.  
  
 ![동시성 시각화 도우미의 집계 범위 마커](../profiling/media/cvmarkerspanaggregate.png "CVMarkerSpanAggregate")  
집계 표식 범위  
  
## 참고 항목  
 [동시성 시각화 도우미 표식](../profiling/concurrency-visualizer-markers.md)   
 [동시성 시각화 도우미 SDK](../profiling/concurrency-visualizer-sdk.md)