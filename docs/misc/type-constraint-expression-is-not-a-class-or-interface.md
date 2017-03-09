---
title: "형식 제약 조건 &#39;&lt;expression&gt;&#39;이 클래스 또는 인터페이스가 아닙니다. | Microsoft Docs"
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
  - "bc32048"
  - "vbc32048"
helpviewer_keywords: 
  - "BC32048"
ms.assetid: 68811886-44ac-43e1-9315-b39857310033
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식 제약 조건 &#39;&lt;expression&gt;&#39;이 클래스 또는 인터페이스가 아닙니다.
제약 조건 목록에 형식 매개 변수에 대한 유효한 제약 조건을 나타내지 않는 식이 포함되어 있습니다.  
  
 제약 조건 목록은 형식 매개 변수에 전달되는 형식 인수에 대해 요구 사항을 적용합니다. 다음 요구 사항을 임의로 조합해서 지정할 수 있습니다.  
  
-   형식 인수는 하나 이상의 인터페이스를 구현해야 합니다.  
  
-   형식 인수는 최대 하나의 클래스에서 상속해야 합니다.  
  
-   형식 인수는 만드는 코드에서 액세스할 수 있는 매개 변수가 없는 생성자를 노출해야 합니다.  
  
-   형식 인수는 참조 형식이거나 값 형식이어야 합니다.  
  
 **오류 ID:** BC32048  
  
### 이 오류를 해결하려면  
  
-   식과 해당 요소의 철자가 맞는지 확인합니다.  
  
-   식이 앞의 요구 사항 목록에 맞지 않을 경우 제약 조건 목록에서 제거합니다.  
  
-   식이 인터페이스 또는 클래스를 참조하는 경우 컴파일러가 해당 인터페이스 또는 클래스에 액세스할 수 있는지 확인합니다. 해당 이름을 한정하거나 프로젝트에 대한 참조를 추가해야 할 수도 있습니다. 자세한 내용은 [NOTINBUILD: 여러 변수에 동일한 이름이 있는 경우 참조 확인](http://msdn.microsoft.com/ko-kr/9601e39f-1911-44e1-ace5-3f6e090408b9)에서 "프로젝트에 대한 참조"를 참조하세요.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Value Types and Reference Types](/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)   
 [NOTINBUILD 방법: 선언된 요소 이름 한정](http://msdn.microsoft.com/ko-kr/6bd112f5-df6f-42b8-9427-a9225bfcbaab)   
 [How to: Add and Remove Project References](http://msdn.microsoft.com/ko-kr/f51b784d-0bc8-4c19-a898-e560d5ed696b)