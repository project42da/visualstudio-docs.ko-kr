---
title: "방법: ClickOnce 보안 설정 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "ClickOnce 배포, 보안 설정"
  - "보안[Visual Studio], ClickOnce 응용 프로그램"
  - "보안 설정, ClickOnce 배포"
ms.assetid: 73cd3e9d-cd72-4ad2-8cae-94d6bb6b01e0
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: ClickOnce 보안 설정 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

ClickOnce 응용 프로그램을 게시하려면 해당 응용 프로그램의 코드 액세스 보안을 설정해야 합니다.  이 작업은 게시 마법사를 사용하여 응용 프로그램을 게시하면 자동으로 수행됩니다.  
  
 일부 경우에 코드 액세스 보안을 설정하면 응용 프로그램을 빌드하거나 디버깅할 때 성능이 저하될 수 있습니다. 이러한 경우에는 보안 설정을 일시적으로 비활성화할 수 있습니다.  
  
 ClickOnce 보안 설정은 **프로젝트 디자이너**의 **보안** 페이지에서 활성화 또는 비활성화할 수 있습니다.  
  
### ClickOnce 보안 설정을 활성화하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **보안** 탭을 클릭합니다.  
  
3.  **ClickOnce 보안 설정 사용** 확인란을 선택합니다.  
  
     이제 보안 페이지에서 응용 프로그램의 보안 설정을 사용자 지정할 수 있습니다.  
  
    > [!NOTE]
    >  이 확인란은 **게시** 마법사를 사용하여 응용 프로그램을 게시할 때마다 자동으로 선택됩니다.  
  
### ClickOnce 보안 설정을 비활성화하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **보안** 탭을 클릭합니다.  
  
3.  **ClickOnce 보안 설정 사용** 확인란의 선택을 취소합니다.  
  
     응용 프로그램은 완전 신뢰 보안 설정으로 실행되며 **보안** 페이지의 모든 설정은 무시됩니다.  
  
    > [!NOTE]
    >  게시 마법사를 사용하여 응용 프로그램을 게시할 때마다 이 확인란이 선택됩니다. 응용 프로그램이 게시된 후에는 다시 이 확인란의 선택을 취소해야 합니다.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)   
 [ClickOnce 응용 프로그램의 코드 액세스 보안](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)