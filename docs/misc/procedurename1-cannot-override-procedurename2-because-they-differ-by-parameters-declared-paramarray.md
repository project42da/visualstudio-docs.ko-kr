---
title: "&#39;&lt;procedurename1&gt;&#39;은 &#39;&lt;procedurename2&gt;&#39;를 재정의할 수 없습니다. &#39;ParamArray&#39;로 선언된 매개 변수가 다릅니다. | Microsoft Docs"
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
  - "bc30906"
  - "vbc30906"
helpviewer_keywords: 
  - "BC30906"
ms.assetid: 12939030-732e-4c6d-8fe9-707b7532174b
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;procedurename1&gt;&#39;은 &#39;&lt;procedurename2&gt;&#39;를 재정의할 수 없습니다. &#39;ParamArray&#39;로 선언된 매개 변수가 다릅니다.
파생 클래스의 프로시저가 기본 클래스에서 이름이 같은 프로시저를 재정의하지만 매개 변수 목록이 서로 다릅니다.  
  
 상속된 클래스의 프로시저를 재정의하려면 재정의 프로시저의 매개 변수 목록, 액세스 수준 및 반환 형식\(있는 경우\)이 일치해야 합니다. 특히, [Optional](/dotnet/visual-basic/language-reference/modifiers/optional) 또는 [ParamArray](/dotnet/visual-basic/language-reference/modifiers/paramarray) 선언과 일치해야 합니다.  
  
 **오류 ID:** BC30906  
  
### 이 오류를 해결하려면  
  
-   프로시저를 재정의하려는 경우 매개 변수 목록을 기본 클래스 프로시저의 매개 변수 목록과 동일하게 만듭니다. 기본 클래스 프로시저에서 마지막 매개 변수가 `ParamArray`로 선언된 경우 재정의 프로시저에서 `ParamArray`로 선언합니다.  
  
-   기본 클래스 버전과 다른 매개 변수 목록을 사용하려는 경우 재정의할 수 없습니다. 대신 오버로드하는 것이 좋습니다. 자세한 내용은 [Procedure Overloading](/dotnet/visual-basic/programming-guide/language-features/procedures/procedure-overloading)을 참조하세요.  
  
## 참고 항목  
 [Overrides](/dotnet/visual-basic/language-reference/modifiers/overrides)   
 [빌드에 없음: 속성 및 메서드 재정의](http://msdn.microsoft.com/ko-kr/2167e8f5-1225-4b13-9ebd-02591ba90213)