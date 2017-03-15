---
title: "예외 문제 해결: System.MissingMethodException | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
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
  - "MissingMethodException 클래스"
ms.assetid: 1ca4c351-ca26-4a6d-a5a1-c484ac193e2e
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.MissingMethodException
<xref:System.MissingMethodException> 예외는 존재하지 않는 메서드에 동적 액세스를 시도하는 경우에 throw됩니다.  
  
## 관련 팁  
 **클래스 라이브러리에서 메서드가 제거된 경우 해당 라이브러리를 참조하는 모든 어셈블리를 다시 컴파일하십시오.**  
 이 예외는 강력한 이름으로 참조되지 않는 어셈블리의 메서드를 삭제하거나 그 이름을 변경한 경우 이러한 메서드에 동적 액세스를 시도할 때 일반적으로 throw됩니다.  
  
## 설명  
 관리되지 않는 함수를 호출하는 경우 CLR에서 모듈이나 함수를 찾을 수 없으면 이 예외가 throw됩니다.  
  
## 참고 항목  
 <xref:System.MissingMethodException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [Troubleshooting Interoperability](/dotnet/visual-basic/programming-guide/com-interop/troubleshooting-interoperability)