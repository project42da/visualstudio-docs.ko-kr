---
title: "엔진을 디버그 하는 사용자 지정 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, implementing
- debug engines, custom
- debugging [Debugging SDK], custom debug engines
ms.assetid: 52794238-6fae-451c-bf1c-99f344c6f173
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fb5971bf86c6b97d38daaf86f3a093da196020da
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-a-custom-debug-engine"></a>사용자 지정 디버그 엔진 만들기
디버그 엔진 (DE)는 구성 요소로, 특정 런타임 아키텍처를 디버깅할 수 있습니다. 일반적으로 런 타인 환경 당 하나만 DE 구현이 됩니다.  
  
> [!NOTE]
>  TRANSACT-SQL 및 JScript에 대 한 별도 DE 구현을 상태인 VBScript 및 JScript 단일 DE 공유 합니다.  
  
 인터프리터 또는 작업 시스템 실행 제어, 중단점 및 식 평가와 같은 디버깅 서비스를 제공 하는 장치가 작동 합니다. 이러한 서비스 DE 인터페이스를 통해 구현 되 고 다른 작업 모드 간에 전환 하도록 디버거를 발생할 수 있습니다. 자세한 내용은 참조 [작동 모드](../../extensibility/debugger/operational-modes.md)합니다.  
  
 DE 만드는 다음 단계로 구성 됩니다.  
  
1.  Visual Studio와 함께 한 DE을 등록 하는 중입니다.  
  
2.  디버깅할 프로그램을 사용 하도록 설정  
  
3.  실행 제어 및 상태 평가  
  
4.  이벤트 전송  
  
5.  종료 및 분리  
  
## <a name="in-this-section"></a>단원 내용  
 [사용자 지정 디버그 엔진 등록](../../extensibility/debugger/registering-a-custom-debug-engine.md)  
 사용할 수 있도록 Visual Studio와 함께 디버그 엔진을 등록 하는 데 필요한 단계에 설명 합니다.  
  
 [디버그할 프로그램을 사용하도록 설정](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)  
 하 여 DE 프로그램을 디버그할 수는 DE 시작 하거나 해야 기존 프로그램에 연결에 대해 설명 합니다.  
  
 [실행 제어 및 상태 평가](../../extensibility/debugger/execution-control-and-state-evaluation.md)  
 응용 프로그램을 디버깅가 실행 제어 기능을 구현 필요한 이유를 설명 합니다.  
  
 [이벤트 보내기](../../extensibility/debugger/sending-events.md)  
 이벤트 모델 DCOM을 기반으로 디버거는 DE 사이의 통신에 설명 합니다.  
  
 [종료 및 분리](../../extensibility/debugger/termination-and-detaching.md)  
 의미 없는 중단점, 예외, 런타임 오류 또는 무한 루프에 디버깅할 응용 프로그램 정상 종료를 수행 하는 방법에 설명 합니다.  
  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)  
 디버깅 세션에서 발생 하는 이벤트의 호출 하는 순서에 설명 합니다.  
  
 [방법: 사용자 지정 디버그 엔진 디버그](../../extensibility/debugger/how-to-debug-a-custom-debug-engine.md)  
 사용자 지정 DE 디버깅 하는 방법에 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 디버거 확장성](../../extensibility/debugger/visual-studio-debugger-extensibility.md)