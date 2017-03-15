---
title: "컴파일러 경고(수준 1) CS3023 | Microsoft Docs"
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
  - "CS3023"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3023"
ms.assetid: fd7782f9-f18a-4ce8-843b-95bf19b54317
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS3023
CLSCompliant 특성을 반환 형식에 적용하면 의미가 없습니다.  대신 이 특성을 메서드에 배치해 봅니다.  
  
 CLS 규격 규칙이 메서드 및 형식 선언에 적용되므로 함수 반환 형식이 CLS 규격에 대해 확인되지 않습니다.  
  
## 예제  
 다음 예제에서는 CS3023 경고를 생성합니다.  
  
```  
// C3023.cs [assembly:System.CLSCompliant(true)] public class Test { [return:System.CLSCompliant(true)]  // CS3023 // Try this instead: // [method:System.CLSCompliant(true)] public static int Main() { return 0; } }  
```