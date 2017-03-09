---
title: "JIT 최적화 및 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "디버깅[Visual Studio], 최적화된 코드"
  - "최적화된 코드, 디버깅"
ms.assetid: 19bfabf3-1a2e-49dc-8819-a813982e86fd
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# JIT 최적화 및 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

관리되는 응용 프로그램을 디버깅할 때 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 기본적으로 JIT\(Just\-In\-Time\) 코드 최적화를 사용하지 않습니다.  JIT 최적화를 사용하지 않으면 최적화되지 않은 코드를 디버깅하게 됩니다.  코드가 최적화되지 않으므로 코드 실행 속도는 약간 느려지지만 디버깅은 더 철저하게 수행할 수 있습니다.  최적화된 코드는 디버깅하기가 더 어려우므로 최적화된 코드에서는 발생하지만 최적화되지 않은 버전의 코드에서는 재현되지 않는 버그를 발견한 경우에만 이를 수행하는 것이 좋습니다.  
  
 JIT 최적화는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 **모듈을 로드할 때 JIT 최적화 기능 사용 안 함** 옵션으로 제어합니다.  이 옵션은 **옵션** 대화 상자의 **디버깅** 노드 아래에 있는 **일반** 페이지에 있습니다.  
  
 **모듈을 로드할 때 JIT 최적화 기능 사용 안 함** 옵션을 해제하면 최적화된 JIT 코드를 디버깅할 수 있지만 최적화된 코드와 소스 코드 사이의 불일치로 인해 디버깅 기능이 제한될 수도 있습니다.  따라서 **지역** 및 **자동** 창과 같은 디버거 창에 표시되는 정보가 최적화되지 않은 코드를 디버깅할 때보다 적을 수 있습니다.  
  
 또 하나의 중요한 차이점은 내 코드만을 사용한 디버깅과 관련된 것입니다.  내 코드만을 사용하여 디버깅하는 경우 디버거는 최적화된 코드를 사용자가 작성하지 않은 코드로 간주합니다. 이러한 코드는 디버깅하는 동안 표시되지 않습니다.  따라서 JIT 최적화된 코드를 디버깅하는 경우 내 코드만 옵션을 해제해야 할 수도 있습니다.  자세한 내용은 [단계별 코드 실행을 내 코드만으로 제한](../debugger/navigating-through-code-with-the-debugger.md#BKMK_Restrict_stepping_to_Just_My_Code)을 참조하십시오.  
  
 **모듈을 로드할 때 JIT 최적화 기능 사용 안 함** 옵션을 설정하면 모듈을 로드할 때 코드가 최적화되지 않는다는 사실을 기억할 필요가 있습니다.  이미 실행 중인 프로세스에 연결하는 경우 이 프로세스에는 이미 로드되어 JIT 컴파일 및 최적화된 코드가 포함되어 있을 수 있습니다.  **모듈을 로드할 때 JIT 최적화 기능 사용 안 함** 옵션은 이러한 코드에 적용되지 않으며 프로세스에 연결한 후에 로드한 모듈에만 적용됩니다.  또한 **모듈을 로드할 때 JIT 최적화 기능 사용 안 함** 옵션은 NGEN을 사용하여 만든 WinForms.dll 같은 모듈에 영향을 주지 않습니다.  
  
## 참고 항목  
 [관리 코드 디버깅](../debugger/debugging-managed-code.md)   
 [디버거로 코드 탐색](../debugger/navigating-through-code-with-the-debugger.md)   
 [실행 중인 프로세스에 연결](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [관리되는 실행 프로세스](../Topic/Managed%20Execution%20Process.md)