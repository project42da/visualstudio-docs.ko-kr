---
title: "예외 문제 해결: System.CannotUnloadAppDomainException | Microsoft Docs"
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
  - "CannotUnloadAppDomainException 클래스"
ms.assetid: eeee07c3-fdbc-4c91-859b-a419d23be9ba
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.CannotUnloadAppDomainException
<xref:System.CannotUnloadAppDomainException> 예외는 다음 중 하나를 언로드할 때 throw됩니다.  
  
-   응용 프로그램 수명이 다할 때까지 로드된 상태를 유지해야 하는 기본 응용 프로그램 도메인  
  
-   실행을 즉시 중지할 수 없는 실행 스레드가 있는 응용 프로그램 도메인  
  
-   이미 언로드된 응용 프로그램 도메인  
  
## 관련 팁  
 **기본 도메인이거나 실행 중인 스레드가 있거나 이미 언로드된 응용 프로그램 도메인은 언로드할 수 없습니다.**  
 이와 같은 조건에서 이 예외가 throw될 수 있습니다. 자세한 내용은 <xref:System.AppDomain.Unload%2A>을 참조하세요.  
  
## 참고 항목  
 <xref:System.CannotUnloadAppDomainException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)