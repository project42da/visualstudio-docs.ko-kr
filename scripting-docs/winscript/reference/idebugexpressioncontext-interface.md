---
title: "IDebugExpressionContext 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugExpressionContext Interface
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpressionContext interface
ms.assetid: 52af82e8-0dec-49e2-a7f3-d00f66ca1401
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0c55a2f270e4c82c578450092e5066b19fe9e606
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugexpressioncontext-interface"></a>IDebugExpressionContext 인터페이스
식을 계산할 수 있는 컨텍스트를 나타냅니다. 스택 프레임 개체는이 인터페이스를 구현합니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IDebugExpressionContext` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugExpressionContext::ParseLanguageText](../../winscript/reference/idebugexpressioncontext-parselanguagetext.md)|지정된 된 텍스트에 대 한 디버그 식을 만듭니다.|  
|[IDebugExpressionContext::GetLanguageInfo](../../winscript/reference/idebugexpressioncontext-getlanguageinfo.md)|이 컨텍스트를 소유 하는 언어에 대 한 이름 및 GUID를 반환 합니다.|