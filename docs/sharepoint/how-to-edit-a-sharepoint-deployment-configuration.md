---
title: "방법: SharePoint 배포 구성 편집"
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
  - "VS.SharePointTools.Project.DeploymentConfig"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio에서 SharePoint 개발, 배포"
ms.assetid: bff1895b-d3fe-4ec0-ba91-f8884dc35957
caps.latest.revision: 14
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# 방법: SharePoint 배포 구성 편집
  배포 구성을 만들거나 기존 배포 구성을 수정할 수 있습니다.  예를 들어 하나의 단계를 실행하거나 배포 프로세스의 단계 순서를 변경할 수 있습니다.  기본 제공 구성과 프로그래밍 방식으로 추가된 구성은 변경할 수 없으므로 배포 구성을 만들거나 수정해야 할 수도 있습니다.  
  
## SharePoint 배포 구성 만들기  
  
#### SharePoint 배포 구성을 만들려면  
  
1.  **솔루션 탐색기** 에서 SharePoint 프로젝트를 선택한 다음, 메뉴 표시줄에서 **프로젝트**, *ProjectName* **속성** 을 선택합니다.  
  
2.  **SharePoint** 탭에서, **새로 만들기** 버튼을 선택합니다.  
  
     **새 배포 구성 추가** 대화 상자가 나타납니다.  
  
3.  **이름** 텍스트 상자에 배포 구성의 이름을 입력합니다.  
  
4.  **사용 가능한 배포 단계** 창에서 배포 구성에 추가할 단계를 선택하고 \(**\>**\) 버튼을 선택한 다음 **확인** 버튼을 선택합니다.  
  
    > [!NOTE]  
    >  배포 전 명령이나 배포 후 명령을 구성한 경우 사용자 지정 배포 구성에 이러한 단계를 추가해야만 단계가 실행됩니다.  
  
## 활성 배포 구성 변경  
  
#### 활성 배포 구성을 변경하려면  
  
1.  **솔루션 탐색기** 에서 SharePoint 프로젝트를 선택한 다음, 메뉴 표시줄에서 **프로젝트**, *ProjectName* **속성** 을 선택합니다.  
  
2.  **SharePoint** 탭을 선택합니다.  
  
3.  **활성 배포 구성** 목록 상자에서 사용할 배포 구성의 이름을 선택 합니다.  
  
## 참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  