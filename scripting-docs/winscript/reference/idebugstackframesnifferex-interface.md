---
title: "IDebugStackFrameSnifferEx 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugStackFrameSnifferEx 인터페이스"
ms.assetid: fd6cf744-dee7-45f2-9a90-355b90372923
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugStackFrameSnifferEx 인터페이스
구성 요소에 의해 알려져 논리 스택 프레임을 열거 하는 방법을 제공 합니다.  스크립트 엔진은 일반적으로이 인터페이스를 구현 합니다.  이 인터페이스를 모든 스택 프레임을 찾으려면 프로세스 디버그 관리자 사용 특정된 스레드와 관련 된.  
  
> [!NOTE]
>  이 인터페이스에서 관심 있는 스레드 내에서 호출 됩니다.  인터페이스 구현은 현재 스레드를 식별 하 고 적절 한 열거자를 반환 해야 합니다.  
  
 `IDebugStackFrameSniffer`에서 상속되는 메서드 외에 `IDebugStackFrameSnifferEx` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugStackFrameSnifferEx::EnumStackFramesEx](../../winscript/reference/idebugstackframesnifferex-enumstackframesex.md)|현재 스레드에 대 한 스택 프레임에 대 한 열거자를 반환합니다.|