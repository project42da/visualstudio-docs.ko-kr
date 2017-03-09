---
title: "&#39;&lt;delegatename&gt;&#39;:&lt;suberrorlist&gt; 대리자와 호환되는 서명을 가진 액세스 가능한 &#39;&lt;procedurename&gt;&#39; 메서드가 없습니다. | Microsoft Docs"
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
  - "bc30950"
  - "vbc30950"
helpviewer_keywords: 
  - "BC30950"
ms.assetid: c1938099-2c03-491e-b599-d0c43bf94baf
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;delegatename&gt;&#39;:&lt;suberrorlist&gt; 대리자와 호환되는 서명을 가진 액세스 가능한 &#39;&lt;procedurename&gt;&#39; 메서드가 없습니다.
대입문이 대리자 변수에 프로시저의 주소를 대리자 변수에 할당하지만 컴파일러에서 일치하는 서명이 있는 프로시저 버전을 찾을 수 없습니다.  
  
 코드가 프로시저 주소를 사용하는 경우 컴파일러에서 대리자의 매개 변수 목록과 일치하는 매개 변수 목록을 사용하여 해당 프로시저 버전을 찾으려고 합니다. 여러 오버로드된 버전에서 프로시저가 정의된 경우 컴파일러는 서명이 일치하는 단일 버전을 찾으려고 합니다. 자세한 내용은 [Overload Resolution](/dotnet/visual-basic/programming-guide/language-features/procedures/overload-resolution)을 참조하세요.  
  
 컴파일러가 일치하는 서명이 있는 프로시저 버전을 찾을 수 없는 경우 이 오류가 발생합니다. 예를 들어 프로시저 또는 대리자 중 하나가 제네릭이고 여기에 다른 서명과 일치하지 않는 서명을 제공하는 형식 인수가 전달되는 경우 이 오류가 발생할 수 있습니다.  
  
 **오류 ID:** BC30950  
  
### 이 오류를 해결하려면  
  
1.  프로시저 또는 대리자가 일치하는 매개 변수 목록을 갖도록 프로시저 또는 대리자를 다시 정의합니다.  
  
     또는  
  
     프로시저의 매개 변수 목록과 일치하는 매개 변수 목록을 사용하여 새 대리자를 정의하거나 대리자의 매개 변수 목록과 일치하는 매개 변수 목록을 사용하여 새 프로시저를 정의합니다.  
  
2.  프로시저 또는 대리자 중 하나가 제네릭이면 여기에 해당 서명을 다른 서명과 일치시키는 형식 인수를 전달합니다.  
  
## 참고 항목  
 [AddressOf Operator](/dotnet/visual-basic/language-reference/operators/addressof-operator)   
 [Delegate Statement](/dotnet/visual-basic/language-reference/statements/delegate-statement)   
 [빌드에 없음: 대리자 및 AddressOf 연산자](http://msdn.microsoft.com/ko-kr/7b2ed932-8598-4355-b2f7-5cedb23ee86f)   
 [Overload Resolution](/dotnet/visual-basic/programming-guide/language-features/procedures/overload-resolution)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)