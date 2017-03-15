---
title: "&#39;&lt;typeName&gt;&#39;에서 정의된 &#39;&lt;methodName&gt;&#39; 확장 메서드에 대한 형식 인수를 &#39;&lt;delagateName&gt;&#39; 대리자에서 유추할 수 없습니다. | Microsoft Docs"
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
  - "bc36581"
  - "vbc36581"
helpviewer_keywords: 
  - "BC36581"
ms.assetid: 2bb9ca8d-7293-40e9-9285-e20b8254b3af
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typeName&gt;&#39;에서 정의된 &#39;&lt;methodName&gt;&#39; 확장 메서드에 대한 형식 인수를 &#39;&lt;delagateName&gt;&#39; 대리자에서 유추할 수 없습니다.
대입문이 `AddressOf`를 사용하여 대리자에 제네릭 확장 메서드의 주소를 할당하지만 형식 인수를 확장 메서드에 제공하지 않습니다.  
  
 일반적으로 제네릭 메서드를 호출할 때 제네릭 메서드가 정의하는 각 형식 매개 변수에 대해 형식 인수를 제공합니다. 형식 인수를 제공하지 않으면 컴파일러에서 형식 매개 변수에 전달될 형식을 유추하려고 합니다. 컨텍스트에서 컴파일러가 형식을 유추하도록 정보를 충분히 제공하지 않으면 오류가 생성됩니다.  
  
 **오류 ID:** BC36581  
  
### 이 오류를 해결하려면  
  
-   `AddressOf` 식에서 확장 메서드에 대한 형식 인수를 지정합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [AddressOf Operator](/dotnet/visual-basic/language-reference/operators/addressof-operator)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)   
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)