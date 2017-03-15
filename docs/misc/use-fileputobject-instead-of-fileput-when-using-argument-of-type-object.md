---
title: "&#39;Object&#39; 형식의 인수를 사용하는 경우 &#39;FilePut&#39; 대신 &#39;FilePutObject&#39;를 사용하세요. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrUseFilePutObject"
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Object&#39; 형식의 인수를 사용하는 경우 &#39;FilePut&#39; 대신 &#39;FilePutObject&#39;를 사용하세요.
`FilePut` 메서드는 `Object` 형식의 인수를 포함합니다. 모호성을 피하기 위해 `FilePut` 대신 `FilePutObject`를 사용해야 합니다.  
  
### 이 오류를 해결하려면  
  
-   `FilePut`을 `FilePutObject`로 바꿉니다.  
  
-   `Object` 인수를 더 구체적인 형식으로 캐스트합니다.  
  
-   `My.Computer.FileSystem` 개체에서 사용할 수 있는 기능을 사용합니다.  
  
## 참고 항목  
 [빌드에 없음: FilePutObject 함수](http://msdn.microsoft.com/ko-kr/a0f52a1c-5ecc-4945-b18c-03147af61d6b)   
 [My.Computer.FileSystem Object](/dotnet/visual-basic/language-reference/objects/my-computer-filesystem-object)   
 [My.Computer.FileSystem.WriteAllBytes 메서드](http://msdn.microsoft.com/ko-kr/b1a24dc1-eac8-4e22-8ffa-cc3bacbaf826)