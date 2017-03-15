---
title: "컴파일러 경고(수준 1) CS1709 | Microsoft Docs"
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
  - "CS1709"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1709"
ms.assetid: e2bb1d30-4f30-4e10-82da-df1d3418454c
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1709
전처리기 지시문에 지정된 파일 이름이 비어 있습니다.  
  
 파일 이름을 포함하지만 해당 파일이 비어 있는 전처리기 지시문을 지정했습니다. 이 경고를 해결하려면 필요한 내용을 파일에 입력합니다.  
  
## 예제  
 다음 예제에서는 CS1709를 생성합니다.  
  
```  
// CS1709.cs class Test { static void Main() { #pragma checksum "" "{406EA660-64CF-4C82-B6F0-42D48172A799}" ""  // CS1709 } }  
```