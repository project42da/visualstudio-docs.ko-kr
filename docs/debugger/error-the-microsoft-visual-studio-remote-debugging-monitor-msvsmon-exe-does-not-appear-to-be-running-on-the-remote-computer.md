---
title: "오류: Microsoft Visual Studio 원격 디버깅 모니터(MSVSMON.EXE)가 원격 컴퓨터에서 실행 중인 것 같지 않습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.error.server_machine_no_default"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 86db9931-50e3-4095-b161-802ed8ef39c9
caps.latest.revision: 21
caps.handback.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 오류: Microsoft Visual Studio 원격 디버깅 모니터(MSVSMON.EXE)가 원격 컴퓨터에서 실행 중인 것 같지 않습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 오류 메시지는 Visual Studio가 원격 컴퓨터에서 Visual Studio 원격 디버깅 모니터의 올바른 인스턴스를 찾을 수 없음을 의미합니다. 원격으로 디버깅을 수행하려면 Visual Studio 원격 디버깅 모니터를 설치해야 합니다. 원격 디버거를 다운로드하고 설정하는 방법에 대한 자세한 내용은 [장치에서 원격 도구 설정](../Topic/Set%20Up%20the%20Remote%20Tools%20on%20the%20Device.md)을 참조하세요.  
  
> [!IMPORTANT]
>  제품 버그 때문에 이 메시지가 수신되었다고 생각하는 경우 이 문제를 Visual Studio [웃는 얼굴 보내기](../Topic/Visual%20Studio%20Send%20a%20Smile%20Instructions.md)로 알려주세요. 자세한 도움말이 필요한 경우 [의견 보내기](../ide/talk-to-us.md)에서 Microsoft에 문의하는 방법을 참조하세요.  
  
