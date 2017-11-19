---
title: "IDebugApplicationThread 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IDebugApplicationThread interface
ms.assetid: f869c328-4409-4b74-a6c3-9e63fc58c63d
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6e731ba866504c9a3c3c9ad081a90a12b161355d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationthread-interface"></a>IDebugApplicationThread 인터페이스
언어 엔진 및 스레드 동기화를 제공 하 고 스레드 관련 디버그 상태 정보를 유지 하는 호스트 수 있습니다. 이 인터페이스를 확장 된 `IRemoteDebugApplicationThread` 스레드에 원격이 아닌 액세스를 제공 하는 인터페이스입니다.  
  
 상속 된 메서드 외에도 `IRemoteDebugApplicationThread`, `IDebugApplicationThread` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugApplicationThread::SynchronousCallIntoThread](../../winscript/reference/idebugapplicationthread-synchronouscallintothread.md)|호출자에 게 응용 프로그램 스레드에서 코드를 실행 하는 메커니즘을 제공 합니다.|  
|[IDebugApplicationThread::QueryIsCurrentThread](../../winscript/reference/idebugapplicationthread-queryiscurrentthread.md)|이 스레드는 현재 실행 중인 스레드 인지 여부를 확인 합니다.|  
|[IDebugApplicationThread::QueryIsDebuggerThread](../../winscript/reference/idebugapplicationthread-queryisdebuggerthread.md)|이 스레드가 디버거 스레드 인지 여부를 확인 합니다.|  
|[IDebugApplicationThread::SetDescription](../../winscript/reference/idebugapplicationthread-setdescription.md)|이 스레드에 대 한 설명을 설정 합니다.|  
|[IDebugApplicationThread::SetStateString](../../winscript/reference/idebugapplicationthread-setstatestring.md)|스레드 상태에 대 한 설명을 설정합니다.|