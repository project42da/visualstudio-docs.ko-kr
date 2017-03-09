---
title: "컴파일러 경고(수준 1) CS0612 | Microsoft Docs"
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
  - "CS0612"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0612"
ms.assetid: 7695f3b7-ffef-43f7-83db-fc1a9e361f1a
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS0612
'member'는 사용되지 않습니다.  
  
 클래스 디자이너에서 [Obsolete](http://msdn.microsoft.com/ko-kr/05e99cd0-bda6-4f79-a890-1ca093b4b488) 특성으로 멤버를 표시했습니다. 이 경우 멤버가 이후 버전의 클래스에서 지원되지 않을 수 있습니다.  
  
 다음 샘플에서는 사용되지 않는 멤버에 액세스할 경우 CS0612가 발생하는 방식을 보여 줍니다.  
  
```  
// CS0612.cs // compile with: /W:1 using System; class MyClass { [Obsolete] public static void ObsoleteMethod() { } [Obsolete] public static int ObsoleteField; } class MainClass { static public void Main() { MyClass.ObsoleteMethod();    // CS0612 here: method is deprecated MyClass.ObsoleteField = 0;   // CS0612 here: field is deprecated } }  
```