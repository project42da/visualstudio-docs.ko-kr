---
title: "&#39;&lt;procedurename1&gt;&#39;은 이 컨텍스트에서 액세스할 수 없으므로 &#39;&lt;procedurename2&gt;&#39;를 재정의할 수 없습니다. | Microsoft Docs"
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
  - "bc31417"
  - "vbc31417"
helpviewer_keywords: 
  - "BC31417"
ms.assetid: 1a36acbf-cead-43a0-b12f-f52f94d09124
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;procedurename1&gt;&#39;은 이 컨텍스트에서 액세스할 수 없으므로 &#39;&lt;procedurename2&gt;&#39;를 재정의할 수 없습니다.
프로시저 또는 속성이 재정의하는 프로시저 또는 속성에 의한 액세스를 금지하는 액세스 수준으로 프로시저 또는 속성을 재정의합니다.  
  
 예를 들어 한 어셈블리에서 프로시저가 `Friend`로 선언되면 해당 어셈블리 밖에서 액세스할 수 없습니다. 동일한 프로젝트에서 다른 어셈블리의 프로시저가 `Friend` 프로시저를 재정의하려는 경우 재정의하기 위해 액세스할 수 없습니다.  
  
 **오류 ID:** BC31417  
  
### 이 오류를 해결하려면  
  
-   재정의하는 프로시저 또는 속성을 재정의할 프로시저 또는 속성과 같은 어셈블리로 이동합니다.  
  
     또는  
  
-   `Overrides` 키워드를 제거합니다.  
  
## 참고 항목  
 [Access Levels in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/access-levels)   
 [Overrides](/dotnet/visual-basic/language-reference/modifiers/overrides)   
 [빌드에 없음: 속성 및 메서드 재정의](http://msdn.microsoft.com/ko-kr/2167e8f5-1225-4b13-9ebd-02591ba90213)