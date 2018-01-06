---
title: "방법: 배포, 게시 및 원격 서버에 SharePoint 솔루션 업그레이드 | Microsoft Docs"
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
helpviewer_keywords:
- remote deployment [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, remote deployment
- deploying [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, deploying
ms.assetid: d9c67fae-d097-4e26-a2b9-0f72ff800987
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 519f40017fff5dd3241f4563c5a85d0d0d15c01b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-deploy-publish-and-upgrade-sharepoint-solutions-on-a-remote-server"></a>방법: 원격 서버에서 SharePoint 솔루션 배포, 게시 및 업그레이드
  로컬 시스템에 SharePoint 솔루션을 배포 하는 것 외에도 원격 사이트 또는 로컬 SharePoint 사이트 샌드박스 SharePoint 솔루션을 게시할 수 있습니다. 원격 게시 프로세스 SharePoint 서버에.wsp 파일을 복사 하 고 솔루션을 설치 하면 솔루션을 활성화할 수 있습니다. 변경한 후에 원격 SharePoint 솔루션 설치를 업그레이드할 수 있습니다.  
  
## <a name="to-publish-a-sandboxed-sharepoint-solution-to-a-remote-sharepoint-server"></a>원격 SharePoint 서버에 샌드박스 SharePoint 솔루션을 게시 하려면  
  
1.  **솔루션 탐색기**를 게시 하 고 다음을 선택 하려는 샌드박스 SharePoint 프로젝트에 대 한 바로 가기 메뉴를 열고 **게시**합니다.  
  
2.  에 **게시** 대화 상자에서 선택 하는 **SharePoint 사이트에 게시** 옵션 단추를 선택한 다음 예와 같이 온라인 게시 사이트에 대 한 URL을 입력 한 다음: **https:// mytestsite.sharepoint.microsoftonline.com**합니다.  
  
3.  선택 된 **게시 후 브라우저에서 솔루션 갤러리 페이지를 엽니다** 에서 솔루션의 목록을 보려면 옵션 단추는 **솔루션 갤러리** 게시 한 후 페이지입니다.  
  
4.  선택 된 **게시** 단추입니다.  
  
5.  사용자 인증이 필요한 경우 원격 서버에 로그온 합니다.  
  
     Visual Studio에 게시 진행률이 표시 **출력** 창. 프로세스가 완료 되 면 솔루션 (.wsp) 파일이 원격 SharePoint 서버에 설치 됩니다. 그러나 여전히 활성화 해야 SharePoint에서 사용할 수 있습니다.  
  
6.  에 **솔루션 갤러리** 페이지 SharePoint 응용 프로그램을 선택 하 고 리본에서 선택 합니다는 **Activate** 단추입니다.  
  
7.  에 **활성화 솔루션** 대화 상자를 리본에서 선택은 **활성화** 단추를 다시 합니다.  
  
     **상태** 열에는 **솔루션 갤러리** 페이지 응용 프로그램 활성화 되어 있음을 나타냅니다.  
  
## <a name="to-upgrade-a-sandboxed-sharepoint-solution-on-a-remote-sharepoint-server"></a>원격 SharePoint 서버에 샌드박스 SharePoint 솔루션을 업그레이드 하려면  
 다음 프로세스에서 응용 프로그램에 변경한 후 업그레이드를 하면 샌드박스 SharePoint 솔루션을 원격 서버에 이미 게시 하는 경우 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
1.  SharePoint 패키지의 이름 바꾸기 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. 이 수행 하려면 **솔루션 탐색기** 패키지를 엽니다. 에 표시 되는 **패키지 탐색기**합니다.  
  
2.  **패키지 탐색기**에 **이름** 패키지 이름을 고유한 이름으로 변경 합니다.  
  
3.  프로젝트를 저장합니다.  
  
4.  **솔루션 탐색기**를 프로젝트에 대 한 바로 가기 메뉴를 열고 다음 선택 **게시**합니다.  
  
5.  에 **게시** 대화 상자에서 선택 하는 **SharePoint 사이트에 게시** 옵션 단추를 선택한 솔루션 저장 되는 원격 서버에 대 한 URL이 없는 경우 다음을 입력 합니다.  
  
6.  선택 된 **게시 후 브라우저에서 솔루션 갤러리 페이지를 엽니다** 에서 솔루션의 목록을 보려면 옵션 단추는 **솔루션 갤러리** 게시 한 후 페이지입니다.  
  
7.  선택 된 **게시** 단추입니다.  
  
8.  사용자 인증이 필요한 경우 원격 서버에 로그온 합니다.  
  
     로그인 한 경우 원격 서버에 최근에, 인증 되지 필요할 수 있습니다.  
  
     이름이 같은 응용 프로그램의 이전 버전 SharePoint 서버에 여전히 있는 경우 같은 이름의 패키지 SharePoint 서버에 이미 존재 하는 오류를 얻게 됩니다. 게시 하기 전에 고유한 이름으로 패키지 이름을 바꿔야 합니다.  
  
9. Sharepoint에서 새 응용 프로그램을 선택한 다음 리본 메뉴는 **업그레이드** 단추입니다.  
  
10. 에 **솔루션 업그레이드** 대화 상자를 리본에서 선택 된 **업그레이드** 단추를 다시 합니다. **상태** 열에는 **솔루션 갤러리** 페이지 이제 응용 프로그램이 활성화 되어 있음을 나타냅니다.  
  
     이전 버전의 솔루션 비활성화 되어, 이전 솔루션에서 유지 관리 하는 데이터와 새 버전의 솔루션 업그레이드 하 고 새 솔루션 SharePoint에서 활성화 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: SharePoint 솔루션을 로컬 SharePoint 사이트에 게시 및 배포](../sharepoint/how-to-deploy-and-publish-a-sharepoint-solution-to-a-local-sharepoint-site.md)   
 [SharePoint 솔루션 패키지 만들기](../sharepoint/creating-sharepoint-solution-packages.md)   
 [방법: SharePoint 솔루션 패키지 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)   
 [방법: 패키지 디자이너를 사용하여 패키지에 기능과 항목 추가 및 제거](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)  
  
  