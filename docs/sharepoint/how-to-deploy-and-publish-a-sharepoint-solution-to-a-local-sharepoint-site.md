---
title: "방법: SharePoint 솔루션을 로컬 SharePoint 사이트에 게시 및 배포 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
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
manager: ghogen
ms.workload: office
ms.openlocfilehash: b5b3ab297612ec48027af8d4eb74956d1d255443
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-deploy-and-publish-a-sharepoint-solution-to-a-local-sharepoint-site"></a>방법: 로컬 SharePoint 사이트에 SharePoint 솔루션 배포 및 게시
  배포 또는 개발 컴퓨터에서 로컬 SharePoint 서버에 SharePoint 솔루션을 게시할 수 있습니다. 배포 프로세스는 SharePoint 서버에.wsp 파일을 복사, 솔루션을 설치 및 다음 기능을 활성화 합니다. 게시 프로세스는만 SharePoint 서버에.wsp 파일을 복사 하 고 설치 합니다. SharePoint에서 사용 하도록 설정 하는 것을 수동으로 활성화 해야 합니다.  
  
## <a name="to-deploy-a-sharepoint-solution-to-the-local-sharepoint-server"></a>로컬 SharePoint 서버에 SharePoint 솔루션을 배포 하려면  
  
1.  **솔루션 탐색기**를 배포 하려는 프로젝트를 선택 합니다.  
  
2.  메뉴 모음에서 **빌드**, **솔루션 배포**합니다.  
  
     .Wsp 파일을 만들고 로컬 SharePoint 서버에 설치 됩니다. 또한 기능이 활성화 됩니다.  
  
## <a name="to-publish-a-sharepoint-solution-to-a-local-sharepoint-server"></a>로컬 SharePoint 서버에 SharePoint 솔루션을 게시 하려면  
  
1.  **솔루션 탐색기**를 게시 한 다음 선택 하려는 SharePoint 프로젝트에 대 한 바로 가기 메뉴를 열고 **게시**합니다.  
  
2.  에 **게시** 대화 상자에서 선택 하는 **파일 시스템에 게시** 옵션 단추입니다.  
  
3.  에 **대상 위치** 텍스트 상자에는 로컬 경로 입력 한 다음 선택에서 **게시** 단추입니다.  
  
     Visual Studio에 게시 진행률이 표시 **출력** 창. 프로세스가 완료 되 면 솔루션 (.wsp) 파일이 로컬 SharePoint 서버에 설치 됩니다. 그러나 SharePoint에 사용할 활성화 계속 해야 합니다. 솔루션 파일이 이미 존재 하는 경우 오류가 발생 하 고 기존 파일을 덮어쓸 것인지 여부를 묻는 합니다. 원격 패키지를 업그레이드 패키지를 업그레이드에 대 한 내용은 섹션을 참조 [하는 방법: 게시 및 원격 서버에 SharePoint 솔루션 업그레이드 배포](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 배포, 게시 및 원격 서버에 SharePoint 솔루션 업그레이드](../sharepoint/how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server.md)   
 [SharePoint 솔루션 패키지 만들기](../sharepoint/creating-sharepoint-solution-packages.md)   
 [방법: SharePoint 솔루션 패키지 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)   
 [방법: 패키지 디자이너를 사용하여 패키지에 기능과 항목 추가 및 제거](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)  
  
  