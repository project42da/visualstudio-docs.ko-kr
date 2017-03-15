---
title: "예외 문제 해결: System.Security.VerificationException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EHVerification"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "VerificationException 클래스"
ms.assetid: b7b1a4c2-6769-46bd-8912-ebbfe226bfb3
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Security.VerificationException
<xref:System.Security.VerificationException> 예외는 보안 정책상 코드의 형식이 안전해야 하지만 확인 프로세스에서 코드의 형식이 안전한지 확인할 수 없는 경우에 throw됩니다.  
  
## 관련 팁  
 응용 프로그램이 두 개의 충돌하는 클래스 라이브러리 버전을 로드하지 않는지 확인하세요.  
 확인 프로세스의 일부로서 MSIL\(Microsoft Intermediate Language\)의 형식이 안전한지 여부를 검사하여 개체를 서로 안전하게 격리시켜 우발적이거나 악의적인 손상으로부터 안전하게 보호할 수 있도록 합니다. 자세한 내용은 [형식 안전성 및 보안](http://msdn.microsoft.com/ko-kr/095cd1f6-d8db-4c0e-bce2-83ccb34dd5dc)을 참조하세요.  
  
## 참고 항목  
 <xref:System.Security.VerificationException>   
 <xref:System.Security.Permissions.SecurityPermissionAttribute.SkipVerification%2A>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)