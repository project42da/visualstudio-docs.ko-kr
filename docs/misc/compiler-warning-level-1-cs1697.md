---
title: "컴파일러 경고(수준 1) CS1697 | Microsoft Docs"
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
  - "CS1697"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1697"
ms.assetid: 0cd931b7-f358-4ff0-b441-27668645d7d5
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1697
'file name'에 대해 서로 다른 체크섬 값이 지정되었습니다.  
  
 지정된 파일에 대해 둘 이상의 체크섬을 지정했습니다. 디버거는 프로젝트에 동일한 이름을 가진 파일이 둘 이상 있을 경우 체크섬 값을 사용하여 디버그할 파일을 확인합니다. 대부분의 사용자는 이 오류가 발생하지 않지만 코드를 생성하는 응용 프로그램을 작성하는 경우 오류가 발생할 수 있습니다. 이 오류를 해결하려면 지정된 코드 파일에 대한 체크섬을 한 번만 생성하는지 확인합니다.