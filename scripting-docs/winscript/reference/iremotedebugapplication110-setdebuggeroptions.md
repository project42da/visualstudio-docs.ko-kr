---
title: IRemoteDebugApplication110::SetDebuggerOptions | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplication110::SetDebuggerOptions
ms.assetid: 58e9fd18-3e0d-47fa-8893-f316146bde84
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 16782329de6268b309710e60e707d629fd9929a1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iremotedebugapplication110setdebuggeroptions"></a>IRemoteDebugApplication110::SetDebuggerOptions
디버거 옵션을 업데이트 하기 위해 호출 합니다. 후에이 메서드를 호출 해야 [IRemoteDebugApplication::ConnectDebugger](../../winscript/reference/iremotedebugapplication-connectdebugger.md)합니다. [IRemoteDebugApplication::DisconnectDebugger](../../winscript/reference/iremotedebugapplication-disconnectdebugger.md) 메서드 기본 옵션을 자동으로 다시 설정 합니다. 옵션 기본값인 0 (SDO_NONE)으로 설정 합니다.  
  
> [!IMPORTANT]
>  [IRemoteDebugApplication 인터페이스](../../winscript/reference/iremotedebugapplication-interface.md) 구현 PDM v11.0 이상에 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetDebuggerOptions(        [in] enum SCRIPT_DEBUGGER_OPTIONS mask,        [in] enum SCRIPT_DEBUGGER_OPTIONS value    );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mask`  
 [SCRIPT_DEBUGGER_OPTIONS 열거형](../../winscript/reference/script-debugger-options-enumeration.md) 마스크입니다.  
  
 `value`  
 [SCRIPT_DEBUGGER_OPTIONS 열거형](../../winscript/reference/script-debugger-options-enumeration.md) 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IRemoteDebugApplication 인터페이스](../../winscript/reference/iremotedebugapplication-interface.md)   
 [IRemoteDebugApplication110 인터페이스](../../winscript/reference/iremotedebugapplication110-interface.md)