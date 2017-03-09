---
title: "컴파일러 오류 CS1917 | Microsoft Docs"
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
  - "CS1917"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1917"
ms.assetid: 05688706-e4b4-4273-9244-48cce1f7f9b9
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1917
형식이 'struct name'인 읽기 전용 필드 'name'의 멤버는 값 형식이므로 개체 이니셜라이저를 사용하여 할당할 수 없습니다.  
  
 값 형식인 읽기 전용 필드는 생성자에서만 할당할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   구조체를 클래스 형식으로 변경합니다.  
  
-   생성자를 사용하여 구조체를 초기화합니다.  
  
## 예제  
 다음 코드에서는 CS1917을 생성합니다.  
  
```  
// cs1917.cs class CS1917 { public struct TestStruct { public int i; } public class C { public readonly TestStruct str = new TestStruct(); public static int Main() { C c = new C { str = { i = 1 } }; // CS1917 return 0; } } }  
```