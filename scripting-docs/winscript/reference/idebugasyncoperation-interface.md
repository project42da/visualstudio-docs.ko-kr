---
title: "IDebugAsyncOperation 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugAsyncOperation interface
ms.assetid: ebb2ea75-1443-4d8a-812d-171a166f5f9d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 157ed1248535855fcb53ca2eb6f49427fea94149
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugasyncoperation-interface"></a>IDebugAsyncOperation 인터페이스
디버그 프로세스 관리자 구현 하는 `IDebugAsyncOperation` 인터페이스입니다. 호출 하는 언어 엔진에서 `IDebugApplication::CreateAsyncDebugOperation` 이 인터페이스에 대 한 참조를 얻는 메서드를 합니다. 언어 엔진에서 사용할 수는 `IDebugAsyncOperation` 동기 디버그 작업에 대 한 비동기 액세스를 제공 하는 인터페이스입니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IDebugAsyncOperation` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugAsyncOperation::GetSyncDebugOperation](../../winscript/reference/idebugasyncoperation-getsyncdebugoperation.md)|이 개체와 관련 된 동기 디버그 작업을 반환 합니다.|  
|[IDebugAsyncOperation::Start](../../winscript/reference/idebugasyncoperation-start.md)|비동기 작업을 시작 하면 됩니다.|  
|[IDebugAsyncOperation::Abort](../../winscript/reference/idebugasyncoperation-abort.md)|작업을 취소 합니다.|  
|[IDebugAsyncOperation::QueryIsComplete](../../winscript/reference/idebugasyncoperation-queryiscomplete.md)|디버그 작업이 완료 된 경우를 결정 합니다.|  
|[IDebugAsyncOperation::GetResult](../../winscript/reference/idebugasyncoperation-getresult.md)|반환 값과 동기 디버그 작업에서 개체 반환 매개 변수를 제공합니다.|