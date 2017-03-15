---
title: "컴파일러 경고(수준 1) CS0809 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0809"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0809"
ms.assetid: 2c2f0248-ab3a-4cdc-a1b0-2f0e05eac4c9
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS0809
사용되지 않는 'memberA' 멤버가 사용되는 'memberB' 멤버를 재정의합니다.  
  
 일반적으로 사용되지 않음으로 표시된 멤버는 사용되지 않음으로 표시되지 않은 멤버를 재정의하지 않아야 합니다. 이 경고는 [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)]에서 생성되지만 [!INCLUDE[vsprvslong](../code-quality/includes/vsprvslong_md.md)]에서는 생성되지 않습니다.  
  
### 이 오류를 해결하려면  
  
1.  재정의하는 멤버에서 `Obsolete` 특성을 제거하거나 기본 클래스 멤버에 추가합니다.  
  
## 예제  
  
```  
// CS0809.cs public class Base { public virtual void Test1() { } } public class C : Base { [System.Obsolete()] public override void Test1() // CS0809 { } }  
```