---
title: "컴파일러 오류 CS0117 | Microsoft Docs"
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
  - "CS0117"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0117"
ms.assetid: 2cbc7e66-75d6-4817-85ae-89c4b9adfded
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0117
'type'에 'identifier'에 대한 정의가 없습니다.  
  
-   이 오류는 멤버가 데이터 형식에 대해 존재하지 않는 상태에서 해당 멤버에 대해 참조가 만들어진 일부 경우 발생합니다.  
  
## 예제  
 다음 샘플에서는 CS0117을 생성합니다.  
  
```  
// CS0117.cs public class BaseClass { } public class base021 : BaseClass { public void TestInt() { int i = base.someMember; //CS0117 } public static int Main() { return 1; } }  
```