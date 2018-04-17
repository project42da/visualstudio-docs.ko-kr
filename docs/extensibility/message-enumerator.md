---
title: 열거자 메시지 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- message enumerator
- source control plug-ins, message enumeration
ms.assetid: 4a4faa0d-d352-40ea-a21d-c09ea286a8e1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bc945908ac61a0eaa4df49c76725b2291686eac3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="message-enumerator"></a>메시지 열거자
에 사용 되는 다음 플래그는 `TEXTOUTPROC` 함수를 호출할 때 IDE에서 제공 하는 콜백 함수는 [SccOpenProject](../extensibility/sccopenproject-function.md) (참조 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md) 콜백에 대 한 자세한 내용은 함수 사용)입니다.  
  
 IDE는 프로세스를 취소 하려면 요청 되 면 취소 메시지 중 하나 될 수 있습니다. 이 경우 소스 제어 플러그 인 사용 하 여 `SCC_MSG_STARTCANCEL` IDE 표시를 요청 하는 **취소** 단추입니다. 그러면 일반 메시지 집합을 보낼 수 있습니다. 이러한 반환 중 `SCC_MSG_RTN_CANCEL`, 플러그 인 작업을 종료 하 고 반환 합니다. 플러그 인도 폴링합니다 `SCC_MSG_DOCANCEL` 주기적으로 확인 하는 경우 사용자가 작업을 취소 했습니다. 모든 작업을 완료 하거나 사용자가 취소 된 경우 플러그 인 보내는 경우 `SCC_MSG_STOPCANCEL`합니다. `SCC_MSG_INFO`, SCC_MSG_WARNING, 및 SCC_MSG_ERROR 종류는 스크롤 메시지 목록에 표시 하는 메시지에 사용 합니다. `SCC_MSG_STATUS` 상태 표시줄 또는 일시적인 디스플레이 영역에서 텍스트 표시 해야 함을 나타내는 특별 한 형식이입니다. 목록에는 영구적으로 유지 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
enum {   
   SCC_MSG_RTN_CANCEL = -1,   
   SCC_MSG_RTN_OK = 0,   
   SCC_MSG_INFO = 1   
   SCC_MSG_WARNING,   
   SCC_MSG_ERROR,   
   SCC_MSG_STATUS,   
   SCC_MSG_DOCANCEL,   
   SCC_MSG_STARTCANCEL,   
   SCC_MSG_STOPCANCEL   
};  
```  
  
## <a name="members"></a>멤버  
 SCC_MSG_RTN_CANCEL  
 취소를 나타내기 위해 콜백에서 반환 합니다.  
  
 SCC_MSG_RTN_OK  
 계속 하려면 콜백에서 반환 합니다.  
  
 SCC_MSG_INFO  
 메시지는 정보 제공 용입니다.  
  
 SCC_MSG_WARNING  
 메시지는 경고입니다.  
  
 SCC_MSG_ERROR  
 메시지는 오류입니다.  
  
 SCC_MSG_STATUS  
 메시지 상태 표시줄에 대 한 것입니다.  
  
 SCC_MSG_DOCANCEL  
 텍스트가 없습니다. IDE 반환 `SCC_MSG_RTN_OK` 또는 `SCC_MSG_RTN_CANCEL`합니다.  
  
 SCC_MSG_STARTCANCEL  
 취소 루프를 시작 합니다.  
  
 SCC_MSG_STOPCANCEL  
 취소 루프를 중지합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)   
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)