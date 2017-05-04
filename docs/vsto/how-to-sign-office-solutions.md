---
title: "방법: Office 솔루션에 서명 | Microsoft Docs"
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
  - "인증서[Visual Studio에서 Office 개발], Office 솔루션"
  - "보안[Visual Studio에서 Office 개발], Office 솔루션 서명"
  - "매니페스트 서명[Visual Studio에서 Office 개발]"
ms.assetid: d3df5ee6-f1b7-47ed-b7ee-8985679ee3af
caps.latest.revision: 18
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# 방법: Office 솔루션에 서명
  솔루션에 서명할 경우 인증서를 증명 정보로 사용하여 솔루션에 신뢰를 부여할 수 있습니다.  여러 솔루션에 동일한 인증서를 사용할 수 있으며, 이 경우 모든 솔루션은 보안 정책을 추가로 업데이트하지 않고도 신뢰됩니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 매니페스트 생성 및 편집 도구\(mage.exe 및 mageui.exe\)를 사용하여 응용 프로그램 및 배포 매니페스트를 수동으로 편집할 경우 이러한 도구를 사용하기 전에 먼저 매니페스트에 다시 서명해야 합니다.  자세한 내용은 [방법: 응용 프로그램 및 배포 매니페스트에 다시 서명](~/deployment/how-to-re-sign-application-and-deployment-manifests.md)을 참조하십시오.  
  
## 인증서를 사용하여 서명  
 인증서는 솔루션 게시자의 고유 키 및 ID가 들어 있는 파일입니다.  인증서는 인증 기관에서 구입할 수도 있고 사용자가 직접 인증서를 만든 후 인증 기관의 서명을 받을 수도 있습니다.  
  
 Visual Studio에서는 디버깅을 사용할 수 있도록 임시 인증서를 사용하여 Office 솔루션에 서명합니다.  임시 인증서를 배포된 솔루션에서 증명 정보로 사용해서는 안 됩니다.  
  
#### 인증서를 사용하여 Office 솔루션에 서명하려면  
  
1.  **프로젝트** 메뉴에서 *SolutionName* **속성**을 클릭합니다.  
  
2.  **서명** 탭을 클릭합니다.  
  
3.  **ClickOnce 매니페스트 서명**을 선택합니다.  
  
4.  **저장소에서 선택**이나 **파일에서 선택**을 클릭하여 인증서를 찾은 다음 해당 인증서로 이동합니다.  
  
5.  올바른 인증서가 사용되는지 확인하려면 **자세한 내용**을 클릭하여 인증서 정보를 봅니다.  
  
## 참고 항목  
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)   
 [Office 솔루션에 신뢰 부여](../vsto/granting-trust-to-office-solutions.md)   
 [프로젝트 디자이너, 서명 페이지](../ide/reference/signing-page-project-designer.md)  
  
  