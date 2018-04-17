---
title: 배포, 게시, 및 SharePoint 솔루션 패키지를 업그레이드 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.SharePointProjectPropertyTab
- VS.SharePointTools.Project.Publishing
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- deploying [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, deploying
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: aac96c7954a52a3277b08efcd89fa24a743117be
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="deploying-publishing-and-upgrading-sharepoint-solution-packages"></a>SharePoint 솔루션 패키지 배포, 게시 및 업그레이드
  Visual Studio에서 SharePoint 솔루션을 개발한 후 로컬 SharePoint 서버에 해당 패키지 (.wsp) 파일을 배포 하거나 원격 또는 로컬 SharePoint 서버에 게시할 수 있습니다. 파일을 배포 하는 경우 패키지 파일 (.wsp) 배포 되는 방식을 사용자 지정할 수 있습니다.  
  
> [!NOTE]  
>  현재 원격 SharePoint 서버에만 샌드박스 솔루션을 게시할 수 있습니다. 자세한 내용은 참조 [샌드박스 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)합니다.  
  
## <a name="deploying-publishing-and-upgrading"></a>배포, 게시 및 업그레이드  
 *배포* 참조 하는 로컬 호스트에 Visual Studio에서 SharePoint 프로젝트에서 빌드된 SharePoint 솔루션 파일을 복사 합니다. 배포 된 솔루션에서 솔루션을 배포 후 활성화 인터넷 정보 서비스 (IIS) 풀을 재활용 하는 등 배포 단계를 구성할 수 있으며 등 수 있습니다. 를 배포 하려면 사용 된 **배포** 명령을 **빌드** 메뉴. 자세한 내용은 참조 [하는 방법: SharePoint 배포 구성 편집](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md) 및 [하는 방법: SharePoint 솔루션을 로컬 SharePoint 사이트에 게시 및 배포](../sharepoint/how-to-deploy-and-publish-a-sharepoint-solution-to-a-local-sharepoint-site.md)합니다.  
  
 *게시* 참조 원격 sharepoint sandboxed SharePoint 솔루션 파일을 업로드 하 여 사이트, 즉 다른 시스템에 있는 사이트입니다. 로컬 SharePoint 사이트에는 SharePoint 샌드박스 솔루션 파일을 게시할 수도 있지만 인지 사이트에 게시 된 로컬 또는 원격에 관계 없이 해당 배포 단계를 구성할 수 없습니다.  
  
 *업그레이드* 기존 원격 또는 로컬로 게시 SharePoint 솔루션에 업데이트를 참조 합니다. Visual Studio에서 SharePoint 솔루션에 변경 된 후 솔루션의 패키지 파일 이름, 솔루션을 다시 게시 바꾸고 성공적으로 다시 게시 한 후 솔루션을 업그레이드 합니다. 로컬 게시 된 솔루션을 다시 게시할 경우 기존 솔루션 파일을 덮어쓸 수 있습니다.  
  
## <a name="deploying-packages"></a>패키지 배포  
 테스트 및 디버깅을 위한 개발 컴퓨터에 SharePoint 서버에 패키지 파일을 배포할 수 있습니다. 선택 하 여 다른 컴퓨터에 설치할 수 있는 패키지 파일을 만들 수도 있습니다는 **파일 시스템에 게시** 옵션 단추는 **게시** 대화 상자. 패키지를 만들고 지정 된 로컬 파일 경로에 복사 합니다. SharePoint 솔루션을 로컬 서버를 배포 하려면 사용 된 **배포** 명령을 **빌드** 메뉴. 자세한 내용은 참조 [하는 방법: SharePoint 솔루션을 로컬 SharePoint 사이트에 게시 및 배포](../sharepoint/how-to-deploy-and-publish-a-sharepoint-solution-to-a-local-sharepoint-site.md)합니다.  
  
 목록 정의 배포, 이벤트 수신기 추가 및 디자이너 기능 및 패키지 디자이너를 사용 하는 방법을 알아보려면 참조 [연습: 프로젝트 작업 목록 정의 배포](../sharepoint/walkthrough-deploying-a-project-task-list-definition.md)합니다.  
  
## <a name="customizing-the-deployment-process"></a>배포 프로세스를 사용자 지정  
 다음 표에서 디버그 하 고 SharePoint 솔루션을 배포할 때 사용할 수 있는 두 개의 배포 구성을 보여 줍니다.  
  
|배포 구성|설명|  
|------------------------------|-----------------|  
|기본|기본 배포 구성입니다. 다음과 같은 배포 단계가 수행 됩니다.<br /><br /> 1.  배포 전 명령을 실행 합니다.<br />2.  IIS 응용 프로그램 풀을 재활용 합니다.<br />3.  솔루션을 취소 합니다.<br />4.  솔루션을 추가 합니다.<br />5.  기능을 활성화 합니다.<br />6.  배포 후 명령을 실행 합니다.<br /><br /> 패키지를 제거 하면 다음 제거 단계가 수행 됩니다.<br /><br /> 1.  IIS 응용 프로그램 풀을 재활용 합니다.<br />2.  솔루션을 취소 합니다.|  
|정품 인증 없음|이 배포 구성을 기본 구성으로 동일한 단계를 실행 하지만 정품 인증 단계를 건너뜁니다.|  
  
 단일 단계를 완료 하거나 배포 프로세스의 단계 순서를 변경 하려면 고유한 배포 구성을 만들 수 있습니다. 자세한 내용은 참조 [하는 방법: SharePoint 배포 구성 편집](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md)합니다.  
  
 또한 배포 전후 실행할 명령을 추가할 수 있습니다. 자세한 내용은 참조 [하는 방법: SharePoint 배포 명령 설정](../sharepoint/how-to-set-sharepoint-deployment-commands.md)합니다.  
  
## <a name="publishing-packages-to-a-remote-or-local-server"></a>패키지를 원격 또는 로컬 서버에 게시  
 메뉴 모음에서 원격 서버에 샌드박스 SharePoint 솔루션을 게시 하려면 선택 **빌드**, **게시**를 선택한 후는 **게시** 대화 상자에서 선택 하 고 **SharePoint 사이트에 게시** 와 같은 원격 서버의 URL을 제공 하는 옵션 단추를 **https://someremoteserver.sharepoint.microsoftonline.com**합니다.  
  
 로컬 서버에 SharePoint 솔루션을 게시 하는 **게시** 대화 상자에서 선택 하는 **파일 시스템에 게시** 옵션 단추를 로컬 시스템 경로 제공 합니다.  
  
 솔루션을 성공적으로 SharePoint에 게시 하면 솔루션에 표시는 **솔루션 갤러리** 를 활성화할 수 있습니다. 자세한 내용은 참조 [하는 방법: 게시 및 원격 서버에 SharePoint 솔루션 업그레이드 배포](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md)합니다.  
  
### <a name="upgrading-published-packages"></a>게시 된 패키지를 업그레이드합니다.  
 모든 변경 하면 Visual Studio에서 SharePoint 프로젝트에 게시 된 후, 변경 내용을 포함 하려면 게시 된 패키지를 업그레이드 해야 합니다. 를 성공적으로 업그레이드 하려면 패키지에 고유한 이름이 있어야 합니다. 동일한 이름 사용 하 여 패키지 오류 경고는 기존 응용 프로그램을 업데이트 하는 경우 발생할 수 있습니다-하는 SharePoint 사이트에서 발견 되 충돌 수 파일 이름 및 패키지의 이름을 바꿀 수입니다. 다시 게시 하지 후 새 패키지는 SharePoint 사이트에 표시 되 고 업그레이드할 수 있습니다. 오래 된 패키지의 데이터를 사용 하 여 솔루션을 업데이트 하 고 SharePoint에서 솔루션을 활성화 하는 업그레이드 된 패키지입니다. 자세한 내용은 참조 [하는 방법: 게시 및 원격 서버에 SharePoint 솔루션 업그레이드 배포](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  