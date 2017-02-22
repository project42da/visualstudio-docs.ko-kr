---
title: "방법: 디자이너를 사용하여 ClickOnce 응용 프로그램의 URL 활성화 해제 | Microsoft Docs"
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
  - "disallowURLActivation"
  - "URL 활성화, ClickOnce 응용 프로그램"
ms.assetid: a337a582-e67c-409a-b52e-607cd1a8fc57
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: 디자이너를 사용하여 ClickOnce 응용 프로그램의 URL 활성화 해제
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

일반적으로 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 웹 서버에서 설치된 후 즉시 자동으로 시작됩니다.  보안상의 이유로 이 동작을 해제하고 대신 사용자가 **시작** 메뉴에서 응용 프로그램을 시작하도록 설정할 수 있습니다.  다음 절차에서는 URL 활성화를 사용하지 않도록 설정하는 방법을 설명합니다.  
  
 이 기술은 웹 서버에서 사용자 컴퓨터에 설치된 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에만 사용할 수 있고  URL로만 시작할 수 있는 온라인 전용 응용 프로그램에는 사용할 수 없습니다.  온라인 전용 응용 프로그램과 설치된 응용 프로그램의 차이점에 대한 자세한 내용은 [ClickOnce 배포 전략 선택](../deployment/choosing-a-clickonce-deployment-strategy.md)을 참조하십시오.  
  
 이 절차에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 사용합니다.  [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]를 사용하여 이 작업을 수행할 수도 있습니다.  자세한 내용은 [방법: ClickOnce 응용 프로그램의 URL 활성화를 사용하지 않도록 설정](../deployment/how-to-disable-url-activation-of-clickonce-applications.md)를 참조하십시오.  
  
## 절차  
  
#### 응용 프로그램의 URL 활성화를 사용하지 않도록 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  
  
2.  **속성** 페이지에서 **게시** 탭을 클릭합니다.  
  
3.  **옵션**을 클릭합니다.  
  
4.  **매니페스트**를 클릭합니다.  
  
5.  **URL을 통한 응용 프로그램 활성화 방지** 확인란을 선택합니다.  
  
6.  응용 프로그램을 배포합니다.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)