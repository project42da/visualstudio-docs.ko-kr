---
title: "메모리 및 페이징 성능 규칙 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f37972b2-efe4-4a1c-a5d1-a246ccd76817
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 15b9963d10a2a51d34ef3a426ac7a2aba17c2430
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="memory-and-paging-performance-rules"></a>메모리 및 페이징 성능 규칙
메모리의 성능 규칙 및 페이징 범주는 응용 프로그램 성능과 응답성에 영향을 줄 수 있는 프로파일링 실행의 페이징 작업을 식별합니다.  
  
|||  
|-|-|  
|[DA0014: 활성 메모리를 디스크에 페이징하는 비율이 높습니다.](../profiling/da0014-extremely-high-rates-of-paging-active-memory-to-disk.md)|프로파일링 실행 전체에서 발생된 디스크 간 활성 메모리를 페이징하는 비율이 매우 높습니다. 이 수준의 페이징 비율은 대개 응용 프로그램 성능 및 응답성에 영향을 미칩니다. 알고리즘을 수정하여 메모리 할당을 줄여 보세요. 응용 프로그램의 메모리 요구 사항을 고려해야 할 수도 있습니다. 더 많은 메모리가 있는 컴퓨터에서 프로파일링을 다시 실행하세요. 이 규칙은 페이징 작업의 양이 D0017 규칙의 상한 임계값을 초과할 때 발생합니다.|  
|[DA0017: 활성 메모리를 디스크에 페이징하는 비율이 높습니다.](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md)|프로파일링 실행 전체에서 발생된 디스크 간 활성 메모리를 페이징하는 비율이 비교적 높습니다. 이 수준의 페이징 비율은 대개 응용 프로그램 성능 및 응답성에 영향을 미칩니다. 알고리즘을 수정하여 메모리 할당을 줄여 보세요. 응용 프로그램의 메모리 요구 사항을 고려해야 할 수도 있습니다. 더 많은 메모리가 있는 컴퓨터에서 프로파일링을 다시 실행하세요.|