---
title: "getInt8 메서드(DataView) | Microsoft Docs"
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
ms.assetid: 867eefa0-f2e0-44b9-85bc-efb849d55138
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# getInt8 메서드(DataView)
뷰의 시작 지점에서 지정된 오프셋 바이트 수만큼 Int8 값을 가져옵니다.  맞춤 제약 조건이 없습니다. 멀티바이트 값은 모든 오프셋에서 페치될 수 있습니다.  
  
## 구문  
  
```  
var testInt = dataView.getInt8(byteOffset);   
```  
  
## 매개 변수  
 `testInt`  
 필수 요소.  메서드에서 반환되는 Int8 값입니다.  
  
 `byteOffset`  
 값을 검색해야 하는 버퍼의 위치입니다.  
  
## 설명  
 이러한 메서드는 뷰의 끝을 벗어나서 읽으면 예외가 발생합니다.  
  
## 예제  
 다음 예제에서는 DataView에서 첫 번째 Int8를 가져오는 방법을 보여 줍니다.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.getInt8(0));  
        }  
    }  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]