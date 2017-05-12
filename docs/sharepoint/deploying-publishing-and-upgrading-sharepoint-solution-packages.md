---
title: "SharePoint 솔루션 패키지 배포, 게시 및 업그레이드"
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
  - "VS.SharePointTools.Project.SharePointProjectPropertyTab"
  - "VS.SharePointTools.Project.Publishing"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "배포[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 배포"
ms.assetid: 5efc1d99-2bd2-4f1a-a7b0-86c3b8f533f0
caps.latest.revision: 23
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 22
---
# SharePoint 솔루션 패키지 배포, 게시 및 업그레이드
  Visual Studio 에서 SharePoint 솔루션을 개발한 후, 로컬 SharePoint 서버에 해당 패키지 파일 \(.wsp\)를 배포 하거나 원격 또는 로컬 SharePoint 서버에 게시 합니다.  파일을 배포하는 경우, 패키지 파일 \(.wsp\)를 배포 하는 방법을 사용자 지정할 수 있습니다.  
  
> [!NOTE]  
>  현재 샌드박스가 적용된 솔루션만 원격 SharePoint 서버에 게시할 수 있습니다.  자세한 내용은 [샌드박스가 적용된 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)을 참조하십시오.  
  
## 게시, 배포 및 업그레이드  
 *배포* 는 Visual Studio의 SharePoint 프로젝트로 부터 로컬 호스트로 SharePoint 솔루션 파일을 복사하는 것을 참조 합니다.  배포된 솔루션에서, 인터넷 정보 서비스 \(IIS\) 풀을 재활용하거나 배포 후 솔루선 활성화와 같은 배포 단계를 구성할 수 있습니다.  배포를 하기 위해 **빌드** 메뉴에서 **배포** 명령을 사용합니다.  자세한 내용은 [방법: SharePoint 배포 구성 편집](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md) 및 [방법: 로컬 SharePoint 사이트에 SharePoint 솔루션 배포 및 게시](../sharepoint/how-to-deploy-and-publish-a-sharepoint-solution-to-a-local-sharepoint-site.md)를 참조하십시오.  
  
 *게시* 는 원격 SharePoint 사이트, 즉 다른 시스템에 있는 사이트로 SharePoint 샌드박스 솔루션 파일을 업로드하는것을 의미합니다.  로컬 SharePoint 사이트로 SharePoint 샌드박스 솔루션 파일을 게시할 수도 있지만, 사이트가 로컬 또는 원격에 게시된 것과 관계 없이 해당 배포 단계를 구성할 수 없습니다.  
  
 *업그레이드* 는 기존의 원격으로 또는 로컬로 게시된 SharePoint 솔루션을 업로드 하는것을 말합니다.  Visual Studio의 SharePoint 솔루션에서 변화가 생성된 후, 솔루션의 패키지 파일 이름을 변경하고, 솔루션을 다시 게시한 다음, 성공적으로 다시 게시한 후 솔루션을 업그레이드 합니다.  로컬로 게시된 솔루션을 다시 게시하는 경우, 기존 솔루션 파일을 덮어쓸 수 있습니다.  
  
## 패키지 배포  
 테스트 및 디버깅을 위해 개발 컴퓨터의 SharePoint 서버에 패키지 파일을 배포할 수 있습니다.  **게시** 대화 상자에서 **파일 시스템에 게시** 옵션 버튼을 선택하여 다른 컴퓨터에 설치할 수 있는 패키지 파일을 만들 수도 있습니다.  패키지는 지정된 로컬 파일 경로로 만들어지고 복사 합니다.  로컬 서버에 SharePoint 솔루션을 배포하려면, **빌드** 메뉴에서 **배포** 명령을 사용합니다.  자세한 내용은 [방법: 로컬 SharePoint 사이트에 SharePoint 솔루션 배포 및 게시](../sharepoint/how-to-deploy-and-publish-a-sharepoint-solution-to-a-local-sharepoint-site.md)을 참조하십시오.  
  
 목록 정의를 배포하고, 이벤트 수신자를 추가하고, 기능 디자이너 및 패키지 디자이너를 사용하는 방법은 [연습: 프로젝트 작업 목록 정의 배포](../sharepoint/walkthrough-deploying-a-project-task-list-definition.md)를 참조하십시오.  
  
