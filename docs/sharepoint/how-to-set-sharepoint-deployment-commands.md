---
title: "방법: SharePoint 배포 명령 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio에서 SharePoint 개발, 배포"
ms.assetid: 289c8c33-a603-434e-889f-a0d0a1736ecb
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# 방법: SharePoint 배포 명령 설정
  배포 전 및 배포 후 명령을 설정하여 배포 프로세스를 사용자 지정할 수 있습니다.  이러한 명령은 Visual Studio에서 SharePoint 솔루션을 디버깅할 때 다른 배포 작업 전후에 실행됩니다.  
  
### 배포 전 명령을 추가하려면  
  
1.  메뉴 모음의 **프로젝트** 메뉴에서 *ProjectName* **속성**을 선택합니다.  
  
2.  **SharePoint** 탭을 선택합니다.  
  
3.  **사전 배포 명령줄** 텍스트 상자에서 MS\-DOS 또는 MSBuild 명령을 입력하여 이 단계를 사용자 지정합니다.  
  
     예를 들어, 배포가 완료되기 전에 디렉터리 내용을 표시하려면 **dir**을 입력합니다.  
  
### 배포 후 명령을 추가하려면  
  
1.  메뉴 모음의 **프로젝트** 메뉴에서 *ProjectName* **속성**을 선택합니다.  
  
2.  **SharePoint** 탭을 선택합니다.  
  
3.  **배포 후 명령줄** 텍스트 상자에서 MS\-DOS 또는 MSBuild 명령을 입력하여 이 단계를 사용자 지정합니다.  
  
     예를 들어, 배포가 완료된 후에 디렉터리 내용을 표시하려면 **dir**을 입력합니다.  MSBuild 변수를 사용하여 빌드 디렉터리에서 어셈블리를 복사하려면 **copy $\(TargetPath\) c:\\DeploymentDirectory**를 입력합니다.  
  
## 참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  