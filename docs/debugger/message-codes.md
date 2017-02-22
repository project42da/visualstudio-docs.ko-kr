---
title: "Message Codes | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "message codes"
ms.assetid: 9f91f4e2-c1f1-4349-9f11-2fbbf59654be
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Message Codes
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[메시지 뷰](../debugger/messages-view.md)에 표시된 각 메시지 줄에는 'P', 'S', 's' 또는 'R' 코드가 포함되어 있습니다.  이러한 코드의 의미는 다음과 같습니다.  
  
|코드|의미|  
|--------|--------|  
|P|**PostMessage** 함수를 통해 메시지가 큐에 게시되었습니다.  메시지의 최종 처리에 대한 정보를 사용할 수 없습니다.|  
|S|**SendMessage** 함수를 통해 메시지가 전송되었습니다.  즉, 수신자가 메시지를 처리하고 반환할 때까지 전송자는 제어 권한을 다시 가질 수 없습니다.  따라서 수신자는 전송자에게 반환 값을 다시 전달할 수 있습니다.|  
|s|메시지가 전송되었지만 보안상의 이유로 반환 값에 액세스할 수 없습니다.|  
|R|각 'S' 줄에는 메시지 반환 값을 나열하는 해당 'R'\(반환\) 줄이 있습니다.  메시지 호출이 중첩되는 경우도 있는데, 이는 특정 메시지 처리기가 다른 메시지를 보냄을 의미합니다.|