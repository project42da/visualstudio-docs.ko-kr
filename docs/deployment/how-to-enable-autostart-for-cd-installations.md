---
title: "방법: CD 설치를 위한 자동 시작 사용 | Microsoft Docs"
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
  - "ClickOnce 배포, AutoStart"
  - "ClickOnce 배포, CD 또는 DVD 설치"
  - "응용 프로그램 배포[ClickOnce], CD 또는 DVD 설치"
ms.assetid: caaec619-900c-4790-90e3-8c91f5347635
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: CD 설치를 위한 자동 시작 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

CD\-ROM 또는 DVD\-ROM 같은 이동식 미디어를 통해 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 배포하는 경우 미디어를 삽입하면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램이 자동으로 시작되도록 `AutoStart`를 활성화할 수 있습니다.  
  
 `AutoStart`는 **프로젝트 디자이너**의 **게시** 페이지에서 활성화할 수 있습니다.  
  
### AutoStart를 활성화하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 탭을 클릭합니다.  
  
3.  **옵션** 단추를 클릭합니다.  
  
     **게시 옵션** 대화 상자가 표시됩니다.  
  
4.  **배포**를 클릭합니다.  
  
5.  **CD 설치에서 CD를 삽입하면 자동으로 설치 시작** 확인란을 선택합니다.  
  
     응용 프로그램이 게시되면 Autorun.inf 파일이 게시 위치에 복사됩니다.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)