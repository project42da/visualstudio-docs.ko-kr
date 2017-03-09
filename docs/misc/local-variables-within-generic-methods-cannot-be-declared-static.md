---
title: "제네릭 메서드 내에 있는 지역 변수는 &#39;Static&#39;으로 선언할 수 없습니다. | Microsoft Docs"
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
  - "vbc32068"
  - "bc32068"
helpviewer_keywords: 
  - "BC32068"
ms.assetid: cb5df484-76f9-4092-9d19-f26ddcf1c035
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 제네릭 메서드 내에 있는 지역 변수는 &#39;Static&#39;으로 선언할 수 없습니다.
제네릭 프로시저 내의 지역 변수 선언에서 `Static`을 지정합니다.  
  
 Visual Basic 및 .NET Framework는 현재 정적 변수와 제네릭 프로시저의 조합을 지원하지 않습니다.  
  
 **오류 ID:** BC32068  
  
### 이 오류를 해결하려면  
  
-   변수 선언에서 `Static` 키워드를 제거합니다.  
  
## 참고 항목  
 [Static](/dotnet/visual-basic/language-reference/modifiers/static)   
 [NOTINBUILD 방법: 변수의 수명 연장](http://msdn.microsoft.com/ko-kr/04e7c56c-1db0-4fe5-a678-859a39ec654b)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)