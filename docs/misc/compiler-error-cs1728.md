---
title: "컴파일러 오류 CS1728 | Microsoft Docs"
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
  - "CS1728"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1728"
ms.assetid: 79a957db-ff56-4da6-9c17-8c5cffa1df5a
caps.latest.revision: 4
caps.handback.revision: 4
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1728
'member'는 'type'의 멤버이므로 대리자를 바인딩할 수 없습니다.  
  
 `Nullable` 형식의 멤버에 대리자를 바인딩할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 CS1728을 생성합니다.  
  
```  
// CS1728.cs class Test { delegate T GetT<T>(); delegate T GetT1<T>(T t); delegate bool E(object o); delegate int I(); delegate string S(); static void Main() { int? x = null; int? y = 5; GetT<int> d1 = x.GetValueOrDefault;   // CS1728 GetT<int> d2 = y.GetValueOrDefault;   // CS1728 GetT1<int> d3 = x.GetValueOrDefault;   // CS1728 GetT1<int> d4 = y.GetValueOrDefault;   // CS1728 } }  
```