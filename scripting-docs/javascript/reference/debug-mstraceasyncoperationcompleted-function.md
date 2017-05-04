---
title: "Debug.msTraceAsyncOperationCompleted 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 9b628b71-61f1-478a-857f-5e1f607db56c
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# Debug.msTraceAsyncOperationCompleted 함수
비동기 작업이 완료되었음을 나타냅니다.  
  
## 구문  
  
```  
Debug.msTraceAsyncOperationCompleted(asyncOperationId, status)  
```  
  
#### 매개 변수  
 `asyncOperationId`  
 필수 요소.  비동기 작업과 연결된 ID입니다.  
  
 `status`  
 선택 사항입니다.  비동기 작업의 상태입니다.  지정되지 않은 경우 `Debug.MS_ASYNC_OP_STATUS_SUCCESS`가 사용됩니다.  
  
## 설명  
 비동기 작업이 완료되면 이 함수를 호출합니다.  
  
 `asyncOperationId`는 이전에 `Debug.msTraceAsyncOperationStarting`에서 반환된 작업 ID와 일치해야 합니다.  
  
 `status`에 대해 가능한 값은 다음과 같습니다.  
  
-   `Debug.MS_ASYNC_OP_STATUS_SUCCESS`  
  
-   `Debug.MS_ASYNC_OP_STATUS_CANCELED`  
  
-   `Debug.MS_ASYNC_OP_STATUS_ERROR`  
  
> [!NOTE]
>  일부 디버깅 도구는 디버거에 전달된 정보를 표시하지 않습니다.  
  
## 예제  
 다음 코드는 [!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱에 대한 비동기 호출을 추적하는 예제를 제공합니다.  
  
```javascript  
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
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]