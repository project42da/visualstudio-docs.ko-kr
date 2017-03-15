---
title: "컴파일러 오류 CS0003 | Microsoft Docs"
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
  - "CS0003"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0003"
ms.assetid: 6aee4b0e-e24f-47b5-8281-ca4c7ee8a3cf
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0003
메모리 부족  
  
 컴파일러에서 컴파일을 완료하는 데 충분한 가상 메모리를 할당할 수 없습니다. 불필요한 응용 프로그램을 모두 닫고 다시 컴파일합니다.  
  
 또한 페이지 파일 크기를 늘리고 사용 가능한 디스크 공간이 있는지 확인하는 것이 좋습니다.  
  
 이 오류는 [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)] 및 C\# 컴파일러 버전이 일치하지 않거나 C\# 컴파일러를 지원하는 파일이 하나 이상 손상된 경우에도 나타날 수 있습니다. Visual Studio를 다시 설치합니다.