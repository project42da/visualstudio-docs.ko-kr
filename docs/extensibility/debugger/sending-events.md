---
title: "이벤트를 보내는 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], sending events
ms.assetid: 064231e7-59b5-4437-8240-a23c0a7ec2a9
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bf4c3b0f494a5825820b8f794ccaf5dc727786e3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="sending-events"></a>이벤트 전송
디버거와 디버그 엔진 (DE) 간의 통신에 대 한 메커니즘은 DCOM을 기반으로 하는 이벤트 모델. 이벤트는 COM 개체로 전송 되 고, 각 이벤트에 다음을 지정 하는 매개 변수:  
  
-   호출한 이벤트 DE 합니다.  
  
-   상황에 대 한 설명입니다.  
  
-   프로세스, 프로그램 및 스레드 정보 이벤트가 발생 한의 컨텍스트를 식별 하는 합니다. 프로세스는 DE에서 전송 된 이벤트에 대 한 전송 되지 않습니다.  
  
-   동기 또는 비동기 이벤트 인지 여부를 나타내는 이벤트 형식입니다.  
  
 메서드를 사용 하 여 모든 디버그 이벤트는 전송 [IDebugEventCallback2::Event](../../extensibility/debugger/reference/idebugeventcallback2-event.md)합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [이벤트 소스](../../extensibility/debugger/event-sources-visual-studio-sdk.md)  
 이벤트의 두 원본에 설명: 디버그 엔진 (DE) 및 세션 (SDM) 관리자를 디버그 합니다.  
  
 [지원되는 이벤트 형식](../../extensibility/debugger/supported-event-types.md)  
 현재 지원 되는 이벤트 종류: 비동기 및 동기 합니다.  
  
 [이벤트 설명](../../extensibility/debugger/event-descriptions.md)  
 이벤트 및 용도 대 한 이유를 정의합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [사용자 지정 디버그 엔진 만들기](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 DE 디버깅 서비스를 제공 해석기 또는 운영 체제와 함께 작동 하는 방법을 설명 합니다.