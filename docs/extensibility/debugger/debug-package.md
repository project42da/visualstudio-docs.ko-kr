---
title: 패키지를 디버깅 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], packages
ms.assetid: 99947fd4-fb87-4c69-b26c-65634e17d285
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6ca438b7ed8c9b6a4b84693f975144040f998f01
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="debug-package"></a>패키지를 디버그 합니다.
디버그 패키지가 Visual Studio shell에서 실행 되 고 모든 UI를 처리 합니다. 디버깅 인터페이스는 Visual Studio를 사용 하 고 세션 디버그 관리자 (SDM)와 통신 합니다.  
  
 SDM를 통해 전송 된 중단 이벤트 실행된 모드에서 디버거 체인이 프로그램에 포커스를 변경 하 고 중단 모드를 전환 합니다. 디버그 패키지가 이벤트에 의해 전달 된 정보에서 스택 프레임 및 스레드를 추적 합니다.  
  
 디버그 패키지가 언어 또는 런타임 환경 종속성 없습니다. 구현 하거나 디버그 패키지를 수정할 필요는 없습니다.  
  
 디버그 패키지가 vsdebug.dll에 의해 구현 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [세션 디버그 관리자](../../extensibility/debugger/session-debug-manager.md)   
 [스택 프레임](../../extensibility/debugger/stack-frames.md)   
 [스레드](../../extensibility/debugger/threads.md)   
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)