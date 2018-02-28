---
title: "IProvideExpressionContexts 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IProvideExpressionContexts interface
ms.assetid: e4c70f2c-7d86-4fdc-a1cb-f5a0bb8ed037
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 402b439da6f1fa369accacb27f987ac77119e343
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iprovideexpressioncontexts-interface"></a>IProvideExpressionContexts 인터페이스
특정 구성 요소에서 알려진 식 컨텍스트를 열거 하는 방법을 제공 합니다. 스크립트 엔진은 일반적으로이 인터페이스를 구현 합니다.  
  
 프로세스 디버그 관리자가이 인터페이스를 사용 하 여 주어진된 스레드의와 관련 된 모든 전역 식 컨텍스트를 찾을 수 있습니다.  
  
> [!NOTE]
>  이 인터페이스에서 관심 있는 스레드 내에서 호출 됩니다. 구현 자가 현재 스레드를 식별 하 고 적절 한 열거자를 반환 합니다.  
  
## <a name="methods"></a>메서드  
 상속 된 메서드 외에도 `IUnknown`, `IProvideExpressionContexts` 인터페이스는 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IProvideExpressionContexts::EnumExpressionContexts](../../winscript/reference/iprovideexpressioncontexts-enumexpressioncontexts.md)|이 구성 요소에서 식 컨텍스트에서의 열거자를 반환 합니다.|