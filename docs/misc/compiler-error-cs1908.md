---
title: "컴파일러 오류 CS1908 | Microsoft Docs"
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
  - "CS1908"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1908"
ms.assetid: d7da31c2-48ef-4401-b885-3459b4d7f6f6
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1908
DefaultValue 특성에 대한 인수 형식이 매개 변수 형식과 일치해야 합니다.  
  
 이 오류는 <xref:System.ComponentModel.DefaultValueAttribute> 특성 값에 대해 잘못된 인수를 사용할 때 생성됩니다. 매개 변수 형식과 일치하는 값을 사용합니다.  
  
## 예제  
 다음 샘플에서는 CS1908을 생성합니다.  
  
```  
// CS1908.cs // compile with: /target:library using System.Runtime.InteropServices; public interface ISomeInterface { void Bad([Optional] [DefaultParameterValue("true")] bool b);   // CS1908 void Good([Optional] [DefaultParameterValue(true)] bool b);   // OK }  
```