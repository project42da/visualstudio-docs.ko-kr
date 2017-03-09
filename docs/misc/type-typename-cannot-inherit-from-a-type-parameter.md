---
title: "&#39;&lt;typename&gt;&#39; 형식은 형식 매개 변수에서 상속할 수 없습니다. | Microsoft Docs"
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
  - "bc32055"
  - "vbc32055"
helpviewer_keywords: 
  - "BC32055"
ms.assetid: 97af7cad-6e40-41e3-892d-1fbcbd86356d
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 형식은 형식 매개 변수에서 상속할 수 없습니다.
클래스 또는 인터페이스에 제네릭 형식 매개 변수를 지정하는 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)이 포함되어 있습니다.  
  
 형식은 아직 정의되지 않은 형식에서 상속할 수 없습니다. 상속에는 기본 클래스의 멤버를 다시 사용할 수 있는 기능이 포함되므로 이러한 멤버가 정의되어 있어야 합니다. 제네릭 형식 매개 변수는 형식 인수가 제공하는 특정 형식으로 대체되어야 하는 자리 표시자입니다. 따라서 형식은 자리 표시자에서 상속할 수 없습니다.  
  
 **오류 ID:** BC32055  
  
### 이 오류를 해결하려면  
  
-   상속 형식이 다른 형식에서 상속해야 하는 경우 형식 매개 변수 대신 특정 형식을 사용합니다.  
  
-   기본 형식이 제네릭 형식 매개 변수로 표현되어야 하는 경우 다른 형식이 상속할 수 없습니다.[Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)을 제거합니다.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic의 상속](http://msdn.microsoft.com/ko-kr/e5e6e240-ed31-4657-820c-079b7c79313c)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)