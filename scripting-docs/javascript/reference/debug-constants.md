---
title: "Debug 상수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 76b572ee-bad0-404e-9fd4-841c9af35642
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e2c50181dc9f40d8665d6caca407232231682d63
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="debug-constants"></a>Debug 상수
디버그 상수는 `Debug` 개체의 속성인 상수 값을 반환합니다.  
  
## <a name="debug-object-constants"></a>Debug 개체 상수  
 다음 표에서 상수 값의 속성을 나열는 [Debug 개체](../../javascript/reference/debug-object-javascript.md)합니다.  
  
|상수|설명|값|  
|--------------|-----------------|-----------|  
|`Debug.MS_ASYNC_CALLBACK_STATUS_ASSIGN_DELEGATE`|비동기 작업이 실행되도록 하려면 동기 작업 항목에서 콜백 또는 연속 작업을 할당합니다.|0|  
|`Debug.MS_ASYNC_CALLBACK_STATUS_JOIN`|결합 비동기 작업의 일부를 만족시키는 동기 작업 항목입니다.|1|  
|`Debug.MS_ASYNC_CALLBACK_STATUS_CHOOSEANY`|선택 비동기 작업을 만족시키는 동기 작업 항목입니다.|2|  
|`Debug.MS_ASYNC_CALLBACK_STATUS_CANCEL`|동기 작업 항목이 취소되었습니다.|3|  
|`Debug.MS_ASYNC_CALLBACK_STATUS_ERROR`|비동기 작업에 오류가 발생하는 동기 작업 항목입니다.|4|  
|`Debug.MS_ASYNC_OP_STATUS_SUCCESS`|비동기 작업이 성공했습니다.|1|  
|`Debug.MS_ASYNC_OP_STATUS_CANCELED`|비동기 작업이 취소되었습니다.|2|  
|`Debug.MS_ASYNC_OP_STATUS_ERROR`|비동기 작업에 오류가 발생했습니다.|3|  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Debug.msTraceAsyncOperationCompleted 함수](../../javascript/reference/debug-mstraceasyncoperationcompleted-function.md)   
 [Debug.msUpdateAsyncCallbackRelation 함수](../../javascript/reference/debug-msupdateasynccallbackrelation-function.md)