---
title: "컴파일러 오류 CS1724 | Microsoft Docs"
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
  - "CS1724"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1724"
ms.assetid: f25ec28e-c20b-457d-afc2-284494e69dad
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1724
'System.Runtime.InteropServices.DefaultCharSetAttribute'에 인수로 지정한 값이 잘못되었습니다.  
  
 이 오류는 <xref:System.Runtime.InteropServices.DefaultCharSetAttribute> 클래스에 대한 잘못된 인수에 의해 생성됩니다.  
  
## 예제  
 다음 예제에서는 CS1724를 생성합니다.  
  
```  
// CS1724.cs using System.Runtime.InteropServices; // To resolve, replace 42 with a valid CharSet value. [module:DefaultCharSetAttribute((CharSet)42)]   // CS1724 class C { [DllImport("F.Dll")] extern static void FW1Named(); static void Main() {} }  
```