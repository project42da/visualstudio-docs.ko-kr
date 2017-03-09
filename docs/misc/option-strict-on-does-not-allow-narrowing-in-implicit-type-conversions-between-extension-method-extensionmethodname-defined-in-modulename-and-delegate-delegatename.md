---
title: "Option Strict On에서는 &#39;&lt;modulename&gt;&#39;에 정의된 확장 메서드 &#39;&lt;extensionmethodname&gt;&#39;과 &#39;&lt;delegatename&gt;&#39; 대리자 사이의 암시적 형식 변환에 축소 변환을 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc36709"
  - "vbc36709"
helpviewer_keywords: 
  - "BC36709"
ms.assetid: 95d8c833-3525-411b-98e8-b7d3f61f75c9
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On에서는 &#39;&lt;modulename&gt;&#39;에 정의된 확장 메서드 &#39;&lt;extensionmethodname&gt;&#39;과 &#39;&lt;delegatename&gt;&#39; 대리자 사이의 암시적 형식 변환에 축소 변환을 사용할 수 없습니다.
`Option Strict`이 설정되면 대리자의 매개 변수 데이터 형식에서 해당 대리자 형식의 변수에 할당된 확장 메서드의 해당 변수로 축소 변환을 사용할 수 없습니다. 대리자 매개 변수의 데이터 형식을 확장 메서드의 데이터 형식으로 확장해야 합니다.  
  
 **오류 ID:** BC36709  
  
### 이 오류를 해결하려면  
  
-   필요한 확대 관계가 존재하도록 대리자 또는 확장 메서드에서 매개 변수의 데이터 형식을 변경합니다.  
  
## 참고 항목  
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [Relaxed Delegate Conversion](/dotnet/visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion)   
 [Delegates](/dotnet/visual-basic/programming-guide/language-features/delegates/delegates)   
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)   
 [빌드에 없음: 대리자 및 AddressOf 연산자](http://msdn.microsoft.com/ko-kr/7b2ed932-8598-4355-b2f7-5cedb23ee86f)