---
title: "방법: ClickOnce 응용 프로그램을 사용하여 필수 구성 요소 설치 | Microsoft Docs"
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
  - "구성 요소, 부트스트래핑"
  - "응용 프로그램 배포[ClickOnce], 필수 구성 요소"
  - "필수 구성 요소, ClickOnce"
ms.assetid: e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: ClickOnce 응용 프로그램을 사용하여 필수 구성 요소 설치
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

모든 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 실행하려면 컴퓨터에 올바른 버전의 .NET Framework가 설치되어 있어야 합니다. 또한 많은 응용 프로그램에는 다른 필수 구성 요소도 필요합니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 게시할 때는 응용 프로그램과 함께 패키지할 필수 구성 요소 집합을 선택할 수 있습니다.  설치 시에 각 필수 구성 요소가 존재하는지를 확인하며, 필수 구성 요소가 없으면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 설치 전에 설치됩니다.  
  
 필수 구성 요소를 패키지 및 게시하는 대신 구성 요소의 다운로드 위치를 지정할 수도 있습니다.  예를 들어 게시하는 모든 응용 프로그램에 필수 구성 요소를 포함시키는 대신 모든 필수 구성 요소에 대한 설치 관리자가 있는 중앙의 파일 공유 또는 웹 위치를 사용할 수 있습니다. 이 경우 설치 시 해당 위치에서 구성 요소가 다운로드되어 설치됩니다.  
  
> [!IMPORTANT]
>  처음 게시 하기 전에 필수 구성 요소 설치 관리자 패키지를 개발 컴퓨터에 추가 해야 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다.  자세한 내용은 [방법: ClickOnce 응용 프로그램을 사용하여 필수 구성 요소 포함](../deployment/how-to-include-prerequisites-with-a-clickonce-application.md)를 참조하십시오.  
  
 필수 구성 요소는 **프로젝트 디자이너**의 **게시** 창에서 액세스할 수 있는 **필수 구성 요소** 대화 상자에서 관리합니다.  
  
> [!NOTE]
>  미리 결정된 필수 구성 요소 목록 외에 원하는 구성 요소를 목록에 추가할 수 있습니다.  자세한 내용은 [부트스트래퍼 패키지 만들기](../deployment/creating-bootstrapper-packages.md)를 참조하십시오.  
  
### ClickOnce 응용 프로그램과 함께 설치할 필수 구성 요소를 지정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 창을 선택합니다.  
  
3.  **필수 구성 요소** 단추를 클릭하여 **필수 구성 요소** 대화 상자를 엽니다.  
  
4.  **필수 구성 요소** 대화 상자에서 **필수 구성 요소를 설치하기 위한 설치 프로그램 만들기** 확인란이 선택되어 있는지 확인합니다.  
  
5.  **필수 구성 요소** 목록에서 설치할 구성 요소를 선택하고 **확인**을 클릭합니다.  
  
     선택한 구성 요소가 패키지되어 응용 프로그램과 함께 게시됩니다.  
  
### 필수 구성 요소에 대해 다른 다운로드 위치를 지정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 창을 선택합니다.  
  
3.  **필수 구성 요소** 단추를 클릭하여 **필수 구성 요소** 대화 상자를 엽니다.  
  
4.  **필수 구성 요소** 대화 상자에서 **필수 구성 요소를 설치하기 위한 설치 프로그램 만들기** 확인란이 선택되어 있는지 확인합니다.  
  
5.  **필수 구성 요소의 설치 위치를 지정하십시오.** 섹션에서 **다음 위치에서 필수 구성 요소 다운로드**를 선택합니다.  
  
6.  드롭다운 목록에서 위치를 선택하거나 URL, 파일 경로 또는 FTP 위치를 입력한 후 **확인**을 클릭합니다.  
  
    > [!NOTE]
    >  지정한 구성 요소의 설치 관리자가 지정한 위치에 있는지 확인해야 합니다.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)