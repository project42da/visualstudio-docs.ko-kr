---
title: "Office 솔루션에 신뢰 부여 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "보안[Visual Studio에서 Office 개발], 신뢰"
  - "포함 목록[Visual Studio에서 Office 개발], 포함 목록 정보"
  - "신뢰[Visual Studio에서 Office 개발], 2007 Office 시스템"
  - "신뢰 부여[Visual Studio에서 Office 개발]"
ms.assetid: 6c33e614-d367-4556-9e76-0f302ad0f929
caps.latest.revision: 37
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 36
---
# Office 솔루션에 신뢰 부여
  Office 솔루션에 신뢰 부여 솔루션 어셈블리, 응용 프로그램 매니페스트, 배포 매니페스트 및 문서를 신뢰 하도록 각 대상 컴퓨터의 보안 정책을 수정 하는 의미 합니다.  또는 최종 사용자가 Office 솔루션에 신뢰를 부여할 수 있습니다.  
  
 응용 프로그램 및 배포 매니페스트에 서명 하 여 Office 솔루션에 완전 신뢰를 부여할 수 있습니다.  
  
 최종 사용자의 신뢰 여부를 결정 하 여 Office 솔루션에 신뢰를 부여할 수 있는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 신뢰 프롬프트 합니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
##  <a name="Signing"></a> 응용 프로그램 및 배포에 서명 하 여 솔루션에 신뢰를 매니페스트합니다  
 Office 솔루션의 모든 응용 프로그램 및 배포 매니페스트는 게시자를 식별하는 인증서로 서명되어야 합니다.  인증서는 신뢰 여부를 결정하기 위한 기초를 제공합니다.  
  
 빌드할 때 임시 인증서가 자동으로 만들어지고 신뢰가 부여되므로 디버깅하는 동안 해당 솔루션이 실행됩니다.  임시 인증서로 서명 된 솔루션을 게시 하는 경우 최종 사용자가 신뢰 여부를 결정 해야 합니다.  
  
 신뢰할 수 있고 알려진 인증서로 솔루션에 서명하면 해당 솔루션은 최종 사용자에게 신뢰 여부를 결정하라는 메시지 없이 자동으로 설치됩니다.  서명을 위한 인증서를 얻는 방법에 대한 자세한 내용은 [ClickOnce 및 Authenticode](../deployment/clickonce-and-authenticode.md)를 참조하십시오.  인증서를 얻은 후에는 해당 인증서를 신뢰할 수 있는 게시자 목록에 추가하여 명시적으로 신뢰해야 합니다.  자세한 내용은 [방법: ClickOnce 응용 프로그램의 클라이언트 컴퓨터에 신뢰할 수 있는 게시자 추가](~/deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md)을 참조하십시오.  
  
 개발자가 임시 인증서로 솔루션에 서명하면 관리자는 Microsoft .NET Framework 도구 중 하나인 매니페스트 생성 및 편집 도구\(mage.exe\)를 사용하여 신뢰할 수 있고 알려진 인증서로 사용자 지정에 다시 서명할 수 있습니다.  솔루션 서명에 대한 자세한 내용은 [방법: Office 솔루션에 서명](../vsto/how-to-sign-office-solutions.md) 및 [방법: 응용 프로그램 및 배포 매니페스트 서명](~/ide/how-to-sign-application-and-deployment-manifests.md)을 참조하십시오.  
  
##  <a name="TrustPrompt"></a> ClickOnce 신뢰 프롬프트를 사용 하 여 솔루션에 신뢰  
 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]에서는 솔루션의 인증서를 신뢰하는 조직 전반의 정책이 없는 경우 최종 사용자에게 신뢰 여부를 결정하라는 메시지를 표시합니다.  최종 사용자가 솔루션에 신뢰를 부여하면 이 신뢰 관련 결정을 저장하는 URL 및 공개 키가 포함된 포함 목록이 만들어집니다.  신뢰된 사용자 지정을 나중에 실행할 경우 최종 사용자에게 메시지가 다시 표시되지 않습니다.  
  
 관리자는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 신뢰 프롬프트를 사용하지 않도록 설정하거나 Authenticode 인증서로 서명된 솔루션에 대해서만 해당 신뢰 프롬프트가 발생하도록 설정할 수 있습니다.  MyComputer, LocalIntranet, Internet, TrustedSites 및 UntrustedSites 영역에 대해 이러한 설정을 변경하는 방법에 대한 자세한 내용은 [방법: ClickOnce 신뢰 프롬프트 동작 구성](~/deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md)을 참조하십시오.  
  
## 참고 항목  
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)   
 [문서에 신뢰 부여](../vsto/granting-trust-to-documents.md)   
 [Office 솔루션 보안 문제 해결](../vsto/troubleshooting-office-solution-security.md)   
 [Office 솔루션에 대한 특정 보안 고려 사항](../vsto/specific-security-considerations-for-office-solutions.md)  
  
  