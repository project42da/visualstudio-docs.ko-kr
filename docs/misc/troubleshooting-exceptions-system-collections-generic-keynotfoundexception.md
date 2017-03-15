---
title: "예외 문제 해결: System.Collections.Generic.KeyNotFoundException | Microsoft Docs"
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
  - "KeyNotFoundException 클래스"
ms.assetid: de33f5bb-5709-46fe-b889-7105dbd24299
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Collections.Generic.KeyNotFoundException
<xref:System.Collections.Generic.KeyNotFoundException>은 존재하지 않는 키를 사용하여 컬렉션에서 키 또는 키 값 쌍을 검색하려 할 때 throw됩니다.  
  
## 관련 팁  
 **액세스하려는 컬렉션에 사용 중인 키가 있는지 확인하십시오.**  
 이 예외는 컬렉션에 없는 키를 사용하여 해당 컬렉션의 요소를 검색하는 작업을 수행할 때 발생합니다.  
  
### 설명  
 <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> 메서드를 사용하면 키가 있는지 확인할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Collections.Generic>   
 <xref:System.Collections.Generic.KeyNotFoundException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)