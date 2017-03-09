---
title: "구조체에 선언된 메서드에는 &#39;Handles&#39; 절을 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc30728"
  - "bc30728"
helpviewer_keywords: 
  - "BC30728"
ms.assetid: 64c70bb5-3696-4865-8194-328394c2b4b1
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 구조체에 선언된 메서드에는 &#39;Handles&#39; 절을 사용할 수 없습니다.
구조체 메서드는 `Handles` 키워드를 사용하여 이벤트를 처리할 수 없습니다.  
  
 **오류 ID:** BC30728  
  
### 이 오류를 해결하려면  
  
-   구조체를 클래스로 다시 디자인하는 것이 좋습니다.  
  
     구조체가 인터페이스에 정의된 이벤트 처리기를 구현하는 경우 `AddHandler`를 사용하여 이벤트를 이벤트 처리기에 연결할 수 있습니다.  
  
## 참고 항목  
 [Structures and Classes](/dotnet/visual-basic/programming-guide/language-features/data-types/structures-and-classes)   
 [빌드에 없음: 클래스: 개체에 대한 청사진](http://msdn.microsoft.com/ko-kr/2c86373d-0333-4616-a7d8-4790c4e89f7b)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)   
 [빌드에 없음: AddHandler 및 RemoveHandler](http://msdn.microsoft.com/ko-kr/a7a24bd2-519a-46fe-8a2c-2b9df2ca28ef)