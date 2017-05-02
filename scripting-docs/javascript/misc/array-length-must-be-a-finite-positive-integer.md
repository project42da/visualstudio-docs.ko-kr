---
title: "배열 길이는 유한한 양의 정수여야 합니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5029"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 1a467040-4702-4178-848f-418a5974e907
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# 배열 길이는 유한한 양의 정수여야 합니다.
정수\(정수는 0과 양의 정수 집합으로 구성됨\)가 아닌 인수가 있는 **Array**  생성자를 호출하는 중입니다.  
  
### 이 오류를 해결하려면  
  
-   새 `Array` 개체를 만들 때 양의 정수만 사용합니다.  정수가 아닌 단일 요소가 있는 배열을 만들려는 경우 2단계 프로세스로 수행합니다.  먼저, 요소가 하나 있는 배열을 만들고 첫 번째 요소\(array\[0\]\)에 값을 삽입합니다.  다음은 이 오류를 생성하는 예제입니다.  
  
    ```javascript  
    var piArray = new Array(3.14159);  
    ```  
  
     다음 예제에서는 단일 숫자 요소가 있는 배열을 지정하는 올바른 방법을 보여 줍니다.  
  
    ```javascript  
    var piArray = new Array(1);  
    piArray [0] = 3.14159;  
    ```  
  
     최대 정수 값\(약 40억\) 외에 배열 크기에 상한은 없습니다.  
  
## 참고 항목  
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)