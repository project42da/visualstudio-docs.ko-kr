---
title: "GPU 작업(다른 프로세스) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.cv.threads.timeline.gpuother"
  - "vs.cv.threads.timeline.gpuactivity"
ms.assetid: 8a68df65-eb63-452f-9285-fb4ffc92f2b2
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# GPU 작업(다른 프로세스)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**GPU 동작 \(다른 프로세스\)** 세그먼트에서 동시성 시각화 도우미의 스레드 뷰 GPU가 시스템의 다른 프로세스를 대신 하 여 요청을 처리 하는 경우 시간을 나타냅니다.  이러한 요청은 다이렉트 메모리 엑세스 \(DMA\) 패킷으로 GPU에 보냅니다.  세그먼트의 길이 GPU에서 패킷이 처리 된 시간을 나타냅니다.  
  
 작업 세그먼을 선택할 때, **현재** 탭의 보고서가 DMA 패킷이 처리된 것에 대한 정보를 표시 합니다.  이러한 정보는 패킷 DirectX 엔진과 관련된 하드웨어에서 처리 하는데 필요한 시간, 패킷을 전송한 프로세스, 그리고 패킷을 프로세스 하는데 필요한 시간을 포함합니다.