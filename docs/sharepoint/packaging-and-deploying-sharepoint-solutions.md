---
title: "SharePoint 솔루션 패키징 및 배포 | Microsoft Docs"
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
- packaging [SharePoint development in Visual Studio]
- deploying [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, packaging and deploying
ms.assetid: 39072fa7-9f94-49c0-9a67-cbcce0147e61
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 362667d4f07acb7a6c245247b40911be35479b96
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="packaging-and-deploying-sharepoint-solutions"></a>SharePoint 솔루션 패키징 및 배포
  일반적으로 SharePoint 솔루션 솔루션 패키지 (.wsp) 파일을 사용 하 여 SharePoint 서버에 배포 됩니다. SharePoint 프로젝트 항목 기능으로 구성 하 고 SharePoint 기능을 배포할 패키지를 만들려면 Visual Studio를 사용할 수 있습니다.  
  
 이 항목에서는 다음 내용에 대해 설명합니다.  
  
-   [기능 및 패키지 만들기](#Creating)  
  
-   [기능 및 패키징 도구 지원](#Tools)  
  
-   [SharePoint 솔루션 배포](#Deploying)  
  
-   [SharePoint 솔루션에 파일을 배포](#DeployingFiles)  
  
##  <a name="Creating"></a>기능 및 패키지 만들기  
 Visual Studio를 사용 하 여 관련된 SharePoint 요소를 그룹화 하는 *기능*합니다. 예를 들어 연락처 목록 정의 대 한 기능 목록 인스턴스 및 목록 정의 포함할 수 있습니다. 이 두 요소를 하나의 기능 배포 목적으로 결합할 수 있습니다. 기능에 대 한 자세한 내용은 참조 [문서 블록: 기능](http://go.microsoft.com/fwlink/?LinkID=169183)합니다.  
  
 다음으로, SharePoint 솔루션 패키지 (.wsp)를 단일 패키지에 여러 기능, 사이트 정의 어셈블리 및 기타 파일을 번들로 묶는 SharePoint 서버에 파일을 배포 하는 데 필요한 형식으로 파일을 저장 하는 만들 수 있습니다. 자세한 내용은 참조 [문서 블록: 솔루션](http://go.microsoft.com/fwlink/?LinkID=169186)합니다.  
  
##  <a name="Tools"></a>기능 및 패키징 도구 지원  
 신속 하 게 기능 및 솔루션 패키지를 쉽게 배포할으로 SharePoint 파일을 구성 하는 Visual Studio에서 SharePoint 개발 도구를 사용할 수 있습니다. 기능 및 솔루션 패키지를 구성 하려면 다음 도구를 사용할 수 있습니다.  
  
-   기능 디자이너 및 패키지 디자이너를 제공 합니다.  
  
-   패키징 탐색기, 도구 창  
  
-   솔루션 탐색기입니다.  
  
### <a name="feature-designer-and-package-designer"></a>기능 디자이너 및 패키지 디자이너  
 기능을 만드는, 범위를 설정 하 고 기능 디자이너를 사용 하 여 다른 기능 종속성으로 표시할 수 있습니다. 디자이너에는 각 기능을 설명 하는 최종 XML 파일을 표시 됩니다. 자세한 내용은 참조 [SharePoint 기능 만들기](../sharepoint/creating-sharepoint-features.md)합니다.  
  
 설정 하 여 특정 웹 사이트 또는 웹 사이트의 그룹에 기능을 적용 해당 *범위* 기능 디자이너에서 합니다. 개별 웹 사이트에 대 한 기능을 활성화, 기능 특정 웹 사이트에만 작동 합니다. 사이트 모음에 대 한 기능이 활성화 된 기능에 있는 항목 전체 사이트 컬렉션에 적용 됩니다. 자세한 내용은 참조 [요소 범위](http://go.microsoft.com/fwlink/?LinkID=169189)합니다.  
  
 기능이 기타 기능을 필요로 하는 경우 설정할 수 있습니다는 *기능 활성화 종속성* 기능을 사용할 수 있도록 설정 하기 전에 종속 된 기능을 표시 합니다. 기능 활성화 종속성 종속 기능 해당 범위에서 이미 활성화 되어 확인 합니다. 자세한 내용은 참조 [활성화 종속성 및 범위](http://go.microsoft.com/fwlink/?LinkID=169190)합니다.  
  
 패키지 디자이너에서 SharePoint 요소는 단일 솔루션 패키지를 그룹화 수 있으며 배포 하는 동안 웹 서버를 다시 설정 여부를 구성할 수 있습니다. 배포 서버 유형을 설정 하려면는 **속성** 창. 또한 디자이너는 패키지 내용에 설명 하는 XML 파일을 생성 합니다. 자세한 내용은 참조 [SharePoint 솔루션 패키지 만들기](../sharepoint/creating-sharepoint-solution-packages.md)합니다.  
  
 배포 하는 동안 인터넷 정보 서비스 (IIS) 서비스는 SharePoint 서버에 솔루션 파일을 복사할 중지 됩니다. Visual Studio에서 패키지 디자이너를 사용 하면 웹 서버를 다시 시작 해야 하는지 여부를 선택할 수 있습니다. 솔루션은 프런트 엔드 웹 서버 또는 응용 프로그램 서버에 배포 되 면을 구성 하려면 사용 된 **속성** 창. 자세한 내용은 참조 [솔루션 요소 (솔루션)](http://go.microsoft.com/fwlink/?LinkID=169191)합니다.  
  
### <a name="packaging-explorer"></a>패키징 탐색기  
 기능 디자이너 및 패키지 디자이너를 보완 하기 위해 파일을 그룹화 하려면 SharePoint 기능 및 패키지에 패키징 탐색기를 사용할 수 있습니다. 패키지 기능을 SharePoint 프로젝트의 계층 구조 보기에서 볼 수는 또한 항목 및 파일입니다. 패키징 탐색기는 다음 작업을 완료 하는 데 사용할 수 있는 도구 창:  
  
-   SharePoint 프로젝트 항목 및 파일을 엽니다.  
  
-   다른 기능 중 하나에서 SharePoint 프로젝트 항목을 끌어서 설정.  
  
-   끌어서 한 패키지에서 다른 SharePoint 프로젝트 항목 및 기능을 놓습니다.  
  
-   패키지에 새 기능을 추가 합니다.  
  
-   기능 또는 패키지 디자이너를 엽니다.  
  
-   기능 및 패키지의 유효성을 검사 합니다.  
  
 Visual Studio에서 SharePoint 개발 도구는 솔루션 패키지가 올바르게 생성 되었는지 확인 하려면 유효성 검사 규칙을 갖습니다. 또한 규칙.wsp 솔루션 파일 수 수 성공적으로 배포 및 활성화 되었는지 확인 SharePoint 서버에 있습니다. 기능에 대 한 XML 스키마에 대 한 자세한 내용은 참조 [기능 스키마](http://go.microsoft.com/fwlink/?LinkID=169192)합니다.  
  
 SharePoint 프로젝트 시스템에 사용자 지정 기능 및 패키지 유효성 검사 규칙을 추가할 수 있습니다. 자세한 내용은 참조 [하는 방법: 사용자 지정 기능 및 패키지 유효성 검사 규칙 만들기 SharePoint 솔루션에 대 한](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md)합니다.  
  
 패키징 탐색기에 대 한 자세한 내용은 참조 [하는 방법: 패키징 탐색기를 사용 하 여 패키지에 기능과 항목을 제거 하 고 추가](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer.md)합니다.  
  
### <a name="solution-explorer"></a>솔루션 탐색기  
 솔루션 탐색기를 사용 하 여 탐색 하 고 SharePoint 프로젝트의 파일을 열 수 있습니다. 솔루션 탐색기에서 상황에 맞는 메뉴를 사용 하 여 기능 이벤트 수신자 기능을 추가 하 고 기능 리소스. 또한 디자이너 기능 및 패키지 디자이너 기능 및 배포에 대 한 패키지를 구성 하는 열 수 있습니다.  
  
##  <a name="Deploying"></a>SharePoint 솔루션 배포  
 기능 및 Visual Studio에서 패키지를 사용자 지정한 후에 SharePoint 서버를 배포 하려면.wsp 파일을 만들 수 있습니다. Visual Studio 디버깅 하 고 개발 컴퓨터에 SharePoint 서버에만.wsp 테스트에 사용할 수 있습니다. 원격 SharePoint 서버에 SharePoint 솔루션을 배포 하는 방법에 대 한 자세한 내용은 참조 [솔루션 배포](http://go.microsoft.com/fwlink/?LinkID=169194)합니다.  
  
 또한 개발 컴퓨터에서 배포 단계를 사용자 지정할 수 있습니다. 자세한 내용은 참조 [배포, 게시 및 SharePoint 솔루션 패키지 업그레이드](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md)합니다.  
  
##  <a name="DeployingFiles"></a>SharePoint 솔루션에 파일을 배포  
 일반적으로 SharePoint 솔루션을 SharePoint 프로젝트 항목을 추가할 때 필요한 모든 파일이 포함 됩니다. 수 있는 파일 (코드 파일) 컴파일된 솔루션의 출력 어셈블리에 기본 제공 됩니다. 그러나 SharePoint 프로젝트에 호환 파일을.xml,.txt 또는 리소스 파일 추가 할 수 있습니다. 이러한 파일은 자동으로 솔루션에 패키지 되지 않습니다. 패키지를 보장 하려면 SharePoint 프로젝트 항목 또는 매핑된 폴더에 파일 추가 합니다.  
  
 솔루션을 배포할 때 SharePoint 하이브에 매핑된 폴더에 추가 된 파일 자동으로 복사 됩니다. SharePoint 프로젝트 항목에 추가 된 파일에 지정 된 위치에 배포 되는 **배포 위치** 부분적으로 설정 되는 각 파일에 대 한 속성에 따라는 **배포 유형을** 속성입니다. 기본적으로는 **배포 유형을** 속성 값은 **NoDeployment**, 솔루션 파일 배포 되지 않은 의미 합니다. 패키지에 파일을 포함 하도록 속성에 대 한 다른 값을 설정 해야 합니다.  
  
 예를 들어.xml 파일을 SharePoint 프로젝트를 추가 하려면 다음이 작업 중 하나를 수행 합니다.  
  
-   SharePoint "레이아웃" 매핑된 폴더를 프로젝트에 추가 합니다. 그러면에 생성 되 **솔루션 탐색기** 라는 폴더 **레이아웃** 있는 프로젝트에 대 한 하위 폴더입니다. 새 하위 폴더에.xml 파일을 추가 합니다. 기본적으로 파일에서 SharePoint 파일 시스템에 배포 됩니다. \TEMPLATE\LAYOUTS\\*폴더 이름*\\합니다. 매핑된 폴더를 추가 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 매핑된 폴더 추가 및 제거](../sharepoint/how-to-add-and-remove-mapped-folders.md)합니다.  
  
-   SharePoint 프로젝트 항목의 폴더에.xml 파일을 추가 하 고 다음 변경 된 **배포 유형을** 에서.xml 파일의 속성 **NoDeployment** 와 같은 다른 설정에 **RootFile** 또는 **ElementFile**합니다. 적절 한 **배포 유형을** 설정은 파일과 프로젝트에 따라 다릅니다. 에 대 한 자세한 내용은 **배포 유형을** 속성 설정, 참조 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)합니다.  
  
 추가 된 파일이 솔루션에 특정 프로젝트에 적용 되지 않고 경우 솔루션에 빈 SharePoint 프로젝트를 추가할 수 있으며를 추가 하는 파일을 추가 합니다. 특히 콘텐츠 데이터베이스를 SharePoint에 파일을 배포 하기 위한 또 다른 방법은 프로젝트에 모듈을 추가 하 고 다음 모듈에 파일을 추가 하는 것입니다. 자세한 내용은 참조 [솔루션에 파일 포함을 사용 하 여 모듈](../sharepoint/using-modules-to-include-files-in-the-solution.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)   
 [SharePoint 솔루션 빌드 및 디버깅](../sharepoint/building-and-debugging-sharepoint-solutions.md)  
  
  