---
title: "컴파일러 경고(수준 1) CS0824 | Microsoft Docs"
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
  - "CS0824"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0824"
ms.assetid: ad643bb7-51b2-455b-a9f3-2bd4588d2c5d
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS0824
'name' 생성자가 external로 표시되었습니다.  
  
 생성자가 extern으로 표시될 수 있습니다. 그러나 컴파일러는 생성자가 실제로 존재하는지 확인할 수 없습니다. 따라서 경고가 생성됩니다.  
  
### 이 경고를 제거하려면  
  
1.  Pragma 경고 지시문을 사용하여 무시합니다.  
  
2.  생성자를 형식 안으로 이동합니다.  
  
## 예제  
 다음 코드에서는 CS0824를 생성합니다.  
  
```  
// cs0824.cs public class C { extern C(); // CS0824 public static int Main() { return 1; } }  
```  
  
## 참고 항목  
 [extern](/dotnet/csharp/language-reference/keywords/extern)   
 [\#pragma warning](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning)