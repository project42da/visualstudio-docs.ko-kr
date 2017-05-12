---
title: "Windows 런타임 비동기 메서드 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "JavaScript, Windows 런타임 비동기 메서드"
ms.assetid: 70756833-44f7-4383-827f-2ac781558082
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# Windows 런타임 비동기 메서드 사용
많은 Windows 런타임 메서드 특히, 완료하는 데 시간이 오래 걸릴 수 있는 메서드는 비동기입니다.  이러한 메서드는 일반적으로 비동기 동작 또는 작업\(예: `Windows.Foundation.IAsyncAction`, `Windows.Foundation.IAsyncOperation`, `Windows.Foundation.IAsyncActionWithProgress` 또는 `Windows.Foundation.IAsyncOperationWithProgress`\)을 반환합니다.  이러한 메서드는 JavaScript에서 [CommonJS\/Promises\/A](http://go.microsoft.com/fwlink/p/?LinkId=244434) 패턴으로 표현됩니다.  즉, 이러한 메서드는 [then](http://msdn.microsoft.com/ko-kr/c63904fc-465b-4fd5-a1d6-e4fb200248e7) 함수가 포함된 Promise 개체를 반환합니다. 이 함수에 대해서는 작업이 성공하는 경우 결과를 처리하는 `completed` 함수를 제공해야 합니다.  오류 처리기를 제공하지 않으려면 [then](http://msdn.microsoft.com/ko-kr/c63904fc-465b-4fd5-a1d6-e4fb200248e7) 함수 대신 [done](http://msdn.microsoft.com/ko-kr/9a5e6877-a2cf-421f-a91e-37d84ccb40da) 함수를 사용해야 합니다.  
  
> [!IMPORTANT]
>  Windows 런타임 기능은 Internet Explorer에서 실행되는 앱에는 사용할 수 없습니다.  
  
## 비동기 메서드 예제  
 다음 예제에서는 [then](http://msdn.microsoft.com/ko-kr/c63904fc-465b-4fd5-a1d6-e4fb200248e7) 함수가 `createResourceAsync` 메서드의 완료된 값을 나타내는 매개 변수를 사용합니다.  
  
```javascript  
client.createResourceAsync(uri, description, item)  
    // Success.  
    .then(function(newItem) {   
        console.log("New item is: " + newItem.id);  
            });  
```  
  
 이 경우 `createResourceAsync` 메서드가 실패하면 오류 상태로 promise를 반환하지만 예외를 throw하지는 않습니다.  다음과 같이 [then](http://msdn.microsoft.com/ko-kr/c63904fc-465b-4fd5-a1d6-e4fb200248e7) 함수를 사용하여 오류를 처리할 수 있습니다.  
  
```javascript  
client.createResourceAsync(uri, description, item)  
    // Success.  
    .then(function(newItem) {   
              console.log("New item is: " + newItem.id);  
          }  
          function(err) {  
              console.log("Got error: " + err.message);  
          });  
```  
  
 오류를 명시적으로 처리하지 않되 예외를 throw하려면 대신 [done](http://msdn.microsoft.com/ko-kr/9a5e6877-a2cf-421f-a91e-37d84ccb40da) 함수를 사용하면 됩니다.  
  
```javascript  
client.createResourceAsync(uri, description, item)  
    // Success.  
      .done(function(newItem) {   
               console.log("New item is: " + newItem.id);  
            });  
```  
  
 또한 세 번째 함수를 사용하여 완료를 향해 진행된 진행률을 표시할 수 있습니다.  
  
```javascript  
client.createResourceAsync(uri, description, item)  
    // Success.  
      .then(function(newItem) {   
               console.log("New item is: " + newItem.id);  
            },  
    // Error.  
            function(error) {   
               alert("Failed to create a resource.");  
            },  
    // Progress.  
            function(progress, resultSoFar) {   
               setProgressBar(progress);  
            });  
```  
  
 비동기 프로그래밍에 대한 자세한 내용은 [Asynchronous programming](http://msdn.microsoft.com/ko-kr/904ff97c-bb36-4ac5-9eda-a961e3639415)을 참조하세요.  
  
## 참고 항목  
 [JavaScript에서 Windows 런타임 사용](../jswinrt/using-the-windows-runtime-in-javascript.md)