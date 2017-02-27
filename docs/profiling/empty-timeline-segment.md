---
title: "빈 시간 표시 막대 세그먼트 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.cv.threads.timeline.empty"
helpviewer_keywords: 
  - "동시성 시각화 도우미, 빈 시간 표시 막대 세그먼트"
ms.assetid: f37b301f-3edc-4e56-8084-feec2dc5a9b1
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# 빈 시간 표시 막대 세그먼트
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

동시성 시각화 도우미에서, 시간 표시 막대의 섹션 \(흰색 배경에\) 이 비어 있는 이유는 채널의 종류에 따라 달라 집니다.  
  
-   CPU 스레드 채널에 대해 타임 라인의 이 부분 동안 스레드가 존재하지 않는 것을 의미합니다.  이 스레드에 대해 관심이 있는 경우, 확대\/축소 컨트롤이나 가로 스크롤 막대를 사용하여 해당 실행 섹션을 찾을 수 있습니다.  
  
-   I\/O 채널에 대해 이 시점에서 대상 프로세스를 대신하여 디스크가 액세스 할 수 없다는 것을 의미합니다.  
  
-   DirectX 채널에 대해, 타임 라인의 이 부분 동안 대상 프로세스 대신 GPU 작업이 수행된 것입니다.  
  
-   마커를 채널에 대해 마커들이 생성되지 않았다는 것을 의미합니다.  
  
## 참고 항목  
 [스레드 뷰](../profiling/threads-view-parallel-performance.md)   
 [확대\/축소 컨트롤\(스레드 뷰\)](../profiling/zoom-control-threads-view.md)