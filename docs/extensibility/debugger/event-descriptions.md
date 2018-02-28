---
title: "이벤트 설명 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: 09f61652-7e16-4bb0-8055-f61a84bf384e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 6ec084c0d985ce5cc3cb0a886bd1fdcaf6cc3e54
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="event-descriptions"></a>이벤트 설명
이벤트의 각 형식은 특정 목적을 갖습니다.  
  
## <a name="events-and-the-reasons-for-their-use"></a>이벤트 및 사용 하는 이유  
  
|이벤트(event)|설명|  
|-----------|-----------------|  
|문서 이벤트를 활성화 합니다.|이 경우 디버그 엔진 (DE)를 열거나 문서를 포그라운드로 전환 IDE가 때 발생 합니다.|  
|바인딩된 중단점 또는 오류 이벤트 중단점|중단점 또는 때 중단점을 바인딩할 수 없습니다 바인딩되며 오류가 반환 됩니다 때 보냅니다.|  
|바인딩되지 않은 중단점 이벤트|코드에서 바인딩 해제 바인딩된 중단점 때 발생 합니다.|  
|이벤트를 중지할 수 있습니다.|사용자 코드에서 지정 된 시점에서 중지 하려는 지 여부를 결정 하는 IDE에 전송 합니다.|  
|중단점 이벤트|코드 또는 데이터 중단점이 적중 될 때 발생 합니다.|  
|문서 텍스트 이벤트|문서에서 텍스트를 변경할 때 발생 합니다. 이러한 이벤트를 통해 전송 되지 않습니다는 `IDebugEventCallBack2::Event` 메서드.|  
|엔진 이벤트 생성|엔진을 처음으로 만들어질 때 보냅니다.|  
|항목 시점 이벤트|디버깅 중인 프로그램에 초기화 코드를 실행 하 고 해당 첫 번째 사용자 진입점에 도달할 때 보냅니다.|  
|예외 이벤트|실행 중인 프로그램 예외에 도달 하면 전송 합니다.|  
|식 평가 완료 이벤트|비동기 식 평가 완료 하는 경우 전송 합니다.|  
|기호 이벤트 찾기|DE 모듈의 기호 찾기로 사용자에 게 확인 해야 할 때마다 전송 합니다.|  
|완전 한 로드 이벤트|있고 경우에 시작 프로그램 로드가 완료 될 첫 번째 코드를 곧 실행 프로그램에 전송 합니다.|  
|메시지 이벤트|사용자에 게 메시지를 보내면 전송 합니다.|  
|모듈 로드 이벤트|새 모듈 로드 되거나 언로드될 때 보냅니다.|  
|출력 문자열 이벤트|프로그램 디버그 출력을 쓸 때 보냅니다.|  
|생성 및 소멸 이벤트|Visual Studio IDE의 추적할 수 디버깅 중인 프로그램의 상태에 있으므로 생성 또는 소멸 프로세스, 프로그램, 속성, 세션 및 스레드를 발표 하 게 전송 합니다.|  
|단계 완료 이벤트|단계가 완료 되 면 전송 합니다.|  
|스레드 이름 변경 이벤트|스레드의 이름을 변경할 때 보냅니다.|  
|프로그램 이름 변경 이벤트|사용자는 프로그램의 이름을 변경할 때 보냅니다.|  
  
## <a name="see-also"></a>참고 항목  
 [이벤트 보내기](../../extensibility/debugger/sending-events.md)