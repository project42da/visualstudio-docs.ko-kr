---
title: "컴파일러 오류 CS2005 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS2005"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2005"
ms.assetid: 03535d2a-ae30-4272-ab45-e277df5ee8e1
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS2005
'option' 옵션에 대한 파일 사양이 없습니다.  
  
 [컴파일러 옵션](/dotnet/csharp/language-reference/compiler-options/index)을 부분적으로만 지정했습니다.  
  
 예를 들어 [\/recurse](/dotnet/csharp/language-reference/compiler-options/recurse-compiler-option)를 사용하는 경우 검색할 파일을 지정해야 합니다. **\/recurse:***filename***.cs**.  
  
## 예제  
 다음 샘플에서는 CS2005를 생성합니다.  
  
```  
// CS2005.cs // compile with: /recurse: // CS2005 expected class x { public static void Main() {} }  
```