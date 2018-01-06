---
title: "종료 및 분리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- programs, termination events
- debug engines, detaching from programs
ms.assetid: 268c1e51-6363-45d1-964c-1ab99bdfa4f9
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 091f26b43d5775499a5856f783d7b20249382e6d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="termination-and-detaching"></a>종료 및 분리
다음은 정상적으로 종료에 대 한 설명입니다.  
  
## <a name="discussion"></a>토론  
 이후에 [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) 또는 [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) 없는 중단점, 예외, 런타임 오류 또는 무한 루프에 응용 프로그램을 디버깅할 수 없는 경우 인터페이스 계속 디버깅 중인 프로그램 완료 될 때까지 실행 됩니다. 이 정상적으로 종료 합니다.  
  
 보내야는 [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) 정상 종료를 구현 하 합니다. 이 위해서는 구현는 [IDebugProgramDestroyEvent2::GetExitCode](../../extensibility/debugger/reference/idebugprogramdestroyevent2-getexitcode.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 디버그 엔진 만들기](../../extensibility/debugger/creating-a-custom-debug-engine.md)