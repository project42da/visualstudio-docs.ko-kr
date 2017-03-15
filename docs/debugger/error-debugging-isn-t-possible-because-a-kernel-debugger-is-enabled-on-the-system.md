---
title: "오류: 시스템에 커널 디버거가 사용 중이므로 디버깅을 할 수 없습니다. | Microsoft Docs"
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
  - "vs.debug.error.kernel_dbg_enabled"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "커널 디버거"
ms.assetid: 630a7abd-3303-4aaa-888a-6de3de14bc01
caps.latest.revision: 23
caps.handback.revision: 23
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 오류: 시스템에 커널 디버거가 사용 중이므로 디버깅을 할 수 없습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

관리 코드를 디버깅할 때 다음 오류 메시지가 나타날 수 있습니다.  
  
```  
Debugging isn't possible because a kernel debugger is enabled on the system  
```  
  
 이 메시지는 다음과 같은 경우에 관리 코드를 디버깅하려고 하면 발생합니다.  
  
-   디버그 모드에서 시작된 [!INCLUDE[win7](../debugger/includes/win7_md.md)] 또는 [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)] 시스템에서 디버깅하는 경우  
  
-   응용 프로그램에서 CLR 버전 CLR 2.0, 3.0 또는 3.5를 사용하는 경우  
  
## 해결책  
  
#### 이 문제를 해결하려면  
  
-   CLR 버전 4.0 또는 4.5를 사용하도록 응용 프로그램을 업그레이드합니다.  
  
     —또는—  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 커널 디버깅을 비활성화하고 디버깅합니다.  
  
     —또는—  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 대신 커널 디버거를 사용하여 디버깅합니다.  
  
     —또는—  
  
-   커널 디버거에서 사용자 모드 예외를 비활성화합니다.  
  
#### 현재 세션에서 커널 디버깅을 비활성화하려면  
  
-   명령 프롬프트에 다음과 같이 입력합니다.  
  
    ```  
    Kdbgctrl.exe -d  
    ```  
  
#### 모든 세션에 대해 커널 디버깅을 비활성화하려면\(Windows Vista 및 Windows 7\)  
  
1.  명령 프롬프트에 다음과 같이 입력합니다.  
  
    ```  
    bcdedit /debug off   
    ```  
  
2.  컴퓨터를 다시 시작합니다.  
  
#### 모든 세션에 대해 커널 디버깅을 비활성화하려면\(기타 Windows 운영 체제\)  
  
1.  시스템 드라이브\(일반적으로 C:\\\)에서 boot.ini를 찾습니다.  boot.ini 파일은 숨겨져 있고 읽기 전용일 수 있습니다.  따라서 이 파일을 보려면 다음 명령을 사용해야 합니다.  
  
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
  
#### 커널 디버거를 사용하여 디버깅하려면  
  
1.  커널 디버거가 후크되어 있으면 디버깅을 계속할지 묻는 메시지가 나타납니다.  단추를 클릭하여 디버깅을 계속합니다.  
  
2.  `User break exception(Int 3)`이 발생할 수도 있습니다. 이 경우 디버깅을 계속하려면 다음과 같은 커널 디버거 명령을 입력합니다.  
  
     `gn`  
  
## 참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [관리 코드 디버깅](../debugger/debugging-managed-code.md)