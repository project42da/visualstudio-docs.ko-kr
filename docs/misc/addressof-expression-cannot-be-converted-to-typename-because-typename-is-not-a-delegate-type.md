---
title: "&#39;&lt;typename&gt;&#39;이 대리자 형식이 아니므로 &#39;AddressOf&#39; 식을 &#39;AddressOf&#39;로 변환할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30581"
  - "bc30581"
helpviewer_keywords: 
  - "BC30581"
ms.assetid: 5db7589a-5456-4b3a-9d6b-93d9157f0484
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39;이 대리자 형식이 아니므로 &#39;AddressOf&#39; 식을 &#39;AddressOf&#39;로 변환할 수 없습니다.
문이 `AddressOf` 식을 대리자 형식이 아닌 형식으로 변환하려고 합니다.  
  
 `AddressOf` 연산자는 특정 프로시저를 참조하는 프로시저 대리자 인스턴스를 만듭니다.`AddressOf`는 대리자 생성자의 피연산자로 사용하거나 대리자의 형식이 컴파일러에 의해 결정될 수 있는 컨텍스트에서 사용할 수 있습니다.  
  
 **오류 ID:** BC30581  
  
### 이 오류를 해결하려면  
  
-   대상 유형을 대리자 형식으로 변경합니다.  
  
## 참고 항목  
 [AddressOf Operator](/dotnet/visual-basic/language-reference/operators/addressof-operator)   
 [빌드에 없음: 대리자 및 AddressOf 연산자](http://msdn.microsoft.com/ko-kr/7b2ed932-8598-4355-b2f7-5cedb23ee86f)