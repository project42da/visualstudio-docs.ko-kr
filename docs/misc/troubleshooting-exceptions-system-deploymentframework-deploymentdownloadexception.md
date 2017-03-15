---
title: "예외 문제 해결: System.DeploymentFramework.DeploymentDownloadException | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DeploymentDownloadException 클래스"
  - "응용 프로그램 배포[C#], DeploymentDownloadException 클래스"
  - "응용 프로그램 배포[C#], DeploymentDownloadException 클래스"
ms.assetid: 55ec7af5-b1d1-4db2-8af8-3c708f521cc7
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.DeploymentFramework.DeploymentDownloadException
`T:System.DeploymentFramework.DeploymentDownloadException`은 응용 프로그램 업데이트를 다운로드하는 동안 네트워크 예외가 발생한 경우에 발생합니다.  
  
## 관련 팁  
 **InnerException을 조사하여 내부 System.Net 또는 System.IO 예외를 확인하세요.**  
 이 예외는 응용 프로그램 업데이트를 다운로드하는 동안 네트워크 예외가 발생할 때마다 발생합니다. 예외의 <xref:System.Exception.InnerException%2A> 속성을 조사하면 내부 예외를 확인할 수 있습니다.  
  
## 참고 항목  
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)