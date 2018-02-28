---
title: "IMachineDebugManagerEvents 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IMachineDebugManagerEvents interface
ms.assetid: 468de2f4-49e0-4f6f-ba0c-0f5f6832c092
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 369dc8d182efe7bf9697454d0e4b1c9c1a10c027
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="imachinedebugmanagerevents-interface"></a>IMachineDebugManagerEvents 인터페이스
실행에 대 한 변경 내용을 알리는 컴퓨터 디버그 관리자 유지 관리 하는 응용 프로그램 목록입니다. 이 인터페이스 응용 프로그램의 동적 목록을 표시 하려면 IDE 디버거에서 사용할 수 있습니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IMachineDebugManagerEvents` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IMachineDebugManagerEvents::onAddApplication](../../winscript/reference/imachinedebugmanagerevents-onaddapplication.md)|응용 프로그램 실행에 추가 될 때 이벤트를 처리 응용 프로그램 목록입니다.|  
|[IMachineDebugManagerEvents::onRemoveApplication](../../winscript/reference/imachinedebugmanagerevents-onremoveapplication.md)|응용 프로그램 실행에서 제거 될 때 이벤트를 처리 응용 프로그램 목록입니다.|