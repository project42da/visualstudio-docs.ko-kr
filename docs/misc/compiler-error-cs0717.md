---
title: "컴파일러 오류 CS0717 | Microsoft Docs"
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
  - "CS0717"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0717"
ms.assetid: 1976e82a-d048-4f13-a95a-a7f4e3cd7038
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0717
'static class': 정적 클래스는 제약 조건으로 사용할 수 없습니다.  
  
 정적 클래스에는 인스턴스 멤버가 아닌 정적 멤버만 포함할 수 있으므로 정적 클래스를 확장할 수 없습니다. 확장할 수 없으므로 정적 클래스의 특수화인 형식이 존재할 수 없어 형식 매개 변수 및 제약 조건으로 사용할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 CS0717을 생성합니다.  
  
```  
// CS0717.cs public static class SC { public static void F() { } } public class G<T> where T : SC  // CS0717 { public static void Main() { } }  
```