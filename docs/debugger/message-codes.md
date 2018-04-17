---
title: 메시지 코드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- message codes
ms.assetid: 9f91f4e2-c1f1-4349-9f11-2fbbf59654be
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 96f980570bcbee7a26bf742556379899c0a88436
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="message-codes"></a>메시지 코드
에 표시 된 각 메시지 줄 [메시지 뷰](../debugger/messages-view.md) 'P'를 포함의 '의 ' 또는 'R' 코드입니다. 이러한 코드는 다음과 같은 의미가 있습니다.  
  
|코드|의미|  
|----------|-------------|  
|P|메시지의 큐에 게시 된는 **PostMessage** 함수입니다. 정보가는 메시지의 최종 처리와 관련 된 ´ ù.|  
|S|메시지는 **SendMessage** 함수입니다. 즉, 수신자 처리 하 고 메시지를 반환 될 때까지 보낸 사람이 제어 권한을 다시 하지 않습니다. 따라서 수신기는 보낸 사람에 게 반환 값을 통과 수 있습니다.|  
|s|메시지를 보냈지만 보안 반환 값에 액세스할 수 없습니다.|  
|R|각각의 ' 선은 메시지 반환 값을 나열 하는 해당 'R' (return) 줄 합니다. 경우에 따라 메시지 호출이 중첩 되는, 즉, 특정 메시지 처리기는 다른 메시지를 보냅니다.|