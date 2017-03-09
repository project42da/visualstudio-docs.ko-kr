---
title: "컴파일러 오류 CS1646 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1646"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1646"
ms.assetid: 5e4b0f1e-8de3-42b0-bde6-9f882677a409
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1646
축자 지정자 @ 뒤에는 키워드, 식별자 또는 문자열이 필요합니다.  
  
 축자 지정자 '@'의 사용에 대한 문자열 리터럴을 참조하세요. 축자 지정자는 문자열, 키워드 또는 식별자 앞에서만 허용됩니다. 이 오류를 해결하려면 @ 기호를 잘못된 위치에서 제거하거나 의도한 문자열, 키워드 또는 식별자를 추가합니다.  
  
 다음 샘플에서는 CS1646을 생성합니다.  
  
```  
// CS1646 class C { int i = @5;  // CS1646 // Try this line instead: // int i = 5; }  
```