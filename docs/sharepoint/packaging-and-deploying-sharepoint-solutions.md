---
title: "SharePoint 솔루션 패키징 및 배포"
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
  - "패키징[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 패키징 및 배포"
ms.assetid: 39072fa7-9f94-49c0-9a67-cbcce0147e61
caps.latest.revision: 34
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 33
---
# SharePoint 솔루션 패키징 및 배포
  일반적으로 SharePoint 솔루션은 솔루션 패키지 파일\(.wsp\)을 사용하여 SharePoint 서버에 배포됩니다.  Visual Studio를 사용하여 SharePoint 프로젝트 항목을 기능으로 구성하고 패키지를 만들어 SharePoint 기능을 배포할 수 있습니다.  
  
 이 항목에서는 다음 내용에 대해 설명합니다.  
  
-   [기능 및 패키지 만들기](#Creating)  
  
-   [기능 및 패키징 도구 지원](#Tools)  
  
-   [SharePoint 솔루션 배포](#Deploying)  
  
-   [SharePoint 솔루션의 파일 배포](#DeployingFiles)  
  
##  <a name="Creating"></a> 기능 및 패키지 만들기  
 Visual Studio를 사용하여 관련된 SharePoint 요소를 *기능*으로 그룹화할 수 있습니다.  예를 들어 연락처 목록 정의의 기능에는 목록 인스턴스와 목록 정의가 포함될 수 있습니다.  배포를 위해 이러한 두 요소를 하나의 기능으로 결합할 수 있습니다.  기능에 대한 자세한 내용은 [블록 구성: 기능](http://go.microsoft.com/fwlink/?LinkID=169183) 을 참조하십시오.  
  
 다음에는 SharePoint 솔루션 패키지\(.wsp\)를 만들어 여러 개의 기능, 사이트 정의, 어셈블리 및 기타 파일을 하나의 패키지로 번들할 수 있습니다. 이 패키지에는 SharePoint에서 파일을 서버로 배포하는 데 필요한 형식으로 파일이 저장됩니다.  자세한 내용은 [블록 구성: 솔루션](http://go.microsoft.com/fwlink/?LinkID=169186) 을 참조하십시오.  
  
##  <a name="Tools"></a> 기능 및 패키징 도구 지원  
 배포가 용이하도록 Visual Studio의 SharePoint 개발 도구를 사용하여 SharePoint 파일을 기능 및 솔루션 패키지로 신속하게 구성할 수 있습니다.  다음 도구를 사용하여 기능 및 솔루션 패키지를 구성할 수 있습니다.  
  
-   기능 디자이너 및 패키지 디자이너  
  
-   패키징 탐색기, 도구 창  
  
-   솔루션 탐색기  
  
### 기능 디자이너 및 패키지 디자이너  
 기능 디자이너를 사용하면 기능을 만들고, 범위를 설정하고, 다른 기능을 종속성으로 표시할 수 있습니다.  디자이너에는 각 기능을 설명하는 최종 XML 파일도 표시됩니다.  자세한 내용은 [SharePoint 기능 만들기](../sharepoint/creating-sharepoint-features.md)을 참조하십시오.  
  
 기능 디자이너에서 *범위*를 설정하여 특정 웹 사이트나 웹 사이트 그룹에 기능을 적용할 수 있습니다.  개별 웹 사이트에 대해 기능을 활성화하면 해당 웹 사이트에서만 기능이 작동합니다.  사이트 컬렉션에 대해 기능을 활성화하면 기능의 항목이 전체 사이트 컬렉션에 적용됩니다.  자세한 내용은 [요소 범위](http://go.microsoft.com/fwlink/?LinkID=169189) 를 참조하십시오.  
  
 기능이 다른 기능을 필요로 하는 경우 기능을 사용할 수 있도록 설정하기 전에 *기능 활성화 종속성*을 설정하여 종속된 기능을 표시할 수 있습니다.  기능 활성화 종속성을 사용하면 해당 범위에서 종속된 기능이 이미 활성화되어 있는지 여부를 확인할 수 있습니다.  자세한 내용은 [활성화 종속성 및 범위](http://go.microsoft.com/fwlink/?LinkID=169190) 을 참조하십시오.  
  
 패키지 디자이너에서 SharePoint 요소를 하나의 솔루션 패키지로 그룹화하고, 배포하는 동안 웹 서버를 다시 설정할지 여부를 구성할 수 있습니다.  배포 서버 유형을 설정하려면 **속성** 창을 사용합니다.  또한 디자이너는 패키지 내용을 설명하는 XML 파일을 생성합니다.  자세한 내용은 [SharePoint 솔루션 패키지 만들기](../sharepoint/creating-sharepoint-solution-packages.md)을 참조하십시오.  
  
 배포하는 동안 솔루션 파일을 SharePoint 서버로 복사하기 위해 IIS\(인터넷 정보 서비스\) 서비스가 중지됩니다.  Visual Studio의 패키지 디자이너를 사용하면 웹 서버를 다시 시작할지 여부를 선택할 수 있습니다.  솔루션을 프런트 엔드 웹 서버에 배포할지 응용 프로그램 서버에 배포할지 구성하려면 **속성** 창을 사용합니다.  자세한 내용은 [솔루션 요소 \(솔루션\)](http://go.microsoft.com/fwlink/?LinkID=169191) 을 참조하십시오.  
  
### 패키징 탐색기  
 기능 디자이너와 패키지 디자이너를 보완하기 위해 패키징 탐색기를 사용하여 SharePoint 파일을 기능 및 패키지로 그룹화할 수 있습니다.  또한 패키지, 기능, SharePoint 프로젝트 항목 및 파일의 계층적 뷰를 표시할 수 있습니다.  패키징 탐색기는 다음 작업을 완료하는 데 사용할 수 있는 도구 창입니다.  
  
-   SharePoint 프로젝트 항목과 파일을 엽니다.  
  
-   SharePoint 프로젝트 항목을 한 기능에서 다른 기능으로 끌어서 놓습니다.  
  
-   SharePoint 프로젝트 항목과 기능을 한 패키지에서 다른 패키지로 끌어서 놓습니다.  
  
-   패키지에 새 기능을 추가합니다.  
  
-   기능 디자이너 또는 패키지 디자이너를 엽니다.  
  
-   기능 및 패키지의 유효성을 검사합니다.  
  
 Visual Studio의 SharePoint 배포 도구에서 제공하는 유효성 검사 규칙을 사용하면 솔루션 패키지의 형식이 올바른지 쉽게 확인할 수 있습니다.  또한 이 규칙을 통해 .wsp 솔루션을 SharePoint 서버에서 성공적으로 배포 및 활성화할 수 있는지 여부도 확인할 수 있습니다.  기능의 XML 스키마에 대한 자세한 내용은 [스키마 기능](http://go.microsoft.com/fwlink/?LinkID=169192) 을 참조하십시오.  
  
 SharePoint 프로젝트 시스템에 사용자 지정 기능 및 패키지 유효성 검사 규칙을 추가할 수 있습니다.  자세한 내용은 [How to: Create Custom Feature and Package Validation Rules for SharePoint Solutions](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md)을 참조하십시오.  
  
 패키징 탐색기에 대한 자세한 내용은 [방법: 패키징 탐색기를 사용하여 패키지에 기능과 항목 추가 및 제거](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer.md)를 참조하십시오.  
  
### 솔루션 탐색기  
 솔루션 탐색기를 사용하여 SharePoint 프로젝트의 파일을 탐색하고 열 수 있습니다.  솔루션 탐색기의 상황에 맞는 메뉴를 사용하여 기능, 기능 이벤트 수신자 및 기능 리소스를 추가할 수 있습니다.  또한 기능 디자이너와 패키지 디자이너를 열어 배포를 위해 기능과 패키지를 구성할 수 있습니다.  
  
##  <a name="Deploying"></a> SharePoint 솔루션 배포  
 Visual Studio에서 기능 및 패키지를 사용자 지정한 후 SharePoint 서버에 배포할 .wsp 파일을 만들 수 있습니다.  Visual Studio를 사용하여 개발 컴퓨터의 SharePoint 서버에서만 .wsp를 디버깅하고 테스트할 수 있습니다.  원격 SharePoint 서버에 SharePoint 솔루션을 배포하는 방법에 대한 자세한 내용은 [솔루션 배포](http://go.microsoft.com/fwlink/?LinkID=169194) 을 참조하십시오.  
  
 개발 컴퓨터에서 배포 단계를 사용자 지정할 수도 있습니다.  자세한 내용은 [SharePoint 솔루션 패키지 배포, 게시 및 업그레이드](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md)을 참조하십시오.  
  
##  <a name="DeployingFiles"></a> SharePoint 솔루션의 파일 배포  
 일반적으로 SharePoint 프로젝트 항목을 SharePoint 솔루션에 추가할 때 필요한 파일이 모두 포함됩니다.  컴파일될 수 있는 파일\(코드 파일\)은 솔루션의 출력 어셈블리로 빌드됩니다.  그러나 .xml, .txt 또는 리소스 파일과 같은 컴파일할 수 없는 파일을 SharePoint 프로젝트에 추가해야 할 수도 있습니다.  이러한 파일은 솔루션에 자동으로 패키지되지 않습니다.  이러한 파일이 패키지되도록 하려면 파일을 매핑된 폴더나 SharePoint 프로젝트 항목에 추가합니다.  
  
 매핑된 폴더에 추가된 파일은 솔루션이 배포될 때 SharePoint 하이브에 자동으로 복사됩니다.  SharePoint 프로젝트 항목에 추가된 파일은 **배포 형식** 속성에 따라 부분적으로 설정되는 각 파일의 **배포 위치** 속성에 지정된 위치에 배포됩니다.  기본적으로 **배포 형식** 속성 값은 파일이 솔루션과 함께 배포되지 않음을 의미하는 **NoDeployment**입니다.  패키지에 파일을 포함하려면 속성에 다른 값을 설정해야 합니다.  
  
 예를 들어 .xml 파일을 SharePoint 프로젝트에 추가하려면 다음 작업 중 하나를 수행합니다.  
  
-   SharePoint "Layouts" 매핑된 폴더를 프로젝트에 추가합니다.  이렇게 하면 **솔루션 탐색기**에서 프로젝트에 대한 하위 폴더가 있는 **Layouts**라는 폴더가 만들어집니다.  .xml 파일을 새 하위 폴더에 추가합니다.  기본적으로 파일은 ..\\TEMPLATE\\LAYOUTS\\*Folder Name*\\ 아래의 SharePoint 파일 시스템에 배치됩니다.  매핑된 폴더를 추가하는 방법에 대한 자세한 내용은 [방법: 매핑된 폴더 추가 및 제거](../sharepoint/how-to-add-and-remove-mapped-folders.md)를 참조하십시오.  
  
-   .xml 파일을 SharePoint 프로젝트 항목의 폴더에 추가한 다음 .xml 파일의 **배포 형식** 속성을 **NoDeployment**에서 **RootFile** 또는 **ElementFile** 등의 다른 설정으로 변경합니다.  적절한 **배포 형식** 설정은 파일과 프로젝트에 따라 결정됩니다.  **배포 형식** 속성 설정에 대한 자세한 내용은 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)을 참조하십시오.  
  
 추가된 파일이 솔루션의 특정 프로젝트에 적용되지 않는 경우 빈 SharePoint 프로젝트를 솔루션에 추가한 다음 추가 파일을 이 프로젝트에 추가할 수 있습니다.  파일을 SharePoint\(특히 콘텐츠 데이터베이스\)에 배포하는 다른 방법은 모듈을 프로젝트에 추가한 다음 파일을 모듈에 추가하는 것입니다.  자세한 내용은 [모듈을 사용하여 솔루션에 파일 포함](../sharepoint/using-modules-to-include-files-in-the-solution.md)을 참조하십시오.  
  
## 참고 항목  
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)   
 [SharePoint 솔루션 빌드 및 디버깅](../sharepoint/building-and-debugging-sharepoint-solutions.md)  
  
  