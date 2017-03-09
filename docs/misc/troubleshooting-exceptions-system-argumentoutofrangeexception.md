---
title: "예외 문제 해결: System.ArgumentOutOfRangeException | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ArgumentOutOfRangeException 클래스"
ms.assetid: f53c58d9-7c4e-407f-93d3-1e59d90d98f5
caps.latest.revision: 24
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.ArgumentOutOfRangeException
<xref:System.ArgumentOutOfRangeException>은 메서드를 호출할 때 메서드에 전달된 인수 중 적어도 하나 이상이 null 참조\(Visual Basic의 경우 `Nothing`\)가 아니지만 어떠한 인수에도 유효한 값이 포함되지 않은 경우에 throw됩니다.  
  
## 관련 팁  
 **이 메서드에 대한 인수의 값이 올바른지 확인하십시오.**  
 null 참조가 아닌 인수에는 유효한 값이 들어 있어야 합니다.  
  
 **컬렉션에 대한 작업을 하는 경우에는 인덱스가 컬렉션보다 크기가 작은지 확인하십시오.**  
 인덱스는 컬렉션 크기의 범위 내에 있어야 하고 이 크기 범위를 초과하거나 0보다 작을 수 없습니다. 자세한 내용은 [컬렉션](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)을 참조하세요.  
  
 **ComboBox 또는 ListBox와 함께 오버로드되고 인수가 두 개인 FindString 또는 FindExactString 메서드를 사용할 때에는 startIndex 매개 변수를 확인하십시오.**  
 이 예외는 `startIndex`가 관련 목록에 있는 마지막 항목의 인덱스 값과 같은 경우에 throw될 수 있습니다. 이 문제를 해결하려면 `startIndex` 매개 변수에 0을 전달하거나 인수가 한 개인 `FindString` 또는 `FindStringExact` 메서드를 사용합니다. 자세한 내용은 [CComboBox::FindString](../Topic/CComboBox::FindString.md) 또는 [CListBox::FindString](../Topic/CListBox::FindString.md)를 참조하세요.  
  
## 참고 항목  
 <xref:System.ArgumentOutOfRangeException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)