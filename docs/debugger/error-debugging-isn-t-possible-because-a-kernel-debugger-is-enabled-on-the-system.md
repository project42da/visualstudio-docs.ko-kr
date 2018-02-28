---
title: "큰 &#39; 오류: 디버깅 가능한 때문에 커널 디버거가 t는 시스템에서 활성화 되어 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.error.kernel_dbg_enabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- kernel debugger
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0841b6e6d592a8b09b85e744d693f0b356fcbf9d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="error-debugging-isn39t-possible-because-a-kernel-debugger-is-enabled-on-the-system"></a>큰 &#39; 오류: 디버깅 가능한 때문에 커널 디버거가 t는 시스템에서 활성화 되어
관리 코드를 디버깅할 때 다음 오류 메시지가 나타날 수 있습니다.  
  
```  
Debugging isn't possible because a kernel debugger is enabled on the system  
```  
  
 이 메시지는 다음과 같은 경우에 관리 코드를 디버깅하려고 하면 발생합니다.  
  
-   디버그 모드에서 시작된 [!INCLUDE[win7](../debugger/includes/win7_md.md)] 또는 [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)] 시스템에서 디버깅하는 경우  
  
-   응용 프로그램에서 CLR 버전 CLR 2.0, 3.0 또는 3.5를 사용하는 경우  
  
## <a name="solution"></a>솔루션  
  
#### <a name="to-fix-this-problem"></a>이 문제를 해결하려면  
  
-   CLR 버전 4.0 또는 4.5를 사용하도록 응용 프로그램을 업그레이드합니다.  
  
     또는  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 커널 디버깅을 비활성화하고 디버깅합니다.  
  
     또는  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 대신 커널 디버거를 사용하여 디버깅합니다.  
  
     또는  
  
-   커널 디버거에서 사용자 모드 예외를 비활성화합니다.  
  
#### <a name="to-disable-kernel-debugging-in-the-current-session"></a>현재 세션에서 커널 디버깅을 비활성화하려면  
  
-   명령 프롬프트에 다음과 같이 입력합니다.  
  
    ```  
    Kdbgctrl.exe -d  
    ```  
  
#### <a name="to-disable-kernel-debugging-for-all-sessions-windows-vista-and-windows-7"></a>모든 세션에 대해 커널 디버깅을 비활성화하려면(Windows Vista 및 Windows 7)  
  
1.  명령 프롬프트에서 다음을 입력합니다.  
  
    ```  
    bcdedit /debug off   
    ```  
  
2.  컴퓨터를 다시 시작합니다.  
  
#### <a name="to-disable-kernel-debugging-for-all-sessions-other-windows-operating-systems"></a>모든 세션에 대해 커널 디버깅을 비활성화하려면(기타 Windows 운영 체제)  
  
1.  시스템 드라이브에서 boot.ini를 찾습니다 (일반적으로 c:\\). boot.ini 파일은 숨겨져 있고 읽기 전용일 수 있습니다. 따라서 이 파일을 보려면 다음 명령을 사용해야 합니다.  
  
    ```  
    dir /ASH  
    ```  
  
2.  메모장을 사용하여 boot.ini를 열고 다음 옵션을 제거합니다.  
  
    ```  
    /debug  
    /debugport  
    /baudrate  
    ```  
  
3.  컴퓨터를 다시 시작합니다.  
  
#### <a name="to-debug-with-the-kernel-debugger"></a>커널 디버거를 사용하여 디버깅하려면  
  
1.  커널 디버거가 후크되어 있으면 디버깅을 계속할지 묻는 메시지가 나타납니다. 단추를 클릭하여 디버깅을 계속합니다.  
  
2.  표시 될 수 있습니다는 `User break exception(Int 3).` 디버깅을 계속 하려면 다음 커널 디버거 명령을 입력 하는이 문제가 발생 합니다.  
  
     `gn`  
  
## <a name="see-also"></a>참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [관리 코드 디버그](../debugger/debugging-managed-code.md)