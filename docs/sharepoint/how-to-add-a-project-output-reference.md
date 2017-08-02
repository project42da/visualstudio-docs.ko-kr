---
title: "방법: 프로젝트 출력 참조 추가"
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
  - "프로젝트 출력 참조[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 고급 패키징 도구"
  - "Visual Studio에서 SharePoint 개발, 프로젝트 출력 참조"
ms.assetid: 9d6bc25e-bf0d-4483-a691-2ad7a796fa80
caps.latest.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# 방법: 프로젝트 출력 참조 추가
  비 SharePoint 프로젝트 어셈블리\(또는 Silverlight 프로젝트의 .xap 파일\)를 SharePoint에 배포하려면 해당 어셈블리를 프로젝트 출력 참조로 추가합니다.  
  
 이 프로세스에서는 두 프로젝트 간에 솔루션 빌드 종속성을 만듭니다.  프로젝트 출력 참조와 연결된 프로젝트는 SharePoint 프로젝트가 빌드되고 배포되기 전에 빌드됩니다.  
  
### 프로젝트 출력 참조를 추가하려면  
  
1.  SharePoint 프로젝트가 하나 이상 포함되고 비 SharePoint 프로젝트가 하나 포함된 솔루션을 로드합니다.  
  
2.  **솔루션 탐색기**에서 SharePoint 프로젝트 노드의 항목을 클릭합니다.  
  
3.  **속성** 창에서 **프로젝트 출력 참조** 속성을 선택한 다음 그 옆의 줄임표\(![ASP.NET 모바일 디자이너 줄임표](~/docs/sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표")\) 버튼을 선택합니다.  
  
4.  **프로젝트 출력 참조** 대화 상자에서 **추가** 버튼을 선택합니다.  
  
5.  속성 창에서 **배포 형식** 속성 옆의 드롭다운 화살표를 선택한 다음, 참조하고 있는 비 SharePoint 항목에 적절한 값을 선택합니다\(예: **ElementFile**\).  
  
6.  **프로젝트 이름** 옆에 있는 화살표를 선택하고, 비 SharePoint 프로젝트 항목의 이름을 선택한 다음, **확인** 버튼을 선택합니다.  
  
## 참고 항목  
 [프로젝트 항목에 패키징 및 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [방법: 컨트롤을 안전 컨트롤로 표시](../sharepoint/how-to-mark-controls-as-safe-controls.md)   
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  