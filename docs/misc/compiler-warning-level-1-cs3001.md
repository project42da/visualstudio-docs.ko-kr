---
title: "컴파일러 경고(수준 1) CS3001 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS3001"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3001"
ms.assetid: c4f3e247-5e47-4182-b415-c573fb1a152f
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS3001
인수 형식 'type'이 CLS 규격이 아닙니다.  
  
 [public](/dotnet/csharp/language-reference/keywords/public), [protected](/dotnet/csharp/language-reference/keywords/protected) 또는 `protected``internal` 메서드는 형식이 CLS\(공용 언어 사양\) 규격인 매개 변수를 사용해야 합니다. CLS 규격에 대한 자세한 내용은 [CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3) 및 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)를 참조하세요.  
  
## 예제  
 다음 예제에서는 CS3001을 생성합니다.  
  
```  
// CS3001.cs [assembly:System.CLSCompliant(true)] public class a { public void bad(ushort i)   // CS3001 { } private void OK(ushort i)   // OK, private method { } public static void Main() { } }  
```