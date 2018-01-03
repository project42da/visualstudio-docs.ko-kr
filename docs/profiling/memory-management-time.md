---
title: "메모리 관리 시간 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.threads.timeline.paging
helpviewer_keywords: Concurrency Visualizer, Paging Time
ms.assetid: 67af3509-3a7d-435d-bc37-5262448da915
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 08c111b89ee265820d314150ff28096eb9bf5d2e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="memory-management-time"></a>메모리 관리 시간
타임라인의 이러한 세그먼트는 메모리 관리로 분류되는 차단 시간과 관련이 있습니다. 이는 스레드가 페이징 같은 메모리 관리 작업 관련 이벤트에 의해 차단됨을 의미합니다. 이 시간 동안 스레드는 동시성 시각화 도우미가 메모리 관리로 간주되는 API 또는 커널 상태에서 차단되었습니다. 여기에는 페이징 및 메모리 할당과 같은 이벤트가 포함됩니다.  
  
 연관된 호출 스택 및 프로필 보고서를 조사해서 해당 블록이 메모리 관리로 분류되는 기본 이유를 자세히 이해할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [스레드 뷰](../profiling/threads-view-parallel-performance.md)