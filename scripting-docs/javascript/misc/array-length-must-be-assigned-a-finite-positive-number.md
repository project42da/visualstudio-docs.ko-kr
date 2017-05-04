---
title: "배열 길이에는 유한한 양수가 할당되어야 합니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5030"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: c51c66a4-a543-4e95-b18d-2cfbcb3d1fdd
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 배열 길이에는 유한한 양수가 할당되어야 합니다.
기존 **Array** 개체의 **length** 속성을 설정할 때 양수 또는 0이 아닌 배열 길이를 지정했습니다.  이 오류는 음수이거나 숫자가 아닌\(`NaN`\) `Array` 개체의 **length** 속성에 값을 할당할 때 발생합니다.  [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]는 소수를 정수로 자동으로 변환합니다.  
  
### 이 오류를 해결하려면  
  
-   양의 정수를 length 속성에 할당하세요.  최대 정수 값\(약 40억\) 외에 배열 크기에 상한은 없습니다.  다음 예제에서는 **Array** 개체의 **length** 속성을 설정하는 올바른 방법을 보여 줍니다.  
  
    ```javascript  
    var my_array = new Array();  
    my_array.length = 99;  
    ```  
  
## 참고 항목  
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)