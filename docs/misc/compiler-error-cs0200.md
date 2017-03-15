---
title: "컴파일러 오류 CS0200 | Microsoft Docs"
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
  - "CS0200"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0200"
ms.assetid: 1990704a-edfa-4dbd-8477-d9c7aae58c96
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0200
'property' 속성 또는 인덱서는 읽기 전용이므로 할당할 수 없습니다.  
  
 [property](/dotnet/csharp/programming-guide/classes-and-structs/using-properties)에 값을 할당하려고 했지만 property에 set 접근자가 없습니다. set 접근자를 추가하여 오류를 해결합니다. 자세한 내용은 [방법: 읽기\/쓰기 속성 선언 및 사용](../Topic/How%20to:%20Declare%20and%20Use%20Read%20Write%20Properties%20\(C%23%20Programming%20Guide\).md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0200을 생성합니다.  
  
```  
// CS0200.cs public class MainClass { // private int _mi; int I { get { return 1; } // uncomment the set accessor and declaration for _mi /* set { _mi = value; } */ } public static void Main () { MainClass II = new MainClass(); II.I = 9;   // CS0200 } }  
```