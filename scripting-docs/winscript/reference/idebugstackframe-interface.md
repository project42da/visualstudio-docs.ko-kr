---
title: "IDebugStackFrame 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugStackFrame 인터페이스"
ms.assetid: e95c1b4f-17c1-490c-a56b-c25fa45d4822
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugStackFrame 인터페이스
스레드 스택의 논리 스택 프레임을 나타냅니다.  호출의 `IDebugStackFrame::QueryInterface` 를 구하려면 메서드는 `IDebugExpressionContext` 식 평가 및 조사식 창을 허용 하는 인터페이스.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugStackFrame` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugStackFrame::GetCodeContext](../../winscript/reference/idebugstackframe-getcodecontext.md)|스택 프레임과 연결 된 코드가 현재 컨텍스트를 반환 합니다.|  
|[IDebugStackFrame::GetDescriptionString](../../winscript/reference/idebugstackframe-getdescriptionstring.md)|스택 프레임의 짧은 또는 긴 텍스트 설명을 반환합니다.|  
|[IDebugStackFrame::GetLanguageString](../../winscript/reference/idebugstackframe-getlanguagestring.md)|언어의 짧은 또는 긴 텍스트 설명을 반환합니다.|  
|[IDebugStackFrame::GetThread](../../winscript/reference/idebugstackframe-getthread.md)|이 스택 프레임과 연결 된 스레드를 반환 합니다.|  
|[IDebugStackFrame::GetDebugProperty](../../winscript/reference/idebugstackframe-getdebugproperty.md)|속성 브라우저에 현재 프레임을 반환합니다.|