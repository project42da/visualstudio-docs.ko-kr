---
title: "Debug.msUpdateAsyncCallbackRelation 함수 | Microsoft Docs"
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
ms.assetid: ee6a1efc-375c-4ce8-a4e8-8896ee29f849
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c47ed7f6313646dddf86dd766d7f1027b2d38ad
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="debugmsupdateasynccallbackrelation-function"></a>Debug.msUpdateAsyncCallbackRelation 함수
동기 작업 항목과 연결된 비동기 작업 사이의 관계 상태를 업데이트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.msUpdateAsyncCallbackRelation(relatedAsyncOperationId, relationType)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `relatedAsyncOperationId`  
 필수 요소. 비동기 작업과 연결된 ID입니다.  
  
 `relationType`  
 선택 사항입니다. 관계 상태를 지정하는 값입니다.  
  
## <a name="remarks"></a>설명  
 동기 작업 항목은 일반적으로 비동기 작업에 대한 콜백 함수입니다. 비동기 작업이 중단될 때, 조인 작업이 사용될 때 또는 기타 시나리오에서 이 함수를 호출할 수 있습니다.  
  
 `relationType`에 대해 가능한 값은 다음과 같습니다.  
  
-   `Debug.MS_ASYNC_CALLBACK_STATUS_ASSIGN_DELEGATE`  
  
-   `Debug.MS_ASYNC_CALLBACK_STATUS_JOIN`  
  
-   `Debug.MS_ASYNC_CALLBACK_STATUS_CHOOSEANY`  
  
-   `Debug.MS_ASYNC_CALLBACK_STATUS_CANCEL`  
  
-   `Debug.MS_ASYNC_CALLBACK_STATUS_ERROR`  
  
 자세한 내용은 참조 [Debug 상수](../../javascript/reference/debug-constants.md)합니다.  
  
> [!NOTE]
>  일부 디버깅 도구는 이 함수가 디버거로 전달하는 정보를 표시하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]