---
title: "GPU 작업(페이징) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.gpuactivity
- vs.cv.threads.timeline.gpupaging
ms.assetid: 95284ac5-3492-4f7b-a79f-7d2840a07679
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 10a4f9a0c83e18da6fb9f45a2ac4fded913d2723
ms.lasthandoff: 02/22/2017

---
# <a name="gpu-activity-paging"></a>GPU 작업(페이징)
스레드 탭의 **GPU 작업(페이징)** 세그먼트는 GPU가 페이징 요청을 처리한 시간을 나타냅니다.  세그먼트의 길이는 GPU가 DMA(직접 메모리 액세스) 페이징 패킷을 처리한 기간을 나타냅니다. 일반적으로 페이징 패킷은 CPU와 GPU 간의 메모리 전송과 연관됩니다.  
  
 GPU 페이징 세그먼트를 선택하면 **현재** 탭의 보고서에 처리된 DMA 패킷에 대한 정보가 표시됩니다. 여기에는 DirectX 엔진과 연결된 하드웨어 큐에서 대기한 시간, DMA 패킷을 전송한 프로세스, 패킷을 처리하는 데 필요한 시간이 포함됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용률 뷰](../profiling/utilization-view.md)
