---
title: "컴파일러 오류 CS2036 | Microsoft Docs"
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
  - "CS2036"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2036"
ms.assetid: 44b73be4-b792-4735-bdbd-bd757ab22683
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS2036
\/pdb 옵션은 \/debug 옵션과 함께 사용해야 합니다.  
  
 프로그램 데이터베이스 파일은 디버그 빌드에 대해서만 생성됩니다. 따라서 **\/pdb** 옵션은 일반 정품 빌드에서 의미가 없습니다.  
  
### 이 오류를 해결하려면  
  
-   **\/debug** 컴파일러 옵션을 추가합니다.  
  
-   **\/pdb** 컴파일러 옵션을 제거합니다.  
  
## 예제  
 다음 예제에서 **\/pdb** 옵션을 사용하여 컴파일할 때는 CS2036이 생성되지만 \/debug 옵션을 사용할 때는 생성되지 않습니다.  
  
```  
// cs2036.cs // Compile with: /pdb // CS2036 class Test { public static int Main() { return 1; } }  
```  
  
## 참고 항목  
 [\/pdb \(Specify Debug Symbol File\)](/dotnet/csharp/language-reference/compiler-options/pdb-compiler-option)   
 [\/debug \(Emit Debugging Information\)](/dotnet/csharp/language-reference/compiler-options/debug-compiler-option)