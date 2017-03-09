---
title: "예외 문제 해결: System.Deployment.DependentPlatformMissingException | Microsoft Docs"
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
  - "DependentPlatformMissingException 클래스"
ms.assetid: 2343eb4f-f23f-4b6c-a65c-1f93c3e6ea36
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Deployment.DependentPlatformMissingException
`T:System.Deployment.DependentPlatformMissingException` 예외는 호환되지 않는 컴퓨터에서 응용 프로그램의 실행을 시도하는 경우에 throw됩니다. 이 문제는 대상 컴퓨터에 잘못된 운영 체제나 잘못된 버전의 .NET Framework가 설치되어 있는 경우에 발생할 수 있습니다.  
  
## 관련 팁  
 **응용 프로그램에 필요한 모든 어셈블리가 대상 컴퓨터에 설치되어 있는지 확인하십시오.**  
 Windows Installer를 사용하려는 모든 설치에서는 우선 사용자의 컴퓨터에 설치 관리자가 있는지 검사한 다음 설치 관리자가 없으면 해당 컴퓨터에 Windows Installer를 설치할 준비가 되어 있는지 확인합니다.  
  
## 참고 항목  
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)