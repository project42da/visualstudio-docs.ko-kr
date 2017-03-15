---
title: "컴파일러 오류 CS1910 | Microsoft Docs"
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
  - "CS1910"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1910"
ms.assetid: 0fef9727-e56f-451c-9255-ca4e5a26d7c6
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1910
'type' 형식의 인수는 DefaultValue 특성에 사용할 수 없습니다.  
  
 개체 형식인 매개 변수의 경우 <xref:System.Runtime.InteropServices.DefaultParameterValueAttribute>의 인수는 `null`, 정수 형식, 부동 소수점, `bool`, `string`, `enum` 또는 `char`여야 합니다. 인수는 <xref:System.Type> 형식 또는 배열 형식일 수 없습니다.  
  
## 예제  
 다음 샘플에서는 CS1910을 생성합니다.  
  
```  
// CS1910.cs // compile with: /target:library using System.Runtime.InteropServices; public interface MyI { void Test([DefaultParameterValue(typeof(object))] object o);   // CS1910 }  
```