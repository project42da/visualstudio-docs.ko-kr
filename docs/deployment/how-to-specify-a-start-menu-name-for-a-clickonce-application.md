---
title: "방법: ClickOnce 응용 프로그램의 시작 메뉴 이름 지정 | Microsoft Docs"
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
  - "ClickOnce 배포, 시작 메뉴 이름"
  - "시작 메뉴 이름"
  - "시작 메뉴 리소스 이름"
ms.assetid: 4b5183b2-2fd4-4433-9310-4a73bb12c4e3
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: ClickOnce 응용 프로그램의 시작 메뉴 이름 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 온라인과 오프라인으로 모두 사용하도록 설치하면 **시작** 메뉴 및 **프로그램 추가\/제거** 목록에 항목이 추가됩니다.  기본적으로 표시 이름은 응용 프로그램 어셈블리의 이름과 같지만 **게시 옵션** 대화 상자의 **제품 이름**을 설정하여 표시 이름을 바꿀 수 있습니다.  
  
 **제품 이름**은 publish.htm 페이지에 표시됩니다. 설치된 오프라인 응용 프로그램의 경우 제품 이름은 **시작** 메뉴의 항목 이름과 **프로그램 추가\/제거**에 표시되는 이름으로 사용됩니다.  
  
 **게시자 이름**은 publish.htm 페이지에서 **제품 이름** 위에 표시됩니다. 설치된 오프라인 응용 프로그램의 경우 게시자 이름은 **시작** 메뉴의 응용 프로그램 아이콘이 들어 있는 폴더 이름으로 사용됩니다.  
  
 **프로젝트 디자이너**의 **게시** 페이지에 있는 **게시 옵션** 대화 상자에서 **제품 이름** 및 **게시자 이름** 속성을 설정할 수 있습니다.  
  
### 시작 메뉴 이름을 지정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 탭을 클릭합니다.  
  
3.  **옵션** 단추를 클릭하여 **게시 옵션** 대화 상자를 엽니다.  
  
4.  **설명**을 클릭합니다.  
  
5.  **게시 옵션** 대화 상자에서 **제품 이름**에 표시할 이름을 입력합니다.  
  
6.  선택적으로 **게시자 이름**에 게시자 이름을 입력할 수 있습니다.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)