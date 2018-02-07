---
title: "bind 메서드 사용(JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- bind method [JavaScript]
- this object [JavaScript]
ms.assetid: f608f95b-3b9d-437a-a67a-5a4ef8f6c07f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d185801cc5bba355751147edb79b9c47d21f8eed
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2018
---
# <a name="using-the-bind-method-javascript"></a>bind 메서드 사용(JavaScript)
JavaScript `bind` 메서드는 여러 가지 용도가 있습니다. 일반적으로 이 메서드는 다른 컨텍스트에서 실행되는 함수에 대한 실행 컨텍스트를 유지하는 데 사용됩니다. `bind`는 원본 함수와 동일한 본문을 갖는 새 함수를 만듭니다. `bind`로 전달되는 첫 번째 인수는 바인딩된 함수에서 `this` 키워드의 값을 지정합니다. 또한, 추가로 선택적 인수를 `bind`로 전달할 수 있습니다. 다른 사용 예는 [bind 메서드(함수)](../../javascript/reference/bind-method-function-javascript.md)를 참조하세요. `bind`를 사용하여 함수를 부분적으로 적용하는 예제는 [Hilo JavaScript(Windows 스토어)의 비동기 프로그래밍 패턴 및 팁](http://msdn.microsoft.com/library/windows/apps/jj649740.aspx)을 참조하세요.  
  
## <a name="preserving-the-execution-context-using-bind"></a>Bind를 사용하여 실행 컨텍스트 유지  
 `bind` 함수는 이벤트 수신기를 추가할 때 종종 사용됩니다. 다음 코드 예제에서는 `bind`가 현재 개체(`DataObject`)의 컨텍스트를 유지하는 데 사용됩니다. 데이터 개체는 `bind` 키워드를 사용하여 `this`로 전달되는데, 이벤트 처리기(`dataReadyHandler`) 작동 시 이 키워드를 통해 데이터 개체 속성과 함수에 액세스합니다. `bind`의 작동 방식을 설명하기 위해, 이 코드에서는 사용자 지정 이벤트를 만듭니다.  
  
```JavaScript  
var data;  
  
var dataReadyEvent = document.createEvent("Event");  
dataReadyEvent.initEvent("dataReady", true, false);  
  
function DataObject() {  
    this.name = "Data Object";  
    this.data = function () {  
        return data;  
    }  
    this.onDataCompleted = dataReadyHandler;  
    document.addEventListener('dataReady', this.onDataCompleted.bind(this));  
    // To see the result of not using bind, comment out the preceding line,   
    // and uncomment the following line of code.  
    // document.addEventListener('dataReady', this.onDataCompleted);  
}  
function dataReadyHandler() {  
    if (console && console.log) {  
        console.log("Data object property value: " + this.name);  
        console.log("Data object property value: " + this.data());  
    }  
}  
  
setTimeout(function () {  
    data = [0, 1, 2, 3];  
    document.dispatchEvent(dataReadyEvent);  
    }, 5000);
  
var dataObj = new DataObject();  
  
// Output:  
// Data Object  
// 0,1,2,3  
  
```  
  
 `bind`를 사용하는 코드 줄을 주석으로 처리하고 `addEventListener`를 사용하지 않고 `bind`를 호출하는 코드 줄을 주석 처리 제거한 다음 코드를 다시 실행하면, `dataReadyHandler` 함수가 실패합니다. 예를 들어, `dataReadyHandler`에서 `this.name`이 정의되지 않고, `this.data()` 개체가 더 이상 데이터 개체를 참조하지 않기 때문에 `this`에서 오류가 발생합니다.  
  
## <a name="see-also"></a>참고 항목  
 [bind 메서드(Function)](../../javascript/reference/bind-method-function-javascript.md)
