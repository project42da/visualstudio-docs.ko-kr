---
title: "&#39;&lt;keyword&gt;&#39;는 모듈 안에서 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc32001"
  - "bc32001"
helpviewer_keywords: 
  - "BC32001"
ms.assetid: b00757ac-5652-460d-9d2c-11b264d7ec7f
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;keyword&gt;&#39;는 모듈 안에서 사용할 수 없습니다.
`Me` 또는 `MyBase`와 같이 클래스 인스턴스에 관련된 키워드가 모듈 내에서 사용됩니다. 모듈에는 상속 또는 인스턴스가 없습니다.  
  
 **오류 ID:** BC32001  
  
### 이 오류를 해결하려면  
  
-   해당 키워드를 사용하는 코드가 클래스 인스턴스와 관련되는 경우 클래스 구현으로 이동합니다.  
  
-   해당 키워드를 사용하는 코드가 모듈에 적용되는 경우 잘못된 키워드를 제거합니다.  
  
## 참고 항목  
 [Me](http://msdn.microsoft.com/ko-kr/a65973c7-cf06-4547-9b25-9fba885525c2)   
 [MyBase \- 삭제](http://msdn.microsoft.com/ko-kr/52491d06-6451-4f6f-9aa6-8fab59bbc2b9)