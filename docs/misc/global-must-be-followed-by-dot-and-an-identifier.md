---
title: "&#39;Global&#39; 뒤에는 &#39;.&#39;과 식별자가 와야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36000"
  - "vbc36000"
helpviewer_keywords: 
  - "BC36000"
ms.assetid: 0007d7b4-54a2-4f09-904c-d5ad60a55f8e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Global&#39; 뒤에는 &#39;.&#39;과 식별자가 와야 합니다.
[Global \- 삭제](http://msdn.microsoft.com/ko-kr/18c8ba14-40f6-4978-8096-6a5852324635) 키워드가 네임스페이스 액세스 이외의 컨텍스트에서 나타납니다.  
  
 `Global`의 목적은 코드가 루트 수준 네임스페이스를 차단한 네임스페이스 구조체 내에서 루트 수준 네임스페이스에 액세스할 수 있도록 하는 것입니다.  
  
 **오류 ID:** BC36000  
  
### 이 오류를 해결하려면  
  
-   루트 수준 네임스페이스에 액세스하려면 `Global` 키워드와 마침표\(`.`\) 뒤에 지정합니다.  
  
    ```  
    Dim keyInfo As Global.System.ConsoleKeyInfo  
    ```  
  
-   루트 수준 네임스페이스에 액세스하지 않으려면 `Global` 키워드를 제거합니다.  
  
## 참고 항목  
 [Global \- 삭제](http://msdn.microsoft.com/ko-kr/18c8ba14-40f6-4978-8096-6a5852324635)