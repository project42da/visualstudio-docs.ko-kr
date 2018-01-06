---
title: "JIT 최적화 및 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], optimized code
- optimized code, debugging
ms.assetid: 19bfabf3-1a2e-49dc-8819-a813982e86fd
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2c3dcd57568bdfaac3ba0f7aff33cefca8a0ee32
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="jit-optimization-and-debugging"></a>JIT 최적화 및 디버깅
관리 되는 응용 프로그램을 디버깅할 때 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 기본적으로 타임 (JIT) 코드의 최적화를 표시 하지 않습니다. JIT 최적화를 사용하지 않으면 최적화되지 않은 코드를 디버깅하게 됩니다. 코드가 최적화되지 않으므로 코드 실행 속도는 약간 느려지지만 디버깅은 더 철저하게 수행할 수 있습니다. 최적화된 코드는 디버깅하기가 더 어려우므로 최적화된 코드에서는 발생하지만 최적화되지 않은 버전의 코드에서는 재현되지 않는 버그를 발견한 경우에만 이를 수행하는 것이 좋습니다.  
  
 JIT 최적화 작업은에서 제어 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 여는 **모듈을 로드할 때 JIT 최적화** 옵션입니다. 이 옵션을 찾을 수 있습니다는 **일반** 페이지는 **디버깅** 에서 노드는 **옵션** 대화 상자.  
  
 선택을 취소 하면는 **모듈을 로드할 때 JIT 최적화** 옵션을 최적화 된 JIT 코드를 디버깅할 수 있지만 최적화 된 코드의 소스 코드와 일치 하지 않으므로 디버깅 기능이 제한 될 수 있습니다. 결과적으로, 창과 같은 디버거는 **지역** 및 **자동** 정보가 최적화 되지 않은 코드를 디버깅할 때 많은 창에 표시 되지 않을 수 있습니다.  
  
 또 하나의 중요한 차이점은 내 코드만을 사용한 디버깅과 관련된 것입니다. 내 코드만을 사용하여 디버깅하는 경우 디버거는 최적화된 코드를 사용자가 작성하지 않은 코드로 간주합니다. 이러한 코드는 디버깅하는 동안 표시되지 않습니다. 따라서 JIT 최적화된 코드를 디버깅하는 경우 내 코드만 옵션을 해제해야 할 수도 있습니다. 자세한 내용은 참조 [단계별 실행을 내 코드만으로 제한](../debugger/navigating-through-code-with-the-debugger.md#BKMK_Restrict_stepping_to_Just_My_Code)합니다.  
  
 에 유의 해야는 **모듈을 로드할 때 JIT 최적화** 옵션 모듈을 로드할 때 코드가 최적화 되지 않습니다. 이미 실행 중인 프로세스에 연결하는 경우 이 프로세스에는 이미 로드되어 JIT 컴파일 및 최적화된 코드가 포함되어 있을 수 있습니다. **모듈을 로드할 때 JIT 최적화** 옵션은 이러한 코드에 영향을 주지 않습니다만 연결한 후 로드 한 모듈에 적용 됩니다. 또한는 **모듈을 로드할 때 JIT 최적화** 옵션 WinForms.dll 같은 모듈에, NGEN을 사용 하 여 만든 영향을 주지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Debugging Managed Code](../debugger/debugging-managed-code.md) (관리 코드 디버그)  
 [Navigating through Code with the Debugger](../debugger/navigating-through-code-with-the-debugger.md) (디버거로 코드 탐색)  
 [실행 중인 프로세스에 연결](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [관리되는 실행 프로세스](/dotnet/standard/managed-execution-process)