---
title: "방법: ClickOnce 응용 프로그램의 기본 웹 페이지 사용자 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "Publish.htm 웹 페이지"
  - "ClickOnce 배포 기본 웹 페이지"
  - "응용 프로그램 배포[ClickOnce], 게시"
  - "게시, ClickOnce"
ms.assetid: 418de18c-bee9-4f24-9cd9-0252d175070d
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: ClickOnce 응용 프로그램의 기본 웹 페이지 사용자 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

ClickOnce 응용 프로그램을 웹에 게시하면 응용 프로그램과 함께 웹 페이지가 자동으로 생성 및 게시됩니다.  기본 페이지에는 응용 프로그램의 이름과 응용 프로그램 설치, 필수 구성 요소 설치 또는 MSDN 도움말 액세스를 위한 링크가 포함되어 있습니다.  
  
> [!NOTE]
>  페이지에 나타나는 실제 링크는 페이지가 표시되는 컴퓨터와 사용자가 포함하는 필수 구성 요소에 따라 다릅니다.  
  
 웹 페이지의 기본 이름은 Publish.htm이며 **프로젝트 디자이너**에서 다른 이름으로 변경할 수 있습니다.  자세한 내용은 [방법: ClickOnce 응용 프로그램의 게시 페이지 지정](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)을 참조하십시오.  
  
 Publish.htm 웹 페이지는 최신 버전이 검색되는 경우에만 게시됩니다.  
  
> [!NOTE]
>  **게시** 설정을 변경해도 Publish.htm 페이지에는 영향을 주지 않습니다. 단, 처음에 게시한 후 필수 구성 요소를 추가하거나 제거하면 필수 구성 요소 목록이 달라져 정확하지 않게 됩니다.  따라서 필수 구성 요소 링크의 텍스트를 편집하여 변경 내용을 반영해야 합니다.  
  
### 게시 웹 페이지를 사용자 지정하려면  
  
1.  ClickOnce 응용 프로그램을 웹 위치에 게시합니다.  자세한 내용은 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)을 참조하십시오.  
  
2.  웹 서버에서 Visual Web Designer나 다른 HTML 편집기로 Publish.htm 파일을 엽니다.  
  
3.  원하는 대로 페이지를 사용자 지정하고 저장합니다.  
  
4.  선택 사항입니다.  사용자 지정된 게시 웹 페이지를 Visual Studio에서 덮어쓰지 않도록 하려면 게시 옵션 대화 상자에서 **게시할 때마다 자동으로 배포 웹 페이지 생성**의 선택을 취소합니다.  
  
## 참고 항목  
 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: ClickOnce 응용 프로그램을 사용하여 필수 구성 요소 설치](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [방법: ClickOnce 응용 프로그램의 게시 페이지 지정](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)