---
title: "방법: 로컬 SharePoint 사이트에 SharePoint 솔루션 배포 및 게시"
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
  - "배포[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 배포"
ms.assetid: 73f8d6a9-4c64-4bba-ae0e-9474baf8df26
caps.latest.revision: 18
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# 방법: 로컬 SharePoint 사이트에 SharePoint 솔루션 배포 및 게시
  개발 컴퓨터의 지역 SharePoint 서버에 SharePoint 솔루션을 배포하거나 게시할 수 있습니다.  배포 프로세스에서는 .wsp 파일을 SharePoint 서버로 복사하고 솔루션을 설치한 다음 기능을 활성화합니다.  게시 프로세스만 .wsp 파일을 SharePoint 서버에 복사하고 설치 합니다.  이것을 SharePoint에서 사용하기 위해 수동으로 활성화 해야 합니다.  
  
## 로컬 SharePoint 서버에 SharePoint 솔루션을 배포하려면  
  
1.  **솔루션 탐색기**에서 배포할 프로젝트를 선택합니다.  
  
2.  메뉴 모음에서 **빌드**, **솔루션 배포**를 선택합니다.  
  
     로컬 SharePoint 서버에 .wsp 파일이 만들어지고 설치됩니다.  또한 기능들이 활성화됩니다.  
  
## 로컬 SharePoint 서버에 SharePoint 솔루션을 게시하려면  
  
1.  **솔루션 탐색기**에서, 게시하려는 프로젝트에 대한 바로 가기 메뉴를 연 후 **게시**를 선택합니다.  
  
2.  **게시** 대화 상자에서 **파일 시스템에 게시** 옵션 버튼을 선택합니다.  
  
3.  **대상 위치** 텍스트 상자에서 로컬 경로를 입력한 다음 **게시** 버튼을 선택합니다.  
  
     게시 진행률이 Visual Studio **출력** 창에 표시됩니다.  프로세스가 완료되면 솔루션 \(.wsp\) 파일이 로컬 SharePoint 서버에 설치 됩니다.  그러나, 이것을 SharePoint에서 사용하려면 여전히 활성화 되야 합니다.  솔루션 파일이 이미 존재할 경우, 오류가 발생하고 기존 파일을 덮어쓸 것인지 묻는 메시지가 나타납니다.  패키지 업그레이드에 대한 자세한 내용은 [방법: 원격 서버에서 SharePoint 솔루션 배포, 게시 및 업그레이드](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md) 의 원격 패키지 업그레이드 절을 참조하십시오.  
  
## 참고 항목  
 [방법: 원격 서버에서 SharePoint 솔루션 배포, 게시 및 업그레이드](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md)   
 [SharePoint 솔루션 패키지 만들기](../sharepoint/creating-sharepoint-solution-packages.md)   
 [방법: SharePoint 솔루션 패키지 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)   
 [방법: 패키지 디자이너를 사용하여 패키지에 기능과 항목 추가 및 제거](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)  
  
  