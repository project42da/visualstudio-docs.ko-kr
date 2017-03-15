---
title: "Visual Studio에서 다중 스레드 응용 프로그램 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.gputthreads"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "디버깅[Visual Studio], 고성능 계산"
  - "디버깅[Visual Studio], 다중 스레드"
  - "고성능 디버깅"
  - "다중 스레드 디버깅"
  - "스레딩[Visual Studio], 디버깅"
ms.assetid: 9d175bc2-1d95-4c47-9bc3-9755af968a9c
caps.latest.revision: 25
caps.handback.revision: 25
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Visual Studio에서 다중 스레드 응용 프로그램 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

스레드는 운영 체제에서 프로세서 시간을 할당받는 명령 시퀀스입니다.  운영 체제에서 실행되는 모든 프로세스는 최소한 하나의 스레드로 구성됩니다.  프로세스에 스레드가 둘 이상인 경우를 다중 스레드라고 합니다.  
  
 다중 프로세서, 다중 코어 프로세서 또는 하이퍼스레드 프로세스를 갖춘 컴퓨터는 여러 스레드를 동시에 실행할 수 있습니다.  여러 스레드를 병렬 처리하면 프로그램 성능이 크게 향상되지만, 여러 스레드를 추적해야 하므로 디버깅이 어려워질 수도 있습니다.  
  
 또한 다중 스레드로 인해 새로운 종류의 버그가 생길 수 있습니다.  예를 들어 둘 이상의 스레드에서 같은 리소스에 액세스해야 하지만 한 번에 스레드 중 하나만 리소스에 안전하게 액세스할 수 있는 경우가 많습니다.  한 번에 한 스레드만 리소스에 액세스할 수 있게 하려면 특정한 형태의 상호 제외가 필요합니다.  상호 제외가 잘못 수행되면 어떠한 스레드도 실행될 수 없는 *교착 상태* 조건이 발생할 수 있습니다.  교착 상태 문제는 특히 디버깅하기 어려울 수 있습니다.  
  
 Visual Studio에는 **스레드** 창, GPU 스레드 창, 병렬 조사식 창 및 다중 스레드 디버깅을 보다 쉽게 만들어 주는 기타 기능을 제공합니다. 스레딩 기능을 배우는 가장 좋은 방법은 연습을 수행하는 것입니다.  [연습: 다중 스레드 응용 프로그램 디버깅](../debugger/walkthrough-debugging-a-multithreaded-application.md) 및 [연습: C\+\+ AMP 응용 프로그램 디버깅](../Topic/Walkthrough:%20Debugging%20a%20C++%20AMP%20Application.md)을 참조하세요.  
  
 Visual Studio에서 제공하는 강력한 중단점 및 추적점은 다중 스레드 응용 프로그램을 디버깅할 때 매우 유용할 수 있습니다.  중단점 필터를 사용하면 개별 스레드에 중단점을 배치할 수 있습니다.  [중단점 사용](../debugger/using-breakpoints.md)을 참조하세요.  
  
 사용자 인터페이스가 있는 다중 스레드 응용 프로그램은 특히 디버깅하기 어려울 수 있습니다.  이러한 경우 응용 프로그램을 다른 컴퓨터에서 실행하면서 원격 디버깅을 사용하는 것이 좋습니다.  자세한 내용은 [원격 디버깅](../debugger/remote-debugging.md)를 참조하세요.  
  
