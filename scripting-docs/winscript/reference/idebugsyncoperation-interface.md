---
title: "IDebugSyncOperation 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugSyncOperation interface
ms.assetid: 8d714492-1836-462c-980a-c99e91a2c81b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6705c2aa990aef3cf551a94546bf78a64026cecc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugsyncoperation-interface"></a>IDebugSyncOperation 인터페이스
특정 차단 된 스레드에 중첩 된 동안 수행 해야 하는 작업 (예: 식 평가 경우)을 추상화 하는 스크립트 엔진을 수 있습니다. 인터페이스는 또한 응답 하지 않는 작업을 취소 하기 위한 메커니즘을 제공 합니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IDebugSyncOperation` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugSyncOperation::GetTargetThread](../../winscript/reference/idebugsyncoperation-gettargetthread.md)|이 동기화 작업에 대해 대상 응용 프로그램 스레드를 반환합니다.|  
|[IDebugSyncOperation::Execute](../../winscript/reference/idebugsyncoperation-execute.md)|동기적으로 작업을 수행 하 고 반환 합니다.|  
|[IDebugSyncOperation::InProgressAbort](../../winscript/reference/idebugsyncoperation-inprogressabort.md)|다른 스레드에서 진행 중인 작업을 취소합니다.|