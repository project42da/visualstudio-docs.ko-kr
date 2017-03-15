---
title: "MSBuild 오류 MSB3122 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GenerateManifest.FileAssociationsApplicationNotFullTrust"
helpviewer_keywords: 
  - "MSB3122"
ms.assetid: 523e4160-f165-437a-9f19-fb2ec77d46f5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3122
**MSB3122: 파일 연결을 사용하려면 완전 신뢰가 필요합니다.**  
  
 파일 연결을 구성하는 응용 프로그램을 게시하려면 해당 응용 프로그램이 완전 신뢰 응용 프로그램이어야 합니다.  
  
### 이 오류를 해결하려면  
  
-   ClickOnce 보안 설정을 활성화하고 응용 프로그램을 완전 신뢰 응용 프로그램으로 설정합니다.  자세한 내용은 [방법: ClickOnce 보안 설정 사용](../deployment/how-to-enable-clickonce-security-settings.md)을 참조하십시오.  
  
## 참고 항목  
 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)   
 [ClickOnce 응용 프로그램의 코드 액세스 보안](../deployment/code-access-security-for-clickonce-applications.md)