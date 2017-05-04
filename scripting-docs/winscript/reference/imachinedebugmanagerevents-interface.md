---
title: "IMachineDebugManagerEvents 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IMachineDebugManagerEvents 인터페이스"
ms.assetid: 468de2f4-49e0-4f6f-ba0c-0f5f6832c092
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IMachineDebugManagerEvents 인터페이스
신호 변경 실행 하는 컴퓨터 디버그 관리자에 의해 관리 되는 응용 프로그램 목록입니다.  이 인터페이스 IDE 디버거를 통해 응용 프로그램의 동적 목록을 사용할 수 있습니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IMachineDebugManagerEvents` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IMachineDebugManagerEvents::onAddApplication](../../winscript/reference/imachinedebugmanagerevents-onaddapplication.md)|응용 프로그램 실행에 추가 될 때 이벤트를 처리 합니다. 응용 프로그램 목록입니다.|  
|[IMachineDebugManagerEvents::onRemoveApplication](../../winscript/reference/imachinedebugmanagerevents-onremoveapplication.md)|응용 프로그램 실행에서 제거 될 때 이벤트를 처리 합니다. 응용 프로그램 목록입니다.|