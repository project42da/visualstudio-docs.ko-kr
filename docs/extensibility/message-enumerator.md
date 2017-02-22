---
title: "메시지 열거자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "메시지 열거자"
  - "소스 제어 플러그 인, 메시지 열거형"
ms.assetid: 4a4faa0d-d352-40ea-a21d-c09ea286a8e1
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 메시지 열거자
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다음 플래그에 사용 되는 `TEXTOUTPROC` 함수를 호출할 때 IDE에서 제공 하는 콜백 함수는 [SccOpenProject](../extensibility/sccopenproject-function.md) \(참조 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md) 콜백 함수에 대 한 내용은\).  
  
 프로세스를 취소 하는 IDE가 요청 되 면 취소 메시지 중 하나가 발생할 수 있습니다. 이 경우 소스 제어 플러그 인 사용 하 여 `SCC_MSG_STARTCANCEL` 표시 하도록 IDE에 게는 **취소** 단추입니다. 그런 다음 일반 메시지 집합을 보낼 수 있습니다. 이러한 반환 중 `SCC_MSG_RTN_CANCEL`, 플러그 인 작업을 종료 하 고 반환 합니다. 플러그 인을 들 여 또한 폴링합니다 `SCC_MSG_DOCANCEL` 주기적으로 알아보려면 경우 사용자가 작업을 취소 했습니다. 모든 작업을 완료 하거나 사용자가 취소 된 경우 플러그 인 보낼 때 `SCC_MSG_STOPCANCEL`합니다.`SCC_MSG_INFO`, SCC\_MSG\_WARNING, SCC\_MSG\_ERROR 형식 메시지의 스크롤 목록에 표시 되는 메시지에 사용 되 고 있습니다.`SCC_MSG_STATUS` 상태 표시줄 또는 일시적인 디스플레이 영역에서 텍스트 표시 해야 함을 나타내는 특수 한 형식이입니다. 목록에는 영구적으로 남아 있지 않습니다.  
  
## 구문  
  
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
  
## 멤버  
 SCC\_MSG\_RTN\_CANCEL  
 취소를 나타내기 위해 콜백에서 반환 합니다.  
  
 SCC\_MSG\_RTN\_OK  
 계속 하려면 콜백에서 반환 합니다.  
  
 SCC\_MSG\_INFO  
 정보 메시지가입니다.  
  
 SCC\_MSG\_WARNING  
 메시지는 경고입니다.  
  
 SCC\_MSG\_ERROR  
 메시지 오류입니다.  
  
 SCC\_MSG\_STATUS  
 메시지 상태 표시줄 위한 것입니다.  
  
 SCC\_MSG\_DOCANCEL  
 텍스트가 없습니다. IDE 반환 `SCC_MSG_RTN_OK` 또는 `SCC_MSG_RTN_CANCEL`합니다.  
  
 SCC\_MSG\_STARTCANCEL  
 취소 루프를 시작 합니다.  
  
 SCC\_MSG\_STOPCANCEL  
 취소 루프를 중지합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)   
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)