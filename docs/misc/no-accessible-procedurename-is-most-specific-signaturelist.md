---
title: "액세스할 수 없는 &#39;&lt;procedurename&gt;&#39;은 &lt;signaturelist&gt;에만 한정됩니다. | Microsoft Docs"
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
  - "vbc30794"
  - "BC30794"
helpviewer_keywords: 
  - "BC30794"
ms.assetid: 51d54cbb-b530-4661-9952-5ccc17e4220b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 액세스할 수 없는 &#39;&lt;procedurename&gt;&#39;은 &lt;signaturelist&gt;에만 한정됩니다.
대입문이 대리자 변수에 오버로드된 프로시저의 주소를 할당하지만 컴파일러에서 오버로드된 버전을 확인할 수 없습니다.  
  
 코드가 여러 오버로드 버전에서 정의된 프로시저의 주소를 사용하는 경우 컴파일러에서 사용할 오버로드를 결정해야 합니다. 대리자 매개 변수 목록과 일치하는 매개 변수 목록으로 단일 버전을 찾습니다. 자세한 내용은 [Overload Resolution](/dotnet/visual-basic/programming-guide/language-features/procedures/overload-resolution)을 참조하세요.  
  
 컴파일러가 일치하는 서명이 있는 프로시저 버전을 둘 이상 찾을 경우 이 오류가 발생합니다. 예를 들어 오버로드 중 하나가 제네릭인데 다른 오버로드와 동일한 서명을 제공하는 형식 인수가 전달된 경우 이 오류가 발생할 수 있습니다.  
  
 **오류 ID:** BC30794  
  
### 이 오류를 해결하려면  
  
-   다른 오버로드와 같은 서명을 가진 제네릭 오버로드로 인해 충돌이 발생한 경우 해당 제네릭 오버로드로 전달된 형식 인수를 변경합니다.  
  
## 참고 항목  
 [AddressOf Operator](/dotnet/visual-basic/language-reference/operators/addressof-operator)   
 [Delegate Statement](/dotnet/visual-basic/language-reference/statements/delegate-statement)   
 [빌드에 없음: 대리자 및 AddressOf 연산자](http://msdn.microsoft.com/ko-kr/7b2ed932-8598-4355-b2f7-5cedb23ee86f)   
 [Overload Resolution](/dotnet/visual-basic/programming-guide/language-features/procedures/overload-resolution)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)