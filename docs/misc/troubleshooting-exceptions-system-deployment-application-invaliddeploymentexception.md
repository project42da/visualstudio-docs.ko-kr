---
title: "예외 문제 해결: System.Deployment.Application.InvalidDeploymentException | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "InvalidDeploymentException 클래스"
ms.assetid: 4361e053-8eaf-44e3-b8ac-95516d8d1832
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Deployment.Application.InvalidDeploymentException
<xref:System.Deployment.Application.InvalidDeploymentException> 예외는 응용 프로그램이나 해당 응용 프로그램 및 배포 매니페스트가 유효하지 않은 경우에 throw됩니다.  
  
## 관련 팁  
 **이 응용 프로그램의 매니페스트가 올바른지 확인하십시오.**  
 응용 프로그램 매니페스트는 응용 프로그램에서 런타임에 바인딩해야 할 공유 및 전용 side\-by\-side 어셈블리를 설명하고 식별하는 XML 파일입니다. 이는 응용 프로그램을 테스트하는 데 사용된 어셈블리 버전과 동일해야 합니다. 응용 프로그램 매니페스트에서는 응용 프로그램에 전용인 파일의 메타데이터를 설명하기도 합니다.  
  
 **ClickOnce 기능을 사용하여 응용 프로그램을 배포하십시오.**  
 ClickOnce를 사용하여 Windows 응용 프로그램을 웹 서버에 게시합니다. 설치를 단순화하기 위해 네트워크 파일 공유 위치에 게시할 수도 있습니다. 자세한 내용은 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)을 참조하세요.  
  
## 참고 항목  
 <xref:System.Deployment.Application.InvalidDeploymentException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [ClickOnce 배포 문제 해결](../deployment/troubleshooting-clickonce-deployments.md)   
 [Windows Forms에 대한 ClickOnce 배포](../Topic/ClickOnce%20Deployment%20for%20Windows%20Forms.md)