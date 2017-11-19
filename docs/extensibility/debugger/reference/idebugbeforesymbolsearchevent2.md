---
title: IDebugBeforeSymbolSearchEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugBeforeSymbolSearchEvent2 interface
ms.assetid: 679fd7b1-765a-41a8-a046-63240c09a499
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9541c7008129f47df93e2e4cf2c3e8248742b0c8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugbeforesymbolsearchevent2"></a>IDebugBeforeSymbolSearchEvent2
기호 로드 하는 동안 메시지 표시줄 세션 디버그 관리자 (SDM) 상태를 설정 하려면이 인터페이스를 전송 하는 디버그 엔진 (DE).  
  
## <a name="syntax"></a>구문  
  
```  
IDebugBeforeSymbolSearchEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE 상태 표시줄 메시지 기호 로드 하는 동안 설정 해야 하는 경우이 인터페이스를 구현 합니다. 이 인터페이스를 사용 하거나 스크립트 번역기의 일부인 디버그 엔진에 의해서만 구현 됩니다. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 해당이 인터페이스와 같은 개체에 대해 인터페이스를 구현 해야 합니다 (은 SDM 사용 하 여 **QueryInterface** 액세스로는 **IDebugEvent2** 인터페이스).  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 DE을 만들어 상태 표시줄 메시지 기호 로드 하는 동안 설정 해야 하는 경우이 이벤트 개체를 보냅니다. 이벤트를 사용 하 여 보내집니다는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 은 SDM 디버깅 중인 프로그램에는 연결 된 경우 제공한 콜백 함수입니다.  
  
## <a name="methods"></a>메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugBeforeSymbolSearchEvent2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetModuleName](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2-getmodulename.md)|현재 디버깅 중인 모듈의 이름을 검색 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll