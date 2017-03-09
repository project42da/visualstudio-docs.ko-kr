---
title: "예외 문제 해결: System.FieldAccessException | Microsoft Docs"
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
  - "FieldAccessException 클래스"
ms.assetid: 47a72daf-500e-494c-b2fe-374edad2e9cd
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.FieldAccessException
<xref:System.FieldAccessException> 예외는 클래스 내의 전용 필드나 보호된 필드에 잘못된 액세스를 시도하는 경우에 throw됩니다.  
  
## 관련 팁  
 **클래스 라이브러리에 있는 필드의 액세스 수준이 변경된 경우 해당 라이브러리를 참조하는 모든 어셈블리를 다시 컴파일하십시오.**  
 이 예외는 대개 클래스 라이브러리에 있는 필드의 액세스 수준\(`Public`, `Private` 등\)이 변경되었지만 이 라이브러리를 참조하는 하나 이상의 어셈블리를 다시 컴파일하지 않은 경우에 throw됩니다.  
  
## 참고 항목  
 <xref:System.FieldAccessException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)