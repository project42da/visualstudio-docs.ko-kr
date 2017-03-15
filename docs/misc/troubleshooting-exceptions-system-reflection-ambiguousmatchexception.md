---
title: "예외 문제 해결: System.Reflection.AmbiguousMatchException | Microsoft Docs"
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
  - "System.Reflection.AmbiguousMatchException 예외"
  - "AmbiguousMatchException 예외"
ms.assetid: f92b5c51-42b6-4c2e-83df-0d598b3b41c4
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Reflection.AmbiguousMatchException
메서드에 대해 바인딩할 때 바인딩 기준에 일치하는 메서드가 두 개 이상인 경우 throw되는 예외입니다.  
  
## 설명  
 <xref:System.Reflection.AmbiguousMatchException>은 응용 프로그램에서 클래스를 호출했지만 어떠한 클래스 또는 오버로드된 클래스를 사용해야 할지 확인할 수 없는 경우 throw됩니다. 바인딩 과정에서는 매개 변수의 형식과 매개 변수의 수에 따라 사용할 적절한 클래스를 찾습니다. 조건에 맞는 클래스가 여러 개인 경우 이 예외가 throw됩니다.  
  
## 참고 항목  
 <xref:System.Reflection.AmbiguousMatchException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)