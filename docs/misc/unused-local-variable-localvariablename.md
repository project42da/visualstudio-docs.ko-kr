---
title: "사용되지 않는 지역 변수: &#39;&lt;localvariablename&gt;&#39; | Microsoft Docs"
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
  - "vbc42024"
  - "BC42024"
helpviewer_keywords: 
  - "BC42024"
ms.assetid: 749b1315-0f85-4f7e-b68b-8cc4346c502b
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 사용되지 않는 지역 변수: &#39;&lt;localvariablename&gt;&#39;
프로시저의 지역 변수가 선언되었지만 사용되지 않았습니다.  
  
 프로시저의 지역 변수 간에 철자 오류가 있을 수 있습니다. 이 변수가 실제로 다른 문에서 다른 철자로 사용되는 경우 컴파일러에 두 개의 다른 변수로 표시됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42024  
  
### 이 오류를 해결하려면  
  
1.  프로시저 내의 지역 변수 간에 맞춤법 오류를 확인합니다. 대\/소문자가 구분되지 않습니다.`ABC` 및 `abc`는 동일한 변수를 가리키는 것으로 간주됩니다.  
  
2.  철자가 잘못된 경우 이 변수의 선언을 제거하거나 프로시저의 다른 문에서 사용합니다.  
  
## 참고 항목  
 [Declared Element Names](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names)   
 [Dim Statement](/dotnet/visual-basic/language-reference/statements/dim-statement)