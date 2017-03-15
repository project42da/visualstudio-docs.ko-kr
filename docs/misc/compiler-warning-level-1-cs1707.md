---
title: "컴파일러 경고(수준 1) CS1707 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1707"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1707"
ms.assetid: 47b6096e-4e4b-4057-b9d7-4a096139267a
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1707
새 언어 규칙 때문에 'DelegateName' 대리자가 'MethodName2' 대신 'MethodName1'에 바인딩되었습니다.  
  
 C\# 2.0에서는 대리자를 메서드에 바인딩하기 위한 새로운 규칙을 구현합니다. 이전에는 확인되지 않았던 추가 정보가 고려됩니다. 이 경고는 이제 대리자가 이전에 바인딩된 것과 다른 메서드의 오버로드에 바인딩되어 있음을 나타냅니다. 대리자가 실제로 'MethodName2' 대신 'MethodName1'에 바인딩되어야 하는지 확인할 수도 있습니다.  
  
 컴파일러에서 대리자를 바인딩할 메서드를 확인하는 방법에 대한 자세한 내용은 [대리자의 가변성 사용](../Topic/Using%20Variance%20in%20Delegates%20\(C%23%20and%20Visual%20Basic\).md)을 참조하세요.