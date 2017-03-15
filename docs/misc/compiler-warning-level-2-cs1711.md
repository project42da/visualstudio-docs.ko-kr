---
title: "컴파일러 경고(수준 2) CS1711 | Microsoft Docs"
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
  - "CS1711"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1711"
ms.assetid: 0021275a-43eb-4295-929e-bb3283577a11
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS1711
'type'의 XML 주석에 'parameter'에 대한 형식 매개 변수 태그가 있지만 해당 이름을 가진 형식 매개 변수가 없습니다.  
  
 제네릭 형식의 설명서에 잘못된 이름을 가진 형식 매개 변수에 대한 태그가 포함되어 있습니다.  
  
## 예제  
 다음 코드는 CS1711 경고를 생성합니다.  
  
```  
// cs1711.cs // compile with: /doc:cs1711.xml // CS1711 expected using System; ///<typeparam name="WrongName">can be an int</typeparam> class CMain { public static void Main() { } }  
```