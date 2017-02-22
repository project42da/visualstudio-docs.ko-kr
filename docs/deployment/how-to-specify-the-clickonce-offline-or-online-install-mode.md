---
title: "방법: ClickOnce 오프라인 또는 온라인 설치 모드 지정 | Microsoft Docs"
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
  - "ClickOnce 배포, 설치 모드 지정"
  - "ClickOnce 설치 모드"
  - "설치 모드"
  - "오프라인 응용 프로그램"
  - "온라인 응용 프로그램"
ms.assetid: 0aee5fc1-e966-4bda-9b8f-d9997aeaa779
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: ClickOnce 오프라인 또는 온라인 설치 모드 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램의 `Install Mode`는 응용 프로그램을 오프라인으로 사용할 수 있는지 아니면 온라인으로 사용할 수 있는지를 결정합니다.  **온라인으로만 응용 프로그램 사용 가능**을 선택한 경우 응용 프로그램을 실행하려면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 게시 위치\(웹 페이지 또는 파일 공유\)에 액세스해야 합니다.  **오프라인으로도 응용 프로그램 사용 가능**을 선택하면 **시작** 메뉴 및 **프로그램 추가\/제거** 대화 상자에 응용 프로그램 항목이 추가됩니다. 따라서 연결되지 않은 상태에서도 응용 프로그램을 실행할 수 있습니다.  
  
 `Install Mode`는 **프로젝트 디자이너**의 **게시** 페이지에서 설정할 수 있습니다.  
  
 **참고** 게시 마법사를 사용하여 `Install Mode`를 설정할 수도 있습니다.  자세한 내용은 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)를 참조하십시오.  
  
### ClickOnce 응용 프로그램을 온라인으로만 사용할 수 있게 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 탭을 클릭합니다.  
  
3.  **설치 모드 및 설정** 영역에서 **온라인으로만 응용 프로그램 사용 가능** 옵션 단추를 클릭합니다.  
  
### ClickOnce 응용 프로그램을 온라인 또는 오프라인으로 사용할 수 있게 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 탭을 클릭합니다.  
  
3.  **설치 모드 및 설정** 영역에서 **오프라인으로도 응용 프로그램 사용 가능** 옵션 단추를 클릭합니다.  
  
     응용 프로그램을 설치하면 **시작** 메뉴 및 제어판의 **프로그램 추가\/제거**에 응용 프로그램 항목이 추가됩니다.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [ClickOnce 배포 전략 선택](../deployment/choosing-a-clickonce-deployment-strategy.md)