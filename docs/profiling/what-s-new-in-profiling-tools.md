---
title: "프로파일링의 새로운 기능 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling
- what's new
ms.assetid: d4736cc8-8961-4089-be9e-d5190ce8353c
caps.latest.revision: 42
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 669bc5894727c207691a7e37937f432d98fee8b1
ms.openlocfilehash: 0b1d5d3c39e2f52952397413d47229034bbb4adb
ms.contentlocale: ko-kr
ms.lasthandoff: 06/30/2017

---
# <a name="whats-new-in-profiling-tools-in-includevsdev15miscincludesvsdev15mdmd"></a>[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]에 포함된 프로파일링 도구의 새로운 기능
진단 도구에는 수정해야 하는 앱의 문제를 식별하는 데 사용할 수 있는 새로운 시각화가 포함되어 있습니다. 이제는 진단 도구에 ASP.NET 앱 지원이 포함됩니다.

자세한 내용은 [[!include[vs_dev15](../misc/includes/vs_dev15_md.md)] 릴리스 정보](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes#debuggingdiag)를 참조하세요.

성능 분석을 위한 주요 영역을 중점적으로 확인할 수 있는 **요약** 탭이 도구에 추가되었습니다. 이 탭에서는 발생한 이벤트의 수를 확인하고, 힙의 스냅샷을 생성하고, CPU 사용량 데이터 수집을 빠르게 활성화할 수 있습니다. 이 뷰에는 모든 [Application Insights](https://azure.microsoft.com/en-us/documentation/articles/app-insights-visual-studio/) 또는 [UI 분석](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes#UIAnalysis) 이벤트가 표시됩니다. 또한 Visual Studio Enterprise의 경우 이 뷰에는 IntelliTrace 이벤트도 표시됩니다.

![진단 도구 요약 탭](../profiling/media/DiagToolsSummaryTab-2.png "DiagToolsSummaryTab")

CPU 사용량 도구에는 성능 문제를 발생시킬 가능성이 가장 높은 기능을 식별하는 데 사용할 수 있는 [새로운 시각화](../profiling/Beginners-Guide-to-Performance-Profiling.md)가 포함되어 있습니다. 새로운 **호출자/호출 수신자** 뷰에서는 선택한 함수와의 함수 호출 비용을 조사할 수 있습니다.

![진단 도구 호출자/호출 수신자 뷰](../profiling/media/DiagToolsCallerCallee.png "DiagToolsCallerCallee")
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio의 프로파일링](../profiling/index.md) [프로파일링 기능 둘러보기](../profiling/profiling-feature-tour.md)
