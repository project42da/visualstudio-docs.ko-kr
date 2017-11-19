---
title: "SCRIPT_DEBUGGER_OPTIONS 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: SCRIPT_DEBUGGER_OPTIONS Enumeration
ms.assetid: aef41ec0-6f65-48e8-a69e-44b4e4fb929f
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 54b910562670104f0fb5679f2b09780afcd17751
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="scriptdebuggeroptions-enumeration"></a>SCRIPT_DEBUGGER_OPTIONS 열거형
옵션 및/또는 연결 된 디버거에 적용 하는 기능 집합을 나타냅니다. 에 사용 된 [IDebugApplicationNode100::GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md) 및 [IDebugApplicationNode100::SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)  
  
> [!IMPORTANT]
>  이러한 상수는 PDM v 10.0 및 보다 구현 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef SCRIPT_DEBUGGER_OPTIONS  
```  
  
## <a name="members"></a>멤버  
  
|멤버|값|설명|  
|------------|-----------|-----------------|  
|SDO_NONE|0x00000000|옵션이 설정 됩니다.|  
|SDO_ENABLE_FIRST_CHANCE_EXCEPTIONS|0x00000001|스크립트 런타임 예외가 발생 하면 BREAKREASON_ERROR 이벤트를 발생 시켜야 나타냅니다. 이 옵션 디버거에 의해 설정 되었거나를 통해 사용자 코드로 설정할 `Debug.enableFirstChanceExceptions(<true&#124;false>)`합니다.|  
|SDO_ENABLE_WEB_WORKER_SUPPORT|0x00000002|연결 된 디버거에 웹 작업자를 지원함을 나타냅니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)