## 단원 내용  
 [스레드 및 프로세스 디버깅](../debugger/debug-threads-and-processes.md)  
 스레드 및 프로세스 디버깅의 기본 사항에 대해 설명합니다.  
  
 [프로세스 디버깅](../debugger/debug-multiple-processes.md)  
 여러 프로세스 디버깅 방법에 대해 설명합니다.  
  
 [방법: 스레드 창 사용](../debugger/how-to-use-the-threads-window.md)  
 **스레드** 창을 사용하여 스레드를 디버깅하는 유용한 절차를 보여 줍니다.  
  
 [방법: 디버깅 중 다른 스레드로 전환](../debugger/how-to-switch-to-another-thread-while-debugging.md)  
 디버깅 컨텍스트를 다른 스레드로 전환하는 세 가지 방법을 보여 줍니다.  
  
 [방법: 스레드에 플래그 지정 및 스레드의 플래그 해제](../debugger/how-to-flag-and-unflag-threads.md)  
 디버깅 도중 특별히 주의하려는 스레드를 표시하거나 플래그를 지정합니다.  
  
 [방법: 네이티브 코드에 스레드 이름 설정](../debugger/how-to-set-a-thread-name-in-native-code.md)  
 **스레드** 창에 표시되는 스레드에 이름을 지정합니다.  
  
 [방법: 관리 코드에 스레드 이름 설정](../debugger/how-to-set-a-thread-name-in-managed-code.md)  
 **스레드** 창에 표시되는 스레드에 이름을 지정합니다.  
  
 [연습: 다중 스레드 응용 프로그램 디버깅](../debugger/walkthrough-debugging-a-multithreaded-application.md)  
 다양한 스레드 디버깅 기능을 안내하고, [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)]에서 기능을 사용하는 방법에 중점을 둡니다.  
  
 [방법: 고성능 클러스터에서 디버깅](../debugger/how-to-debug-on-a-high-performance-cluster.md)  
 고성능 클러스터에서 실행되는 응용 프로그램을 디버깅하는 방법을 보여 줍니다.  
  
 [네이티브 코드의 스레드 디버깅 팁](../debugger/tips-for-debugging-threads-in-native-code.md)  
 네이티브 스레드를 디버깅하는 단순하지만 유용한 방법을 보여 줍니다.  
  
 [작업 창 사용](../debugger/using-the-tasks-window.md)  
 관리 또는 네이티브 작업 개체의 상태 및 다른 유용한 정보를 포함한 모든 목록을 보여 줍니다.  
  
 [병렬 스택 창 사용](../debugger/using-the-parallel-stacks-window.md)  
 단일 뷰에서 다중 스레드 또는 작업의 스택 호출을 보여 주고 스레드 또는 작업 사이의 공통 스택 세그먼트를 병합하기도 합니다.  
  
 [연습: 병렬 응용 프로그램 디버깅](../debugger/walkthrough-debugging-a-parallel-application.md)  
 병렬 작업 및 병렬 스택 창을 사용하는 방법을 보여 주는 연습입니다.  
  
 [방법: 병렬 조사식 창 사용](../debugger/how-to-use-the-parallel-watch-window.md)  
 여러 스레드에서 값과 식을 검사하는 방법을 보여 줍니다.  
  
 [방법: GPU 스레드 창 사용](../debugger/how-to-use-the-gpu-threads-window.md)  
 디버깅 중 GPU에서 실행되는 스레드를 검사하고 작업하는 방법을 보여 줍니다.  
  
## 관련 단원  
 [중단점 사용](../debugger/using-breakpoints.md)  
 -   개별 스레드에 중단점을 배치하려는 경우 중단점 필터를 사용하는 방법을 보여 줍니다.  
  
-   추적점을 통해 프로그램 실행을 중단 없이 추적할 수 있습니다.  이 기능은 교착 상태와 같은 문제를 파악할 때 유용합니다.  
  
 [Threading](../Topic/Managed%20Threading.md)  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 프로그래밍의 스레드 개념에 대해 설명하며, 예제 코드가 포함되어 있습니다.  
  
 [구성 요소에서 다중 스레딩](../Topic/Multithreading%20in%20Components.md)  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 구성 요소에서 다중 스레드를 사용하는 방법에 대해 설명합니다.  
  
 [이전 코드를 위한 다중 스레드 지원\(Visual C\+\+\)](/visual-cpp/parallel/multithreading/multithreading-support-for-older-code-visual-cpp)  
 MFC를 사용하는 C\+\+ 프로그래머를 위한 스레드 개념 및 예제 코드가 들어 있습니다.  
  
## 참고 항목  
 [스레드 및 프로세스 디버깅](../debugger/debug-threads-and-processes.md)   
 [원격 디버깅](../debugger/remote-debugging.md)