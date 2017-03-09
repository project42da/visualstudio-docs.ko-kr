---
title: "&#39;Object&#39; 형식의 인수를 사용하는 경우 &#39;FileGet&#39; 대신 &#39;FileGetObject&#39;를 사용합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 090b8088-895a-482a-9362-606596bac304
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Object&#39; 형식의 인수를 사용하는 경우 &#39;FileGet&#39; 대신 &#39;FileGetObject&#39;를 사용합니다.
`FileGet` 메서드는 `Object` 형식의 인수를 포함합니다. 모호성을 피하기 위해 `FileGet` 대신 `FileGetObject`를 사용해야 합니다.  
  
 `My.Computer.Filesystem`에서 제공하는 기능이 `FileGet` 또는 `FileGetObject`보다 사용하기 쉽고 성능이 뛰어납니다.  
  
### 이 오류를 해결하려면  
  
1.  `FileGet`을 `FileGetObject`로 바꿉니다.  
  
2.  `Object` 인수를 더 구체적인 형식으로 캐스트합니다.  
  
## 참고 항목  
 [빌드에 없음: FileGetObject 함수](http://msdn.microsoft.com/ko-kr/3eda786b-d1ee-4b44-9dd7-0ea6bff072c0)   
 [My.Computer.FileSystem Object](/dotnet/visual-basic/language-reference/objects/my-computer-filesystem-object)