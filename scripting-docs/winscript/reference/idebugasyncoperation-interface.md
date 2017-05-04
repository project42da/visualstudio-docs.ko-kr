---
title: "IDebugAsyncOperation 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugAsyncOperation 인터페이스"
ms.assetid: ebb2ea75-1443-4d8a-812d-171a166f5f9d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugAsyncOperation 인터페이스
구현 프로세스 디버그 관리자는 `IDebugAsyncOperation` 인터페이스.  언어 엔진을 호출 하는 `IDebugApplication::CreateAsyncDebugOperation` 이 인터페이스에 대 한 참조를 얻는 방법.  언어 엔진을 사용할 수 있는 `IDebugAsyncOperation` 동기 디버그 작업 비동기 액세스를 제공 하는 인터페이스.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugAsyncOperation` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugAsyncOperation::GetSyncDebugOperation](../../winscript/reference/idebugasyncoperation-getsyncdebugoperation.md)|이 개체와 관련 된 동기 디버그 작업을 반환 합니다.|  
|[IDebugAsyncOperation::Start](../../winscript/reference/idebugasyncoperation-start.md)|비동기 작업이 시작 됩니다.|  
|[IDebugAsyncOperation::Abort](../../winscript/reference/idebugasyncoperation-abort.md)|작업을 취소 합니다.|  
|[IDebugAsyncOperation::QueryIsComplete](../../winscript/reference/idebugasyncoperation-queryiscomplete.md)|디버그 작업이 완료 되었는지 확인 합니다.|  
|[IDebugAsyncOperation::GetResult](../../winscript/reference/idebugasyncoperation-getresult.md)|반환 값 및 동기 디버그 작업에서 반환 되는 개체 매개 변수를 제공합니다.|