---
title: "컴파일러 경고(수준 2) CS0444 | Microsoft Docs"
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
  - "CS0444"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0444"
ms.assetid: 5beb8c06-39d3-4b59-a7c3-5590200bd43d
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS0444
미리 정의된 형식 'type name 1'이 'System namespace 1'에 없고 'System namespace 2'에 있습니다.  
  
 <xref:System.Int32>와 같이 미리 정의된 개체가 컴파일러가 예상한 위치에 없고 'System namespace 2'에 있습니다.  
  
 이 오류는 .NET Framework가 잘못 설치되었다는 것을 나타낼 수 있습니다. 이를 해결하려면 .NET Framework를 다시 설치합니다.  
  
 사용자 고유의 기본 클래스 라이브러리를 작성하는 경우에도 이 오류가 발생할 수 있습니다. 이 경우 오류를 해결하려면 mscorlib를 다시 작성합니다.