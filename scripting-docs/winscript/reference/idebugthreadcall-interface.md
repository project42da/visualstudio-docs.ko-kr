---
title: "IDebugThreadCall 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugThreadCall interface
ms.assetid: 9a9a9892-f310-4ef3-8db2-4f868be52d7e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8b2b1b500aec08520166d9092edfa6a58c1df0fa
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugthreadcall-interface"></a>IDebugThreadCall 인터페이스
`IDebugThreadCall` 인터페이스는 일반적으로 사용 하 여 크로스 스레드 호출 하는 구성 요소에서 구현에서 `IDebugThread` 마샬링 구현 프로세스 디버그 관리자 (PDM)에서 제공 합니다.  
  
 PDM 호출은 `IDebugThreadCall` 원하는 스레드에서 인터페이스 및 `IDebugThreadCall` 인터페이스 원하는 구현에 대 한 호출을 발송 합니다. `IDebugThreadCall` 인터페이스는 적절 한 상위 매개 변수에서 전달 된 매개 변수 정보를 캐스팅 합니다.  
  
 `IDebugThreadCall` 인터페이스는 자유 스레드 개체가 있습니다.  
  
## <a name="methods"></a>메서드  
 상속 된 메서드 외에도 `IUnknown`, `IDebugThreadCall` 인터페이스는 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugThreadCall::ThreadCallHandler](../../winscript/reference/idebugthreadcall-threadcallhandler.md)|코드가 다른 스레드에서 실행에 대 한 호출을 처리 합니다.|