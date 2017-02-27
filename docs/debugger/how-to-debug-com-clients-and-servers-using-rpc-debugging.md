---
title: "방법: RPC 디버깅을 사용하여 COM 클라이언트 및 서버 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.com"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "COM 클라이언트, 디버깅"
  - "COM 서버, 디버깅"
  - "COM, 디버깅"
  - "in-process 원격 프로시저 호출 디버깅"
  - "out-of-process 원격 프로시저 호출 디버깅"
  - "원격 디버깅, RPC(원격 프로시저 호출)"
  - "RPC(원격 프로시저 호출)"
  - "RPC(원격 프로시저 호출), 디버깅"
  - "RPC(원격 프로시저 호출), COM 클라이언트 및 서버 디버깅"
ms.assetid: 3e8526c8-43b5-4b87-8e0d-b22c24f0a3ea
caps.latest.revision: 23
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 23
---
# 방법: RPC 디버깅을 사용하여 COM 클라이언트 및 서버 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

RPC\(원격 프로시저 호출\) 디버깅을 사용하면 COM 클라이언트\/서버 응용 프로그램을 디버깅할 수 있습니다.  RPC 디버깅을 사용하려면 다음과 같은 방법으로 활성화해야 합니다.  RPC 디버깅을 활성화하고 클라이언트에서 서버 호출을 한 단계씩 실행하면 디버거에서 서버에 연결하여 코드를 디버깅할 수 있습니다.  디버거를 연결하면 클라이언트 및 서버 프로세스에서 모든 디버거 기능을 사용할 수 있습니다.  
  
### RPC 디버깅을 활성화하려면  
  
1.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
2.  **옵션** 대화 상자에서 **디버깅** 폴더를 선택합니다.  
  
3.  **네이티브** 페이지를 클릭합니다.  
  
4.  **RPC 디버깅** 확인란을 선택합니다.  
  
    > [!NOTE]
    >  RPC 호출을 디버깅하려면 관리자 또는 고급 사용자 권한이 있어야 합니다.  
  
    > [!NOTE]
    >  Microsoft Windows Vista가 실행되는 원격 서버에서 RPC 단계별 실행을 사용하려면 원격 서버에 네이티브 디버거가 연결되어 있어야 합니다.  그렇지 않으면 RPC 호출이 실패하고 오류 메시지는 표시되지 않습니다.  또는 RPC 호출이 완료되더라도 RPC 호출에 대한 단계별 실행이 작동하지 않습니다.  
  
## 참고 항목  
 [COM 서버 및 컨테이너 디버깅](../debugger/com-server-and-container-debugging.md)   
 [Visual Studio의 디버깅](../debugger/debugging-in-visual-studio.md)