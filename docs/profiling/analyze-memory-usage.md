---
title: Visual Studio에서 메모리 사용 분석 | Microsoft Docs
ms.custom: ''
ms.date: 01/02/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 20c483b40cf1cc45b730ea67bf01ea452c42af1e
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="analyze-memory-usage"></a>메모리 사용량 분석
디버거 통합 **메모리 사용량** 진단 도구를 사용하여 메모리 누수 및 비효율적인 메모리를 찾습니다. 메모리 사용량 도구를 통해 관리되는 메모리 및 네이티브 메모리 힙의 *스냅숏* 을 하나 이상 만들 수 있습니다. .NET, 네이티브 또는 혼합 모드(.NET 및 네이티브) 앱의 스냅숏을 수집할 수 있습니다.  
  
-   단일 스냅숏을 분석하여 메모리 사용에 대한 개체 형식의 상대적 영향을 파악하고 앱에서 메모리를 비효율적으로 사용하는 코드를 찾을 수 있습니다.  
  
-   또한 앱의 스냅숏 두 개를 비교(diff)하여 코드에서 시간에 따라 메모리 사용이 늘어나는 영역을 찾을 수 있습니다.  

자세한 내용은 [메모리 사용 분석](../profiling/memory-usage.md) 자습서를 참조하세요. 디버거를 연결하지 않고 메모리 사용량을 분석하려면 [디버거 없이 메모리 사용](memory-usage-without-debugging2.md)을 참조하세요.
  
## <a name="blogs-and-videos"></a>블로그 및 동영상  

|         |         |
|---------|---------|
|  ![비디오에 대한 비디오 카메라 아이콘](../install/media/video-icon.png "비디오 보기")  |    Visual Studio 2017의 메모리 사용량 및 CPU 사용량 분석 방법을 보여 주는 진단 도구 사용에 대한 [비디오를 시청](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Profiling-with-Diagnostics-Tools-in-Visual-Studio-2017-daHnzMD6D_9211787171)합니다. |

 [디버그하는 동안 CPU와 메모리 분석](https://blogs.msdn.microsoft.com/visualstudio/2016/02/15/analyze-cpu-memory-while-debugging/)  
  
 [Visual C++ 블로그: Visual C++ 2015의 메모리 프로파일링](https://blogs.msdn.microsoft.com/vcblog/2015/10/21/memory-profiling-in-visual-c-2015/)  

## <a name="see-also"></a>참고 항목
 [Visual Studio의 프로파일링](../profiling/index.md)  
 [프로파일링 기능 둘러보기](../profiling/profiling-feature-tour.md)