---
title: "컴파일러 경고(수준 1) CS0626 | Microsoft Docs"
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
  - "CS0626"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0626"
ms.assetid: 2cd5061c-80e7-48d3-8d14-be7fc642af94
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS0626
메서드, 연산자 또는 접근자 'method'가 external로 표시되었지만 특성이 없습니다. DllImport 특성을 추가하여 외부 구현을 지정하는 것이 좋습니다.  
  
 `extern`으로 표시된 메서드는 또한 특성\(예: [DllImport](frlrfSystemRuntimeInteropServicesDllImportAttributeClassTopic) 특성\)으로도 표시되어야 합니다.  
  
 특성은 메서드가 구현되는 위치를 지정합니다. 런타임에 프로그램에서 이 정보가 필요합니다.  
  
 다음 샘플에서는 CS0626을 생성합니다.  
  
```  
// CS0626.cs // compile with: /warnaserror using System.Runtime.InteropServices; public class MyClass { static extern public void M(); // CS0626 // try the following line // [DllImport("mydll.dll")] static extern public void M(); public static void Main() { } }  
```