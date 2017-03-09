---
title: "컴파일러 오류 CS0537 | Microsoft Docs"
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
  - "CS0537"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0537"
ms.assetid: 6c832a5f-47dc-4f60-aed8-69ac328af44b
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0537
System.Object 클래스는 기본 클래스를 포함할 수 없으며 인터페이스를 구현할 수 없습니다.  
  
 CS0537은 <xref:System> 클래스 라이브러리를 다시 빌드하며 <xref:System.Object>가 다른 클래스에서 파생되는 경우에 발생합니다. 이 오류가 발생할 가능성은 거의 없습니다. 오류가 발생할 경우 클래스 또는 인터페이스에서 <xref:System.Object>를 파생시키지 마세요. 전체 .NET Framework 클래스 계층 구조의 루트이므로 다른 항목에서 파생되지 않습니다.