## Visual Studio 2010 이전 버전에서 디버그하는 동안 이 메시지가 수신됨  
 Visual Studio 2010 이전 버전의 Visual Studio를 사용 중이면 파일 및 프린터 공유를 사용하도록 설정하지 않은 경우에도 이 오류가 발생할 수 있습니다. 이 문제에 대해 자세히 알아보려면 이 설명서의 Visual Studio 2010 버전을 참조하세요. [오류: Microsoft Visual Studio 원격 디버깅 모니터\(MSVSMON.EXE\)가 원격 컴퓨터에서 실행 중인 것 같지 않습니다. \- Visual Studio 2010](https://msdn.microsoft.com/en-us/library/ms164726\(v=vs.100\).aspx)  
  
## 로컬로 디버그하는 동안 이 메시지가 수신됨  
 로컬로 디버그하는 동안 이 메시지가 수신된 경우 바이러스 백신 소프트웨어 또는 타사 방화벽 때문일 수 있습니다. Visual Studio는 32비트 응용 프로그램이므로 64비트 버전의 원격 디버거를 사용하여 64비트 응용 프로그램을 디버그합니다. 두 프로세스는 로컬 컴퓨터 내의 로컬 네트워크를 사용하여 통신합니다. 컴퓨터에서 나가는 트래픽이 없지만 타사 보안 소프트웨어가 통신을 차단할 수 있습니다.  
  
 다음 섹션에서는 이 메시지가 수신되는 몇 가지 다른 이유 및 문제를 해결하기 위해 수행할 수 있는 작업을 보여 줍니다.  
  
## 원격 컴퓨터에 연결할 수 없음  
 원격 컴퓨터를 [ping](https://technet.microsoft.com/en-us/library/ee624059\(v=ws.10\).aspx)하려고 합니다. Ping에 응답하지 않으면 원격 도구도 연결할 수 없습니다. 원격 컴퓨터를 다시 부팅하거나 네트워크에서 올바르게 구성되었는지 확인합니다.  
  
## 원격 디버거 버전이 Visual Studio 버전과 일치하지 않음  
 로컬로 실행하는 Visual Studio 버전이 원격 컴퓨터에서 실행되는 원격 디버깅 모니터 버전과 일치해야 합니다. 이 문제를 해결하려면 일치하는 버전의 원격 디버깅 모니터를 다운로드하여 설치합니다.[다운로드 센터](http://www.microsoft.com/en-us/download)로 이동하여 올바른 버전의 원격 디버거를 찾습니다.  
  
## 로컬 및 원격 컴퓨터의 인증 모드가 서로 다름  
 로컬 및 원격 컴퓨터에서 동일한 인증 모드를 사용해야 합니다. 이 문제를 해결하려면 두 컴퓨터에서 모두 동일한 인증 모드를 사용 중인지 확인합니다. 인증 모드에 대한 자세한 내용은 [Windows 인증 개요](https://technet.microsoft.com/en-us/library/hh831472.aspx)를 참조하세요.  
  
## 원격 디버거가 다른 사용자 계정으로 실행되고 있음  
 다음 방법 중 하나를 사용하여 이 문제를 해결할 수 있습니다.  
  
-   원격 디버거를 중지하고 로컬 컴퓨터에서 사용 중인 계정으로 다시 시작할 수 있습니다.  
  
-   **\/allow \<username\>** 매개 변수를 사용하여 명령줄에서 원격 디버거를 시작할 수 있습니다. `msvsmon /allow <username@computer>`  
  
-   원격 디버거의 사용 권한에 사용자를 추가할 수 있습니다\(원격 디버거 창, **도구 \/ 사용 권한**\).  
  
-   이전 단계에서 메서드를 사용할 수 없는 경우 모든 사용자가 원격 디버깅을 수행하도록 허용할 수 있습니다. 원격 디버거 창에서 **도구 \/ 옵션** 대화 상자로 이동합니다.**인증 안 함**을 선택하는 경우 **모든 사용자가 디버깅할 수 있도록 허용**을 선택할 수 있습니다. 그러나 선택 항목이 없거나 개인 네트워크에 있는 경우에만 이 옵션을 사용해야 합니다.  
  
## 원격 컴퓨터의 방화벽이 원격 디버거로 들어오는 연결을 허용하지 않습니다.  
 Visual Studio와 원격 디버거 간의 통신을 허용하도록 Visual Studio 컴퓨터의 방화벽 및 원격 컴퓨터의 방화벽을 구성해야 합니다. 원격 디버거에서 사용 중인 포트에 대한 자세한 내용은 [원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md)을 참조하세요. Windows 방화벽을 구성하는 방법에 대한 자세한 내용은 [원격 디버깅을 위해 Windows 방화벽 구성](../debugger/configure-the-windows-firewall-for-remote-debugging.md)을 참조하세요.  
  
## 바이러스 백신 소프트웨어가 연결을 차단함  
 Windows 바이러스 백신 소프트웨어는 원격 디버거 연결을 허용하지만 일부 타사 바이러스 백신 소프트웨어가 차단할 수도 있습니다. 이러한 연결을 허용하는 방법을 알아보려면 해당 바이러스 백신 소프트웨어에 대한 설명서를 확인합니다.  
  
## 네트워크 보안 정책에서 원격 컴퓨터와 Visual Studio 간의 통신을 차단함  
 네트워크 보안을 검토하여 통신을 차단하지 않는지 확인합니다. Windows 네트워크 보안 정책에 대한 자세한 내용은 [보안 관리](https://msdn.microsoft.com/en-us/library/windows/desktop/ms721855\(v=vs.85\).aspx)를 참조하세요.  
  
## 네트워크 사용량이 너무 많아 원격 디버깅을 지원할 수 없음  
 다른 시간에 원격 디버깅을 수행하거나 다른 시간에 네트워크 작업을 다시 예약해야 할 수도 있습니다.  
  
## 자세한 도움말  
 명령줄 스위치를 포함하여 원격 디버거에 대한 자세한 도움말을 보려면 브라우저에서 다음을 엽니다.  
  
 **res:\/\/C:\\Program%20Files\\Microsoft%20Visual%20Studio%2014.0\\Common7\\IDE\\Remote%20Debugger\\x64\\msvsmon.exe\/help.htm**  
  
## 참고 항목  
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)