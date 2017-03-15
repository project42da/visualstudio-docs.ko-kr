---
title: "패키지를 디버그 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK], 패키지"
ms.assetid: 99947fd4-fb87-4c69-b26c-65634e17d285
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# 패키지를 디버그 합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버그 패키지 Visual Studio 셸에서 실행 되 고 모든 UI 처리 합니다.  Visual Studio 디버깅 인터페이스 사용 하 고 세션 디버그 매니저 \(SDM\)와 통신 합니다.  
  
 SDM을 통해 보낸 이벤트를 나누기 모드 중단 및 중단 발생 위치를 프로그램에 포커스를 변경 하려면 디버거 실행된 모드에서 전환 합니다.  이벤트로 받은 정보에서 스택 프레임 및 스레드 디버그 패키지를 추적 합니다.  
  
 디버그 패키지 언어 또는 런타임 환경에 종속 되지 않습니다 했습니다.  구현 하거나 디버그 패키지를 수정할 필요는 없습니다.  
  
 디버그 패키지는 vsdebug.dll에서 구현 됩니다.  
  
## 참고 항목  
 [디버그 세션 관리자](../../extensibility/debugger/session-debug-manager.md)   
 [스택 프레임](../../extensibility/debugger/stack-frames.md)   
 [스레드](../../extensibility/debugger/threads.md)   
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)