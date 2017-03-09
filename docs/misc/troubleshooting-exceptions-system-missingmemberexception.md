---
title: "예외 문제 해결: System.MissingMemberException | Microsoft Docs"
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
  - "MissingMemberException 클래스"
ms.assetid: c4cf497b-0554-47fe-b2e9-81ee3eb9ec04
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.MissingMemberException
<xref:System.MissingMemberException> 예외는 존재하지 않는 클래스 멤버에 동적으로 액세스하려 할 때 throw됩니다.  
  
## 관련 팁  
 **클래스 라이브러리에서 멤버가 제거되거나 이름이 변경된 경우 해당 라이브러리를 참조하는 모든 어셈블리를 다시 컴파일하십시오.**  
 이 예외는 일반적으로 하나의 어셈블리에서 필드나 메서드가 삭제되거나 그 이름이 바뀌었지만 이와 같은 더 이상 존재하지 않는 메서드에 액세스하려는 두 번째 어셈블리에 이러한 변경 내용이 반영되지 않은 경우에 throw됩니다.  
  
 **런타임에 바인딩된 개체 변수의 멤버에 액세스하는 경우 이 멤버가 Public으로 선언되어 있는지 확인하십시오.**  
 `Protected`, `Friend` 및 `Private` 변수는 Visual Basic에서 런타임에 바인딩할 수 없습니다.  
  
## 참고 항목  
 <xref:System.MissingMemberException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)