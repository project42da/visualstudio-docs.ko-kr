---
title: "컴파일러 오류 CS0720 | Microsoft Docs"
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
  - "CS0720"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0720"
ms.assetid: 1a8e7613-6bfb-4178-a8b4-f4591316c0b8
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0720
'static class': 정적 클래스에는 인덱서를 선언할 수 없습니다.  
  
 인덱서는 인스턴스에서만 사용할 수 있고 정적 형식의 인스턴스를 만들 수 없기 때문에 정적 클래스에서는 의미가 없습니다.  
  
## 예제  
 다음 샘플에서는 CS0720을 생성합니다.  
  
```  
// CS0720.cs public static class Test { public int this[int index]  // CS0720 { get { return 1; } set {} } static void Main() {} }  
```