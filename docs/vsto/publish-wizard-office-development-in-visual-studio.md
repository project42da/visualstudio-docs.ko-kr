---
title: "게시 마법사(Visual Studio에서는 Office 개발) | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VST.ProjectProperties.PublishWizard"
  - "VST.PublishWizard.Publish.2007System"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "ClickOnce 배포[Visual Studio에서 Office 개발], 게시 마법사"
  - "응용 프로그램 배포[Visual Studio에서 Office 개발], 게시 마법사"
  - "Office 응용 프로그램[Visual Studio에서 Office 개발], 게시 마법사"
  - "게시 마법사, Office 솔루션"
ms.assetid: 793314b6-b6a6-4509-8f1c-dd9466cf5190
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# 게시 마법사(Visual Studio에서는 Office 개발)
  사용은  **게시 마법사** 솔루션 파일을 지정한 위치에 복사 하려면 매니페스트 파일을 만들고 설치 프로그램을 만드는 합니다.  
  
 이 마법사에 액세스 하는  **빌드** 메뉴를 선택  **게시** *SolutionName*.  **솔루션 탐색기**에서도 **게시 마법사**에 액세스할 수 있습니다.  바로 가기 메뉴에서 프로젝트 노드를 열고 선택  **게시**.  
  
 다음의 각 단원에서는 마법사의 페이지에 대해 설명합니다.  
  
## 응용 프로그램을 게시할 위치  
 **이 응용 프로그램을 게시할 위치 지정**  
 필수 요소.  게시 위치는 **게시 마법사**가 매니페스트, 어셈블리, 임시 인증서, 빌드의 기타 파일 등 솔루션 파일을 복사하는 위치입니다.  이 디렉터리에 대한 쓰기 액세스 권한이 있어야 합니다.  
  
 디스크 경로, 파일 공유, FTP 사이트 또는 웹 사이트 URL로 위치를 입력 하거나 클릭 하는  **찾아보기** 버튼의 위치를 찾아볼 수 있습니다.  경로는 다음과 같은 형식일 수 있습니다.  
  
-   표준 Windows 형식의 상대 경로 또는 절대 경로\(예: C:\\Deploy\\MyApplication 또는 \\MyApplication\)  
  
-   UNC\(Universal Naming Convention\) 경로\(예: \\\\ServerName\\MyApplication\\\)  
  
-   Http:\/\/www.microsoft.com\/myapplication와 같은 웹 사이트의 URL입니다.  
  
 IIS가 설치된 경우의 기본 게시 위치는 *http:\/\/localhost\/projectname\/*이고 설치되어 있지 않은 경우의 기본 게시 위치는 publish\\ 디렉터리입니다.  
  
> [!NOTE]  
>  대상 컴퓨터에서 Windows Vista를 실행하는 경우 추가로 고려해야 할 사항이 있습니다.  로컬 게시 옵션을 사용하려면 Windows Vista 컴퓨터의 관리자여야 합니다.  또한 IIS의 설치 여부에 관계없이 기본 위치가 항상 *publish\\* 디렉터리입니다.  
  
## 최종 사용자 컴퓨터의 기본 설치 경로  
 설치 경로는 선택 옵션입니다.  필요한 경우 설치 경로를 나중에 설정할 수 있습니다.  자세한 내용은 [방법: Office 솔루션의 설치 경로 변경](http://msdn.microsoft.com/ko-kr/d0eaa07b-2d72-4902-899f-2f9fb165b8fd)를 참조하십시오.  
  
 설치 경로는 최종 사용자가 사용자 지정을 설치하는 데 사용할 원본 디렉터리입니다.  또한 솔루션에서 업데이트를 확인하는 데 사용할 경로입니다.  이 경로가 이전 페이지의 **이 응용 프로그램을 게시할 위치 지정** 상자에 입력한 경로와 다른 경우 **게시 마법사**는 솔루션을 이 위치에 배포하지 않습니다.  
  
 **웹 사이트에서**  
 최종 사용자가 솔루션을 설치하기 위해 방문할 URL을 지정합니다.  
  
 **UNC 경로 또는 파일 공유에서**  
 최종 사용자가 솔루션을 설치할 때 사용할 UNC 경로를 지정합니다.  
  
 **CD\-ROM 또는 DVD\-ROM에서**  
 이 옵션을 선택하는 경우 설치 경로를 지정할 필요가 없습니다.  
  
 Visual Studio에는 CD나 DVD를 굽는 기능이 없으므로  출력 내용을 CD나 DVD에 직접 복사해야 합니다.  
  
## 참고 항목  
 [ClickOnce를 사용하여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [게시 페이지, 프로젝트 디자이너&#40;Visual Studio에서는 Office 개발&#41;](../vsto/publish-page-project-designer-office-development-in-visual-studio.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)  
  
  