---
title: "예외 문제 해결: System.DeploymentFramework.DependentPlatformMissingException | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DependentPlatformMissingException 클래스, 문제 해결"
ms.assetid: fee1ca1c-0f0b-483b-b8ab-3743dfdda038
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.DeploymentFramework.DependentPlatformMissingException
`T:System.DeploymentFramework.DependentPlatformMissingException` 예외는 이 클라이언트에 설치되지 않은 항목에 응용 프로그램이 의존할 때 throw됩니다. 응용 프로그램이 배포되는 컴퓨터에 설치된 운영 체제나 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 버전이 잘못된 경우를 예로 들 수 있습니다.  
  
## 관련 팁  
 **응용 프로그램에 필요한 모든 어셈블리가 대상 컴퓨터에 설치되어 있는지 확인하세요.**  
 Windows Installer를 사용하려는 모든 설치에서는 우선 사용자의 컴퓨터에 설치 관리자가 있는지 검사한 다음 설치 관리자가 없으면 해당 컴퓨터에 Windows Installer를 설치할 준비가 되어 있는지 확인합니다.  
  
## 참고 항목  
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)