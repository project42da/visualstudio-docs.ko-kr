---
title: "컴파일러 오류 CS0509 | Microsoft Docs"
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
  - "CS0509"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0509"
ms.assetid: dc113e03-7a01-489b-b886-51ee056fc96a
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0509
'class1': sealed 형식 'class2'에서 파생될 수 없습니다.  
  
 [sealed](/dotnet/csharp/language-reference/keywords/sealed) 클래스는 [기본](/dotnet/csharp/language-reference/keywords/base) 클래스로 사용할 수 없습니다. 구조체는 기본적으로 sealed입니다.  
  
 다음 샘플에서는 CS0509를 생성합니다.  
  
```  
// CS0509.cs // compile with: /target:library sealed public class clx {} public class cly : clx {}   // CS0509  
```