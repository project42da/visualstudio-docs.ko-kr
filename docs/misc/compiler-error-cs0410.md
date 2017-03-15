---
title: "컴파일러 오류 CS0410 | Microsoft Docs"
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
  - "CS0410"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0410"
ms.assetid: a8b11042-9119-465e-abf6-235cbc7b8db5
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0410
'method'에 대한 오버로드의 매개 변수 및 반환 형식이 모두 잘못되었습니다.  
  
 이 오류는 매개 변수 형식이 잘못된 함수를 사용하여 대리자를 인스턴스화하려는 경우 발생합니다. 대리자의 매개 변수 형식은 대리자에 할당 중인 함수와 일치해야 합니다.  
  
## 예제  
 다음 예제에서는 CS0410을 생성합니다.  
  
```  
// CS0410.cs // compile with: /langversion:ISO-1 class Test { delegate void D(double d ); static void F(int i) { } static void Main() { D d = new D(F);  // CS0410 } }  
```