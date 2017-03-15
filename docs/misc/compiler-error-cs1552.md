---
title: "컴파일러 오류 CS1552 | Microsoft Docs"
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
  - "CS1552"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1552"
ms.assetid: 647af14d-249e-4f69-80a8-2c0d77fbb244
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1552
배열 형식 지정자인 \[\]는 매개 변수 이름 앞에 사용해야 합니다.  
  
 배열 형식 지정자의 위치가 배열 선언에서 변수 이름 뒤에 있습니다.  
  
## 예제  
 다음 샘플에서는 CS1552를 생성합니다.  
  
```  
// CS1552.cs public class C { public static void Main(string args[])   // CS1552 // try the following line instead // public static void Main(string [] args) { } }  
```