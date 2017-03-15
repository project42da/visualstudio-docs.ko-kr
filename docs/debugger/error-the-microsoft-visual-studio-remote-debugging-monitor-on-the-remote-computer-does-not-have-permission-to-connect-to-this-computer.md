---
title: "오류: 원격 컴퓨터의 Microsoft Visual Studio 원격 디버깅 모니터가 이 컴퓨터에 연결할 수 있는 권한이 없습니다. | Microsoft Docs"
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
  - "vs.debug.error.access_denied_oncallback"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "원격 디버깅, Windows 버전 오류"
ms.assetid: ba08a59b-6dbc-4bbc-9c52-379d3bf5241f
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 오류: 원격 컴퓨터의 Microsoft Visual Studio 원격 디버깅 모니터가 이 컴퓨터에 연결할 수 있는 권한이 없습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 오류는 로컬 컴퓨터에 계정이 없는 사용자가 Visual Studio 원격 디버깅 모니터\(msvsmon\)를 실행하려고 할 때 발생합니다.  
  
### 이 문제를 해결하려면  
  
-   원격 컴퓨터에서 msvsmon을 실행하는 사용자 계정과 이름 및 암호가 같은 사용자 계정을 Visual Studio 디버거 호스트 컴퓨터에 추가합니다.  
  
     \- 또는 \-  
  
-   로컬 컴퓨터에 대한 호출 권한이 있는 사용자로 msvsmon을 실행합니다.  즉, 이 사용자는 msvsmon 컴퓨터의 관리자이자 도메인 사용자여야 합니다.  msvsmon을 실행하기 위한 사용자 계정은 다음 두 가지 방법 중 하나로 지정할 수 있습니다.  
  
    -   msvsmon 아이콘을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **다음 계정으로 실행**을 선택합니다.  
  
     \- 또는 \-  
  
    -   명령 프롬프트에서 `runas.exe`를 실행합니다.  
  
## 참고 항목  
 [도메인 사이의 원격 디버깅](../Topic/Remote%20Debugging%20Across%20Domains.md)   
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [원격 디버깅](../debugger/remote-debugging.md)