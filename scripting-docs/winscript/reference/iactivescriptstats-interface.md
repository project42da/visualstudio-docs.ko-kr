---
title: "IActiveScriptStats 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IActiveScriptStats interface
ms.assetid: dbe84d6f-1b77-4877-aced-cd4e01ead5b5
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d459b89bde609dfdf5963d4b6b10b24db4706a7e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptstats-interface"></a>IActiveScriptStats 인터페이스
호스트를를 실행 중인 스크립트의 통계를 쿼리할 수 있습니다. 호스트를 결정 하는 경우 스크립트에서 완료 시간이 너무 오래 걸렸습니다.이 정보를 사용할 수 있습니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IActiveScriptStats` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptStats::GetStat](../../winscript/reference/iactivescriptstats-getstat.md)|표준 스크립트 통계 중 하나를 반환 합니다.|  
|[IActiveScriptStats::GetStatEx](../../winscript/reference/iactivescriptstats-getstatex.md)|사용자 지정 스크립트 통계를 반환 합니다.|  
|[IActiveScriptStats::ResetStats](../../winscript/reference/iactivescriptstats-resetstats.md)|이 스크립트에 대 한 통계를 다시 설정합니다.|