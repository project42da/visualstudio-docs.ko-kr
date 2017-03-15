---
title: "&#39;&lt;typename&gt;&#39; 형식이 &#39;MustInherit&#39;으로 선언되어 있어 만들 수 없으므로 &#39;AddressOf&#39; 식을 &#39;&lt;typename&gt;&#39;으로 변환할 수 없습니다. | Microsoft Docs"
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
  - "vbc30939"
  - "bc30939"
helpviewer_keywords: 
  - "BC30939"
ms.assetid: e8edef15-0df5-46d7-aba6-89e26a2aa506
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 형식이 &#39;MustInherit&#39;으로 선언되어 있어 만들 수 없으므로 &#39;AddressOf&#39; 식을 &#39;&lt;typename&gt;&#39;으로 변환할 수 없습니다.
문에서 `AddressOf` 식을 기본 클래스로만 사용할 수 있고 인스턴스를 만드는 데는 사용할 수 없는 형식으로 변환하려고 합니다.  
  
 `AddressOf` 연산자는 특정 프로시저를 참조하는 프로시저 대리자 인스턴스를 만듭니다.  
  
 **오류 ID:** BC30939  
  
### 이 오류를 해결하려면  
  
-   `AddressOf` 식을 특정 대리자 형식에 할당합니다.  
  
## 참고 항목  
 [AddressOf Operator](/dotnet/visual-basic/language-reference/operators/addressof-operator)   
 [빌드에 없음: 대리자 및 AddressOf 연산자](http://msdn.microsoft.com/ko-kr/7b2ed932-8598-4355-b2f7-5cedb23ee86f)   
 [Delegates](/dotnet/visual-basic/programming-guide/language-features/delegates/delegates)