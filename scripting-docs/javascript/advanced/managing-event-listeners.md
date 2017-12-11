---
title: "이벤트 수신기 관리 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 87717f5d-b0c6-4c8d-a293-476002b7bfcf
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6a97c579716b9964b8dfb93db419e9a70160d33a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="managing-event-listeners"></a>이벤트 수신기 관리
DOM 요소 또는 개체의 수명이 연결된 이벤트 수신기의 수명과 다르면 메모리 누수를 방지하기 위해 [removeEventListener](http://msdn.microsoft.com/library/ie/ff975250\(v=vs.85\).aspx) 메서드를 사용해야 할 수 있습니다.  
  
## <a name="event-listeners-and-object-scope"></a>이벤트 수신기 및 개체 범위  
 다음 코드 예제에서는 `dataObjFactory()` 함수 호출 시 메모리 누수를 발생시킬 수 있는 코드를 보여 줍니다. 이 코드에서는 새 데이터 개체를 만들 때마다 데이터 개체에 대해 이벤트 수신기가 등록됩니다. `dataReady()` 이벤트 처리기에서 현재 데이터 개체를 사용할 수 있도록 `addEventListener`에서 [bind 메서드(함수)](../../javascript/reference/bind-method-function-javascript.md)가 사용됩니다.  
  
```JavaScript  
 var data;  
 var dataObj;  
  
 var dataReadyEvent = document.createEvent("Event");  
 dataReadyEvent.initEvent("dataReady", true, false);  
  
 function DataObject() {  
  
     this.name = "Data Object";  
     this.data = function () {  
         return data;  
     }  
     this.onDataCompleted = dataReady;  
     // this.handlerRef = this.onDataCompleted.bind(this);  
  
     // document.addEventListener('dataReady', this.handlerRef);  
     document.addEventListener('dataReady', this.onDataCompleted.bind(this));  
 }  
  
 // Runs when the data is available.  
 function dataReady() {  
     if (console && console.log) {  
         console.log("object value: " + this.name);  
         console.log("object value: " + this.data());  
     }  
 }  
  
setTimeout(function () {  
    // Generate data after a timeout period.  
    data = [0, 1, 2, 3];  
    document.dispatchEvent(dataReadyEvent);  
}, 10000);  
  
function dataObjFactory() {  
     for (var x = 0; x < 100; x++) {  
         if (dataObj) {  
             // The following line of code has no effect.  
             document.removeEventListener('dataReady', dataObj.onDataCompleted);  
             dataObj = null;  
         }  
         dataObj = new DataObject();  
     }  
 }  
  
 dataObjFactory();  
```  
  
 각 데이터 개체의 수신기는 데이터 개체와 수명이 다른 `document` 개체를 사용하여 등록됩니다. 이처럼 각 데이터 개체에 대해 이벤트 수신기가 등록되므로 `document` 개체가 범위 내에 유지되면 이벤트 수신기에서 가비지가 수집되지 않습니다. 일부 최신 JavaScript 디자인 패턴에서는 웹 앱의 수명 동안 문서 개체가 범위 내에 유지됩니다. 메모리 누수를 방지하기 위해 `removeEventListener` 함수에서 `dataObjFactory`가 호출됩니다. 그러나 `bind` 함수가 반환하는 이벤트 처리기의 바인딩된 버전에 대해 `removeEventListener`가 호출되지 않았으므로 이 코드는 실패합니다.  
  
 이 코드를 수정하여 가비지 수집에서 데이터 개체를 사용할 수 있도록 하려면 먼저 이 코드에 나와 있는 대로 이벤트 처리기의 바인딩된 버전에 대한 참조를 저장한 다음 저장된 참조를 `addEventListener`로 전달해야 합니다. 수정된 `DataObject`의 코드는 다음과 같습니다.  
  
```JavaScript  
function DataObject() {  
  
    this.name = "Data Object";  
    this.data = function () {  
        return data;  
    }  
    this.onDataCompleted = dataReady;  
    this.handlerRef = this.onDataCompleted.bind(this);  
  
    document.addEventListener('dataReady', this.handlerRef);  
    // document.addEventListener('dataReady', this.onDataCompleted.bind(this));  
}  
  
```  
  
 마지막으로 바인딩된 함수의 저장된 참조(`removeEventListener`)에 대해 `handlerRef`를 호출해야 합니다. 수정된 `dataObjFactory`의 코드는 다음과 같습니다.  
  
```JavaScript  
function dataObjFactory() {  
     for (var x = 0; x < 100; x++) {  
         if (dataObj) {  
             document.removeEventListener('dataReady', dataObj.handlerRef);  
         }  
         dataObj = new DataObject();  
     }  
 }  
  
```  
  
 이제 `removeEventListener` 호출이 작동하며, `document` 개체가 범위 내에 유지되는 동안에도 불필요한 데이터 개체를 가비지 수집할 수 있습니다.