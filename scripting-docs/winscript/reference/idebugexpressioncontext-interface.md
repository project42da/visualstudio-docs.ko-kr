---
title: "IDebugExpressionContext 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugExpressionContext Interface
apilocation: jscript.dll
helpviewer_keywords: 
  - "IDebugExpressionContext 인터페이스"
ms.assetid: 52af82e8-0dec-49e2-a7f3-d00f66ca1401
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugExpressionContext 인터페이스
식을 계산할 수 있는 컨텍스트를 나타냅니다.  스택 프레임 개체는이 인터페이스를 구현 합니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugExpressionContext` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugExpressionContext::ParseLanguageText](../../winscript/reference/idebugexpressioncontext-parselanguagetext.md)|지정 된 텍스트는 디버그 식을 만듭니다.|  
|[IDebugExpressionContext::GetLanguageInfo](../../winscript/reference/idebugexpressioncontext-getlanguageinfo.md)|이 컨텍스트를 소유한 언어에 대 한 이름과 GUID를 반환 합니다.|