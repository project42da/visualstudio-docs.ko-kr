---
title: "방법: ClickOnce 응용 프로그램의 URL 활성화를 사용하지 않도록 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 배포, URL 활성화"
  - "disallowUrlActivation"
  - "URL 활성화, ClickOnce 응용 프로그램"
ms.assetid: db31a16b-960f-4264-91d7-c7c40f876068
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: ClickOnce 응용 프로그램의 URL 활성화를 사용하지 않도록 설정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

일반적으로 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 웹 서버에서 설치된 후 바로 자동으로 시작됩니다.  보안상 이유로 이 동작을 사용하지 않도록 결정하고 사용자에게 **시작** 메뉴에서 응용 프로그램을 시작하도록 알릴 수 있습니다.  다음 절차에서는 URL 활성화를 사용하지 않도록 설정하는 방법에 대해 설명합니다.  
  
 이 방법은 웹 서버에서 사용자 컴퓨터에 설치된 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 대해서만 사용할 수 있습니다.  URL을 사용하여 시작할 수 있는 온라인 전용 응용 프로그램에는 사용할 수 없습니다.  온라인 전용 응용 프로그램과 설치된 응용 프로그램 간 차이점에 대한 자세한 내용은 [ClickOnce 배포 전략 선택](../deployment/choosing-a-clickonce-deployment-strategy.md)을 참조하세요.  
  
 이 절차에서는 [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)] 도구 MageUI.exe를 사용합니다.  이 도구에 대한 자세한 내용은 [MageUI.exe \(매니페스트 생성 및 편집 도구, 그래픽 클라이언트\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)를 참조하세요.  또한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]을\(를\) 사용하여 이 작업을 수행할 수 있습니다.  
  
## 프로시저  
  
#### 응용 프로그램의 URL 활성화를 사용하지 않도록 설정하려면  
  
1.  MageUI.exe에서 배포 매니페스트를 엽니다.  아직 배포 매니페스트를 만들지 않았으면 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)의 단계에 따릅니다.  
  
2.  **배포 옵션** 탭을 선택합니다.  
  
3.  **설치 후 자동으로 응용 프로그램 실행** 확인란의 선택을 취소합니다.  
  
4.  매니페스트를 저장하고 여기에 서명합니다.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)