---
title: "예외 문제 해결: System.DuplicateWaitObjectException | Microsoft Docs"
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
  - "DuplicateWaitObjectException 클래스"
ms.assetid: b9ff6932-a7cf-4a89-bd7d-e4ef1a3ff353
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.DuplicateWaitObjectException
<xref:System.DuplicateWaitObjectException> 예외는 <xref:System.Threading.WaitHandle> 또는 <xref:System.Threading.WaitHandle.WaitAll%2A>에 전달된 <xref:System.Threading.WaitHandle.WaitAny%2A> 개체의 배열에 중복된 운영 체제 핸들이 들어 있는 경우에 throw됩니다.  
  
## 관련 팁  
 **WaitAll 또는 WaitAny 메서드에 전달된 WaitHandle 개체가 고유한지 확인하십시오.**  
 <xref:System.Threading.WaitHandle> 배열에는 동일한 개체에 대한 여러 참조가 포함될 수 없습니다.  
  
### 설명  
 CLR\(공용 언어 런타임\)에서는 <xref:System.Threading.WaitHandle> 개체의 배열에서 실행을 기다리는 동기화 개체를 기반으로 한 스레드 동기화 메커니즘을 제공합니다.  
  
## 참고 항목  
 <xref:System.DuplicateWaitObjectException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)