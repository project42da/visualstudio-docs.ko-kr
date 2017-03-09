---
title: "예외 문제 해결: System.AccessViolationException | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "System.AccessViolationException 예외"
  - "AccessViolationException 클래스"
ms.assetid: 7f09315d-8aad-4ab1-8b5e-21a8c97f6c14
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.AccessViolationException
<xref:System.AccessViolationException>은 보호된 메모리를 읽거나 쓰려는 경우에 throw됩니다.  
  
## 관련 팁  
 액세스하려는 메모리가 할당되어 있는지 확인합니다.  
 자동 메모리 관리는 공용 언어 런타임에서 제공하는 서비스 중 하나입니다. 관리 코드로 전환하면 이 서비스를 활용할 수 있습니다. 자세한 내용은 [자동 메모리 관리](../Topic/Automatic%20Memory%20Management.md)을 참조하십시오.  
  
 액세스하려는 메모리가 손상되지 않았는지 확인합니다.  
 잘못된 포인터를 통해 읽기 또는 쓰기 작업을 여러 차례 수행하면 메모리가 손상될 수 있습니다.  
  
### 설명  
 비관리 코드나 안전하지 않은 코드에서 할당되지 않았거나 액세스 권한이 없는 메모리를 읽거나 쓰려고 하면 액세스 위반이 발생합니다. 잘못된 포인터를 통해 읽거나 쓸 때 항상 액세스 위반이 발생하는 것은 아닙니다. 액세스 위반은 일반적으로 잘못된 포인터를 통해 여러 차례 읽기 또는 쓰기 작업을 수행하여 메모리가 손상되었을 수 있음을 나타냅니다.  
  
 관리 코드에서 모든 참조는 유효하거나 null입니다. 안정형 코드에서 null 참조를 참조하려는 작업을 수행하면 <xref:System.NullReferenceException>이 throw됩니다.  
  
 안전하지 않은 관리 코드에서 발생하는 액세스 위반은 플랫폼에 따라 <xref:System.NullReferenceException> 또는 <xref:System.AccessViolationException>으로 표현될 수 있습니다.  
  
 비관리 코드에서 발생하여 관리 코드로 전달되는 액세스 위반은 항상 <xref:System.AccessViolationException>에 래핑됩니다.  
  
## 참고 항목  
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [메모리 관리: 예](../Topic/Memory%20Management:%20Examples.md)   
 [자동 메모리 관리](../Topic/Automatic%20Memory%20Management.md)