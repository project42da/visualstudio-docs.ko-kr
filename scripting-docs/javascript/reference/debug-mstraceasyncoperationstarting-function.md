---
title: "Debug.msTraceAsyncOperationStarting 함수 | Microsoft Docs"
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
ms.assetid: c8458264-07e0-4cd6-8528-ff7cf009cf9e
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a50c58e352d40a06192664cdf7424348be02d466
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="debugmstraceasyncoperationstarting-function"></a>Debug.msTraceAsyncOperationStarting 함수
비동기 작업에 대한 추적을 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.msTraceAsyncOperationStarting(operationName)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `operationName`  
 필수 요소. 비동기 작업을 식별하는 문자열입니다. `operationName`이 null이거나 정의되지 않은 경우 작업 이름에 빈 문자열이 사용됩니다.  
  
## <a name="return-value"></a>반환 값  
 작업 ID를 나타내는 정수입니다.  
  
## <a name="remarks"></a>설명  
 비동기 작업이 시작되기 전에 이 메서드를 호출합니다.  
  
> [!NOTE]
>  일부 디버깅 도구는 디버거에 전달된 정보를 표시하지 않습니다.  
  
## <a name="example"></a>예제  
 다음 코드는 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에 대한 비동기 호출을 계측하는 예제를 제공합니다.  
  
```JavaScript  
function asyncWrapperFunction() {  
    var opID = Debug.msTraceAsyncOperationStarting('async trace');  
    doSomethingAsync().then(function (result) {  
        Debug.msTraceAsyncOperationCompleted(opID, Debug.MS_ASYNC_OP_STATUS_SUCCESS);  
        Debug.msTraceAsyncCallbackStarting(opID);  
        // Process result of async operation.  
    }, function (error) {  
        Debug.msTraceAsyncOperationCompleted(opID, Debug.MS_ASYNC_OP_STATUS_ERROR);  
        Debug.msTraceAsyncCallbackStarting(opID);  
    });  
  
    Debug.msTraceAsyncCallbackCompleted();  
}  
  
function doSomethingAsync() {  
    return WinJS.Promise.as(true);  
}  
  
asyncWrapperFunction();  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]