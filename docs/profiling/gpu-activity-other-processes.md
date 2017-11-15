---
title: "GPU 작업(다른 프로세스) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.gpuother
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 8a68df65-eb63-452f-9285-fb4ffc92f2b2
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3b32ee2967ccc4a7cf1f02935a58cfff5c9e8a33
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="gpu-activity-other-processes"></a>GPU 작업(다른 프로세스)
동시성 시각화 도우미의 스레드 뷰에 있는 **GPU 작업(다른 프로세스)** 세그먼트는 시스템의 다른 프로세스를 대신해서 GPU가 요청을 처리 중인 시간을 나타냅니다. 이러한 요청은 DMA(직접 메모리 액세스) 패킷으로 GPU에 전송됩니다.  세그먼트 길이는 GPU에서 패킷이 처리된 시간을 나타냅니다.  
  
 이 종류의 세그먼트를 선택하면 **현재** 탭의 보고서에 처리된 패킷에 대한 정보가 표시됩니다.  이 정보에는 DirectX 엔진과 연관된 하드웨어 큐에서 패킷이 대기하는 데 걸린 시간, 패킷을 전송한 프로세스, 패킷을 처리하는 데 필요한 시간이 포함됩니다.