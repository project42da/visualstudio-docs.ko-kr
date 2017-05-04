---
title: "IActiveScriptStats 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptStats 인터페이스"
ms.assetid: dbe84d6f-1b77-4877-aced-cd4e01ead5b5
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptStats 인터페이스
쿼리 통계의 스크립트를 실행 하는 데가 있습니다.  호스트 스크립트 장시간 했는지 확인 하려면이 정보를 사용할 수 있습니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IActiveScriptStats` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IActiveScriptStats::GetStat](../../winscript/reference/iactivescriptstats-getstat.md)|표준 스크립트 통계 중 하나를 반환합니다.|  
|[IActiveScriptStats::GetStatEx](../../winscript/reference/iactivescriptstats-getstatex.md)|사용자 지정 스크립트 통계를 반환 합니다.|  
|[IActiveScriptStats::ResetStats](../../winscript/reference/iactivescriptstats-resetstats.md)|이 스크립트에 대 한 통계를 다시 설정합니다.|