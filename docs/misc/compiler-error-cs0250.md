---
title: "컴파일러 오류 CS0250 | Microsoft Docs"
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
  - "CS0250"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0250"
ms.assetid: a994f361-6287-4db0-9ce1-e293a8190049
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0250
기본 클래스 Finalize 메서드를 직접 호출하지 마세요. 이 메서드는 소멸자에서 자동으로 호출됩니다.  
  
 프로그램에서 기본 클래스 리소스의 정리를 시도할 수 없습니다.  
  
 자세한 내용은 [Finalize 메서드 및 소멸자](http://msdn.microsoft.com/ko-kr/fd376774-1643-499b-869e-9546a3aeea70)를 참조하세요.  
  
 다음 샘플에서는 CS0250을 생성합니다.  
  
```  
// CS0250.cs class B { } class C : B { ~C() { base.Finalize();   // CS0250 } public static void Main() { } }  
```