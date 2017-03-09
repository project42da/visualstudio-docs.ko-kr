---
title: "컴파일러 오류 CS0811 | Microsoft Docs"
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
  - "CS0811"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0811"
ms.assetid: 99f81ad3-684f-47aa-adb8-360e24901454
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0811
'name'의 정규화된 이름이 너무 길어서 디버그 정보에 사용할 수 없습니다. '\/debug' 옵션 없이 컴파일합니다.  
  
 디버그 정보에 변수 및 형식 이름에 대한 크기 제약 조건이 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  이름을 수정할 수 없는 경우 [\/debug](/dotnet/csharp/language-reference/compiler-options/debug-compiler-option) 옵션 없이 컴파일해야 합니다.  
  
## 예제  
 다음 코드에서는 CS0811을 생성합니다.  
  
```  
// cs0811.cs //Compile with: /debug using System; using System.Collections.Generic; namespace TestNamespace { using Long = List<List<List<List<List<List<List<List<List<List<List<List<List <List<List<List<List<List<List<List<List<List<List<List<List<List<List<List<int>>>>>>>>>>>>>>>>>>>>>>>>>>>>; // CS0811 class Test { static int Main() { return 1; } } }  
```