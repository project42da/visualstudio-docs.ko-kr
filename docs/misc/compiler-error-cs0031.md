---
title: "컴파일러 오류 CS0031 | Microsoft Docs"
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
  - "CS0031"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0031"
ms.assetid: 91f11ae9-9143-41f4-8002-5c38c8ee0651
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0031
'value' 상수 값을 'type'으로 변환할 수 없습니다. \(재정의하려면 ‘unchecked’ 구문 사용\)  
  
 해당 형식이 값을 저장할 수 없는 변수에 값을 할당하려고 시도했습니다. 자세한 내용은 [형식](/dotnet/csharp/programming-guide/types/index)을 참조하세요.  
  
 다음 샘플에서는 Checked와 Unchecked 컨텍스트 둘 다에서 CS0031을 생성합니다.  
  
```  
// CS0031.cs namespace CS0031 { public class a { public static void Main() { int num = (int)2147483648M; //CS0031 // Try using a larger numeric type instead: // long num = (long)2147483648M; //CS0031 const decimal d = -10M; // Decimal literal unchecked { const byte b = (byte)d; // CS0031 // For small values try using a signed byte instead: // const sbyte b = (sbyte)d; } } } }  
```  
  
## 참고 항목  
 [unchecked](/dotnet/csharp/language-reference/keywords/unchecked)