---
title: "&#39;&lt;typename&gt;&#39;에 있는 적절한 서명이 포함된 액세스 가능한 &#39;Main&#39; 메서드는 모두 제네릭이거나 제네릭 형식에 중첩되어 있으므로 시작 메서드일 수 없습니다. | Microsoft Docs"
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
  - "vbc30796"
  - "BC30796"
helpviewer_keywords: 
  - "BC30796"
ms.assetid: 606b3629-5a92-4c79-ace2-a530cab8c978
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39;에 있는 적절한 서명이 포함된 액세스 가능한 &#39;Main&#39; 메서드는 모두 제네릭이거나 제네릭 형식에 중첩되어 있으므로 시작 메서드일 수 없습니다.
클래스, 모듈 또는 구조체는 프로젝트 시작 프로시저로 정규화되는 `Main` 프로시저가 없습니다.  
  
 Visual Basic은 프로젝트에 대한 시작 프로시저가 형식 인수에 종속되지 않아야 합니다. 따라서 제네릭이 아니거나 제네릭 형식에 포함되지 않는 하나 이상의 `Main` 프로시저에 액세스할 수 있어야 합니다.  
  
 **오류 ID:** BC30796  
  
### 이 오류를 해결하려면  
  
-   제네릭이 아니거나 제네릭 형식에 포함되지 않도록 하나 이상의 `Main` 프로시저를 정의합니다.  
  
     또는  
  
-   프로젝트의 **속성** 페이지에서 **시작 폼** 또는 **시작 개체**에 대해 다른 양식 또는 모듈을 지정합니다.  
  
## 참고 항목  
 [NIB 방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [NIB: Visual Basic 버전의 Hello, World](http://msdn.microsoft.com/ko-kr/9d030b60-e148-4366-a462-69532f02294c)