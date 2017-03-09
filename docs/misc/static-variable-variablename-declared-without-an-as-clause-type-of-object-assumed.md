---
title: "&#39;As&#39; 절 없이 &#39;&lt;variablename&gt;&#39; 정적 변수가 선언되었습니다. &#39;Object&#39; 형식으로 간주합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc42111"
  - "bc42111"
helpviewer_keywords: 
  - "BC42111"
ms.assetid: ca6b625c-21a5-45f7-ac67-282f6993a724
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;As&#39; 절 없이 &#39;&lt;variablename&gt;&#39; 정적 변수가 선언되었습니다. &#39;Object&#39; 형식으로 간주합니다.
컴파일러는 정적 지역 변수의 데이터 형식을 유추하지 않습니다. 다음 예제에서 `Option Strict`을 `Off`로 설정하면 `Option Infer`가 `On` 또는 `Off`로 설정되었는지 여부에 관계없이 `m`의 형식은 `Object`가 됩니다. 지역 형식 유추는 적용되지 않습니다.  
  
```  
Sub Main() Static m = 10 End Sub  
```  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42111  
  
### 이 경고를 해결하려면  
  
-   정적 지역 변수의 데이터 형식을 지정합니다.  
  
     예를 들어 이전 예제에서 `m`을 `Integer` 형식으로 지정하려는 경우 선언에서 형식을 지정합니다.  
  
    ```  
    Sub Main() Static m As Integer = 10 End Sub  
  
    ```  
  
## 참고 항목  
 [Dim Statement](/dotnet/visual-basic/language-reference/statements/dim-statement)   
 [NOTINBUILD 방법: 변수의 수명 연장](http://msdn.microsoft.com/ko-kr/04e7c56c-1db0-4fe5-a678-859a39ec654b)   
 [Local Type Inference](/dotnet/visual-basic/programming-guide/language-features/variables/local-type-inference)   
 [Option Infer Statement](/dotnet/visual-basic/language-reference/statements/option-infer-statement)   
 [Static](/dotnet/visual-basic/language-reference/modifiers/static)