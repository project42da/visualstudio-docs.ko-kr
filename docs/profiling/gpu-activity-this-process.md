---
title: "GPU 작업(이 프로세스) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.cv.threads.timeline.gpuexecution"
  - "vs.cv.threads.timeline.gpuactivity"
ms.assetid: 0956edbf-9bcd-4afe-9287-fda628648ca0
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# GPU 작업(이 프로세스)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

GPU가 현재 프로세스를 대신하여 요청을 처리하는 경우, 동시성 시각화 도우미의 스레드 뷰에서  **GPU 작업 \(이 프로세스\)** 세그먼트 시간을 나타냅니다.  이러한 요청은 다이렉트 메모리 엑세스 \(DMA\) 패킷으로 GPU에 보내집니다.  세그먼트 길이는 GPU가 현재 프로세스를 대신하여 DMA 패킷이 처리 된 시간을 나타냅니다.  
  
 GPU 작업 세그먼을 선택할떄, **현재** 탭의 보고서가 DMA 패킷이 처리된 것에 대한 정보를 표시 합니다.  이 정보는 패킷 DirectX 엔진과 관련된 하드웨어에서 처리 하는데 필요한 시간, 패킷을 전송한 프로세스, 그리고 패킷을 프로세스 하는데 필요한 시간을 포함합니다.  현재 프로세스가 아닌 프로세스는 DMA 패킷을 GPU에 실제로 제출했을 수 있습니다.  동시성 시각화 도우미는 다른 프로세스가 현재 프로세스 대신 GPU로 작업을 제출할 때 검색할 수 있습니다.