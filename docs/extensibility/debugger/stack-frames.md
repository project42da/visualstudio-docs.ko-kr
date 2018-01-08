---
title: "스택 프레임 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stack frames, debugging
- debugging [Debugging SDK], stack frames
- stack frames
ms.assetid: b5e439d4-1e9d-4e13-9cad-bb8b136d4ca8
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 110a68d737ac2f194c7a318c41d05801d69511c3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="stack-frames"></a>스택 프레임
디버거 아키텍처를 기준으로 한 **스택 프레임**:  
  
-   스레드의 실행 컨텍스트를 제공 하는 스택 추상화가입니다. 스레드는 항상 함수 내에서 실행 됩니다. 스택 프레임에 지역 변수는 인수 및 함수를 보유합니다. Visual Studio를 디버깅 하려면 언어 또는 디버깅 중인 환경 스택 프레임을 지원 해야 합니다.  
  
-   수 모두 식별 자체에 대해 설명 하 고 관련 된 스레드를 반환할 수 있습니다. 스택 프레임을 현재 명령 포인터와는 관련된 설명서를 나타내는 코드 컨텍스트 및 식 평가 컨텍스트를 반환할 수도 있습니다.  
  
-   이름, 형식 및 지역 변수 및 인수 값을 설명 하 고 다양 한 IDE 디버그 창에 표시할 속성이 있습니다.  
  
-   로 표시 됩니다는 [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) 인터페이스를 일반적으로 디버그 엔진 (DE) 또는 가상 컴퓨터에 따르면 스레드를 실행 하 여 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [디버그 엔진](../../extensibility/debugger/debug-engine.md)   
 [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md)