---
title: "IDebugSyncOperation 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugSyncOperation 인터페이스"
ms.assetid: 8d714492-1836-462c-980a-c99e91a2c81b
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugSyncOperation 인터페이스
특정 차단 된 스레드를 중첩 하는 동안 수행 해야 할 작업 \(예: 식 평가\)를 추상화 하는 스크립트 엔진을 수 있습니다.  인터페이스는 또한 응답 작업을 취소 하는 메커니즘을 제공 합니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugSyncOperation` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugSyncOperation::GetTargetThread](../../winscript/reference/idebugsyncoperation-gettargetthread.md)|대상 응용 프로그램 스레드가이 동기 작업을 반환합니다.|  
|[IDebugSyncOperation::Execute](../../winscript/reference/idebugsyncoperation-execute.md)|동기적으로 작업을 수행 하 고 반환 합니다.|  
|[IDebugSyncOperation::InProgressAbort](../../winscript/reference/idebugsyncoperation-inprogressabort.md)|진행 중인 다른 스레드에서 작업을 취소합니다.|