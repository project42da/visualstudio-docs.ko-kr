---
title: "방법: ClickOnce 응용 프로그램의 게시 페이지 지정 | Microsoft Docs"
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
  - "ClickOnce 배포, 게시 페이지 지정"
  - "응용 프로그램 배포[ClickOnce], 게시 페이지 지정"
  - "게시 페이지 속성"
  - "게시, ClickOnce"
ms.assetid: 9d70eebb-bdee-4b42-8e7e-7a07e199bdf7
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: ClickOnce 응용 프로그램의 게시 페이지 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 게시하면 기본 웹 페이지\(publish.htm\)가 생성되어 응용 프로그램과 함께 게시됩니다.  이 페이지에는 응용 프로그램의 이름, 응용 프로그램 및\/또는 필수 구성 요소를 설치하기 위한 링크, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]를 설명하는 도움말 항목 링크가 포함되어 있습니다.  프로젝트의 **게시 페이지** 속성을 사용하면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 대한 웹 페이지의 이름을 지정할 수 있습니다.  
  
 게시 페이지를 지정하고 나면 다음에 해당 페이지를 게시할 때 게시 위치로 복사되며 다시 게시해도 덮어쓰지 않습니다.  페이지 모양을 사용자 지정하려는 경우에도 변경한 내용이 삭제될까 걱정하지 않아도 됩니다.  자세한 내용은 [방법: ClickOnce 기본 웹 페이지 사용자 지정](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md)을 참조하십시오.  
  
 **게시 페이지** 속성은 **프로젝트 디자이너**의 **게시** 창에서 액세스할 수 있는 **게시 옵션** 대화 상자에서 설정할 수 있습니다.  
  
### ClickOnce 응용 프로그램에 대한 사용자 지정 웹 페이지를 지정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 창을 선택합니다.  
  
3.  **옵션** 단추를 클릭하여 **게시 옵션** 대화 상자를 엽니다.  
  
4.  **배포**를 클릭합니다.  
  
5.  **게시 옵션** 대화 상자에서 기본적으로 선택되는 **게시한 후 배포 웹 페이지 열기** 확인란이 선택되어 있는지 확인합니다.  
  
6.  **배포 웹 페이지:** 상자에 웹 페이지의 이름을 입력하고 **확인**을 클릭합니다.  
  
### 게시할 때마다 게시 페이지가 시작되지 않도록 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 창을 선택합니다.  
  
3.  **옵션** 단추를 클릭하여 **게시 옵션** 대화 상자를 엽니다.  
  
4.  **배포**를 클릭합니다.  
  
5.  **게시 옵션** 대화 상자에서 **게시한 후 배포 웹 페이지 열기** 확인란의 선택을 취소합니다.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [방법: ClickOnce 기본 웹 페이지 사용자 지정](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md)