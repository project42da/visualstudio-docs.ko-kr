---
title: "예외 문제 해결: System.TypeInitializationException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "TypeInitializationException 예외"
  - "System.TypeInitializationException 예외"
ms.assetid: c77e81fd-1518-49a1-8213-3f169658f5f5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.TypeInitializationException
클래스 이니셜라이저에 의해 throw되는 예외 주위에서 래퍼로 throw되는 예외입니다.  
  
## 설명  
 클래스 이니셜라이저가 형식을 초기화하지 못하면 <xref:System.TypeInitializationException>이 만들어지고 해당 형식의 클래스 이니셜라이저가 throw한 예외에 대한 참조가 전달됩니다.<xref:System.Exception.InnerException%2A>의 <xref:System.TypeInitializationException> 속성에 내부 예외가 저장됩니다.  
  
## 참고 항목  
 <xref:System.TypeInitializationException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)