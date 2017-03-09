---
title: "컴파일러 경고(수준 1) CS1687 | Microsoft Docs"
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
  - "CS1687"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1687"
ms.assetid: f65d184f-fa1d-45d7-be7d-f439f67bace4
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1687
소스 파일의 줄 수가 PDB에 표시할 수 있는 16,707,565줄을 초과했습니다. 디버그 정보가 올바르지 않을 수 있습니다.  
  
 PDB 및 디버거에 파일 크기에 대한 몇 가지 제한이 있습니다. 소스 파일이 너무 큰 경우 해당 제한을 벗어나서 디버거가 제대로 작동하지 않게 됩니다. 사용자는 `#line hidden`을 사용하여 해당 파일에 대한 디버그 정보를 내보내지 않거나 파일을 여러 개로 분할해 파일 크기를 줄일 수 있는 방법을 찾아야 합니다. 크기가 큰 클래스를 분할하기 위해 `partial` 키워드를 사용할 수도 있습니다.