---
title: "함수 결과에 할당할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.WebClient.Help.SCRIPT5003"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: ee8ffb3a-1451-4cb3-99bf-5e9cf8b77d79
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 함수 결과에 할당할 수 없습니다.
함수 결과에 값을 할당하려고 했습니다.  함수 결과를 변수에 할당할 수 있지만 변수로 사용할 수는 없습니다.  함수 자체에 새 값을 할당하려면 괄호\(함수 호출 연산자\)를 생략하세요.  다음 예제에서는 이 오류가 발생하는 경우를 보여 줍니다.  
  
```  
myFunction() = 42;  // Attempting to assign the value 42 to the result of the function call.  
```  
  
### 이 오류를 해결하려면  
  
-   함수 호출 결과에 값을 *할당*하지 마세요.  하지만 함수 호출의 결과를 *변수*에 할당할 수는 있습니다.  
  
    ```javascript  
    myVar = myFunction(42);  
    ```  
  
-   또는 반환 값이 아닌 함수 자체를 변수에 할당할 수 있습니다.  
  
    ```javascript  
    myFunction = new Function("return 42;");  
    ```  
  
## 참고 항목  
 [Function 개체](../../javascript/reference/function-object-javascript.md)   
 [JavaScript 코드 작성](../../javascript/writing-javascript-code.md)   
 [함수](../../javascript/functions-javascript.md)