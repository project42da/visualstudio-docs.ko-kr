---
title: "컴파일러 경고(수준 1) CS1570 | Microsoft Docs"
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
  - "CS1570"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1570"
ms.assetid: a121d5c4-8b90-4cda-af5b-6ba8f23b2b1e
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1570
'construct'의 XML 주석에 잘못된 형식의 XML이 있습니다. 'reason'  
  
 [\/doc](/dotnet/csharp/language-reference/compiler-options/doc-compiler-option)를 사용하는 경우 소스 코드의 모든 주석이 XML에 있어야 합니다. XML 태그에 오류가 있으면 CS1570이 생성됩니다. 예:  
  
-   [\<exception\>](../Topic/%3Cexception%3E%20\(C%23%20Programming%20Guide\).md) 태그와 같이 **cref**에 문자열을 전달하는 경우 문자열을 큰따옴표로 묶어야 합니다.  
  
-   닫는 태그가 없는 [\<seealso\>](../Topic/%3Cseealso%3E%20\(C%23%20Programming%20Guide\).md)와 같은 태그를 사용하는 경우 닫는 꺾쇠 괄호 앞에 슬래시를 지정해야 합니다.  
  
-   설명 텍스트에 보다 큼 또는 보다 작음 기호를 사용해야 하는 경우 **&gt;** 또는 **&lt;**로 나타내야 합니다.  
  
-   [\<include\>](../Topic/%3Cinclude%3E%20\(C%23%20Programming%20Guide\).md) 태그의 파일 또는 경로 특성이 누락되었거나 잘못 구성되었습니다.  
  
 다음 샘플에서는 CS1570을 생성합니다.  
  
```  
// CS1570.cs // compile with: /W:1 namespace ns { // the following line generates CS1570 /// <summary> returns true if < 5 </summary> // try this instead // /// <summary> returns true if <5 </summary> public class MyClass { public static void Main () { } } }  
```