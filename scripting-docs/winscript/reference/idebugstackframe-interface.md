---
title: "IDebugStackFrame 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugStackFrame interface
ms.assetid: e95c1b4f-17c1-490c-a56b-c25fa45d4822
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 36fa0ba2d1b4049ad41ff0502ed33be0a706d9f6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugstackframe-interface"></a>IDebugStackFrame 인터페이스
스레드 스택에 논리 스택 프레임을 나타냅니다. 호출의 `IDebugStackFrame::QueryInterface` 메서드는 `IDebugExpressionContext` 인터페이스를 통해 식 평가 및 조사식 창.  
  
 상속 된 메서드 외에도 `IUnknown`, `IDebugStackFrame` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugStackFrame::GetCodeContext](../../winscript/reference/idebugstackframe-getcodecontext.md)|스택 프레임을 연관 된 현재 코드 컨텍스트를 반환 합니다.|  
|[IDebugStackFrame::GetDescriptionString](../../winscript/reference/idebugstackframe-getdescriptionstring.md)|스택 프레임의 짧거나 긴 텍스트 설명을 반환합니다.|  
|[IDebugStackFrame::GetLanguageString](../../winscript/reference/idebugstackframe-getlanguagestring.md)|언어의 짧은 또는 긴 텍스트 설명을 반환합니다.|  
|[IDebugStackFrame::GetThread](../../winscript/reference/idebugstackframe-getthread.md)|이 스택 프레임과 연결 된 스레드를 반환 합니다.|  
|[IDebugStackFrame::GetDebugProperty](../../winscript/reference/idebugstackframe-getdebugproperty.md)|현재 프레임에 대 한 속성 브라우저를 반환합니다.|