---
title: "예외 문제 해결: System.ArgumentNullException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
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
  - "ArgumentNullException 클래스"
ms.assetid: 5f21413c-d997-47c6-9b06-3d85a719d51b
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.ArgumentNullException
<xref:System.ArgumentNullException> 예외는 null을 유효한 인수로 사용할 수 없는 메서드에 null 참조\(Visual Basic의 경우 `Nothing`\)를 전달한 경우에 throw됩니다.  
  
## 관련 팁  
 **인수가 null이 아닌지 확인하십시오. Visual Basic의 경우에는 Nothing이 아닌지 확인하십시오.**  
 null 참조는 존재하지 않는 개체에 대한 참조입니다. null 참조는 대개 프로그래밍 방식으로 개체의 인스턴스를 만들지 않은 경우에 발생합니다.  
  
## 설명  
 <xref:System.ArgumentNullException>의 동작은 <xref:System.ArgumentException>과 동일합니다. 이 예외는 null 인수로 인해 발생하는 예외와 null이 아닌 인수로 인해 발생하는 예외를 응용 프로그램 코드에서 구분하기 위해 제공됩니다. null이 아닌 인수로 인해 발생하는 오류에 대한 자세한 내용은 [예외 문제 해결: System.ArgumentOutOfRangeException](../misc/troubleshooting-exceptions-system-argumentoutofrangeexception.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.ArgumentNullException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)