## 배포 프로세스 사용자 지정  
 다음 표에서는 SharePoint 솔루션을 디버깅 및 배포할 때 사용할 수 있는 두 가지 배포 구성을 보여 줍니다.  
  
|배포 구성|설명|  
|-----------|--------|  
|기본|기본 배포 구성입니다.  다음 배포 단계가 수행됩니다.<br /><br /> 1.  배포 전 명령을 실행합니다.<br />2.  IIS 응용 프로그램 풀을 재생합니다.<br />3.  솔루션을 제거합니다.<br />4.  솔루션을 추가합니다.<br />5.  기능을 활성화합니다.<br />6.  배포 후 명령을 실행합니다.<br /><br /> 패키지를 제거하면 다음 제거 단계가 수행됩니다.<br /><br /> 1.  IIS 응용 프로그램 풀을 재생합니다.<br />2.  솔루션을 제거합니다.|  
|활성화 없음|이 배포 구성은 기본 구성과 동일한 단계를 실행하지만 활성화 단계를 건너뜁니다.|  
  
 고유한 배포 구성을 만들어 하나의 단계를 완료하거나 배포 프로세스의 단계 순서를 변경할 수 있습니다.  자세한 내용은 [방법: SharePoint 배포 구성 편집](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md)을 참조하십시오.  
  
 배포 전후에 실행할 명령을 추가할 수도 있습니다.  자세한 내용은 [방법: SharePoint 배포 명령 설정](../sharepoint/how-to-set-sharepoint-deployment-commands.md)을 참조하십시오.  
  
## 원격 또는 로컬 서버에 패키지 게시  
 원격 서버에 SharePoint 샌드박스 솔루션을 게시 하려면, 메뉴 표시줄에서 **빌드**, **게시**를 선택한 다음, **게시** 대화 상자에서 https:\/\/someremoteserver.sharepoint.microsoftonline.com와 같이 원격 서버의 URL을 제공 하는 **SharePoint 사이트에 게시** 옵션 버튼을 선택합니다.  
  
 SharePoint 솔루션을 로컬 서버에 게시 하려면, **게시** 대화 상자에서 로컬 시스템 경로를 제공하는 **파일 시스템에 게시** 옵션 버튼을 선택합니다.  
  
 SharePoint 솔루션을 성공적으로 게시한 후, 솔루션은 활성화 할수 있는 **솔루션 갤러리** 에 표시됩니다.  자세한 내용은 [방법: 원격 서버에서 SharePoint 솔루션 배포, 게시 및 업그레이드](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md)을 참조하십시오.  
  
### 게시된 패키지를 업그레이드  
 게시된 후 Visual Studio의 SharePoint 프로젝트에 변경을 만든 경우, 게시된 패키지는 이러한 변경들을 포함하기 위해 업그레이드 되야 합니다.  제대로 업그레이드 하려면 패키지에 고유한 이름이 있어야 합니다.  같은 이름의 패키지가 SharePoint 사이트에서 발견될 경우\(기존 응용 프로그램을 업데이트할 때 발생할 수 있습니다\), 파일 이름의 충돌을 오류가 발생되고 패키지 이름을 변경할 수 있도록 합니다.  다시 게시된 후 새 패키지는 SharePoint 사이트에 표시되고 업그레이드 될 수 있습니다.  업그레이드된 패키지는 오래된 패키지의 데이터를 사용하여 솔루션을 업데이트하고, SharePoint에서 솔루션을 활성화 합니다.  자세한 내용은 [방법: 원격 서버에서 SharePoint 솔루션 배포, 게시 및 업그레이드](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md)을 참조하십시오.  
  
## 참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  