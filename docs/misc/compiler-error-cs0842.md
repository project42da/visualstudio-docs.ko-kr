---
title: "컴파일러 오류 CS0842 | Microsoft Docs"
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
  - "CS0842"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0842"
ms.assetid: 93a8b333-efc4-40c7-ae53-5264f721a74f
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0842
자동으로 구현된 속성은 StructLayout\(LayoutKind.Explicit\)으로 표시된 형식 내부에서 사용할 수 없습니다.  
  
 자동 구현 속성에 컴파일러에서 제공하는 지원 필드가 있는데 해당 필드가 소스 코드에 액세스할 수 없습니다. 따라서 <xref:System.Runtime.InteropServices.LayoutKind?displayProperty=fullName>와 호환되지 않습니다.  
  
### 이 오류를 해결하려면  
  
1.  속성을 접근자 본문을 제공하는 일반 속성으로 만듭니다.  
  
## 예제  
 다음 예제에서는 CS0842를 생성합니다.  
  
```  
// cs0842.cs using System; using System.Runtime.InteropServices; namespace TestNamespace { [StructLayout(LayoutKind.Explicit)] struct Str { public int Num // CS0842 { get; set; } static int Main() { return 1; } } }  
```