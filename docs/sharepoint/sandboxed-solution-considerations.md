---
title: 샌드박스 솔루션 고려 사항 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.SandboxedSolutions
- VS.SharePointTools.Security.SandboxedSolutions
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, sandboxed solutions
- sandboxed solutions [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, farm solutions
- farm solutions [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ff85f3407fb24d6d49856bb11ff1852c544cad35
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="sandboxed-solution-considerations"></a>Sandboxed Solution Considerations
  *샌드박스 솔루션* 사이트 컬렉션 사용자가 자신의 사용자 지정 코드 솔루션을 업로드할 수 있는 Microsoft SharePoint 2010의 기능입니다. 일반적인 샌드박스 솔루션은 사용자가 자신의 웹 파트를 업로드 합니다.  
  
 샌드박스 SharePoint 응용 프로그램 그리고 웹 팜의 제한 부분에 액세스할 수 있는 안전 하 고 모니터링 프로세스에서 실행 됩니다. Microsoft SharePoint 2010 샌드박스 솔루션을 사용 하도록 설정 하려면 기능, 솔루션 갤러리, 모니터링, 솔루션 및 유효성 검사 프레임 워크의 조합을 사용 합니다.  
  
## <a name="specifying-project-trust-level"></a>프로젝트 신뢰 수준 지정  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 원하는 라고 하는 부울 프로젝트 속성을 통해 샌드박스 솔루션 지원 *샌드박스 솔루션*합니다. 언제 든 지 프로젝트에서이 속성을 설정할 수 있습니다 또는에서 프로젝트를 만들 때 지정할 수 있습니다는 **SharePoint 사용자 지정 마법사**합니다.  
  
> [!NOTE]  
>  변경 된 *샌드박스 솔루션* 를 만든 후 프로젝트의 속성 유효성 검사 오류가 발생할 수 있습니다.  
  
 솔루션은 팜 범위의 솔루션 것으로 간주 됩니다는 *샌드박스 솔루션* 속성이 **false** 선택한 또는 **팜 솔루션으로 배포** 옵션입니다. 그러나 솔루션은 취급 다르게 팜 솔루션과에서 *샌드박스 솔루션* 속성이 **true** 선택한 또는 **샌드박스 솔루션으로 배포** 마법사의 옵션입니다.  
  
## <a name="sharepoint-site-hierarchy"></a>SharePoint 사이트 계층 구조  
 어떻게 샌드박스 솔루션을 이해 하려면 작업을 알면 도움이 범위에서 SharePoint 사이트는 계층입니다. 맨 위에 있는 요소는 웹 팜의 라고 하며 다른 요소에 종속 된:  
  
 웹 팜  
  
 웹 응용 프로그램 A  
  
 사이트 컬렉션 A1  
  
 사이트 A1a  
  
 웹 응용 프로그램 B  
  
 사이트 컬렉션 B1  
  
 사이트 B1a  
  
 사이트 B1b  
  
 사이트 컬렉션 b 2  
  
 사이트 B2a  
  
 볼 수 있듯이 웹 팜에서 하나 이상의 웹 응용 프로그램을 차례로 하위 사이트를 포함할 수 있으며에 있는 하나 이상의 사이트 모음을 포함할 수 있는 포함할 수 있습니다. 하나의 사이트 컬렉션 영향만 사이트 모음에 적용 하 고 다른 변경 합니다. 그러나 웹 팜 수준에서의 변경 내용을 팜의 모든 사이트 모음을 영향을 줍니다.  
  
 Windows SharePoint Services (WSS) 3.0을 사용 하면 팜 수준에만 솔루션을 배포 하지만 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] 팜 수준 (팜 솔루션) 또는 사이트 모음 수준 (샌드박스 솔루션)을 배포할 수 있습니다.  
  
## <a name="why-sandboxed-solutions"></a>이유 샌드박스 솔루션?  
 WSS 3.0 솔루션은 팜 수준에만 배포할 수 있었습니다. 이 유해 하거나 불안정 솔루션 배포 될 수는 전체 웹 팜 및 모든 다른 사이트 모음 및 그 아래에서 실행 되는 응용 프로그램에 영향을 주는 것을 의미 합니다. 그러나 샌드박스 솔루션을 사용 하 여 팜의 특정 사이트 모음 하위 영역에 솔루션을 배포할 수 있습니다. 추가 보호를 제공 하려면 솔루션의 어셈블리는 주에 로드 [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] 프로세스 (w3wp.exe). 프로세스 (SPUCWorkerProcess.exe)에 로드 됩니다. 이 프로세스를 모니터링 하 고 할당량 및 제한 팜을 보호 하기 위해 CPU 주기를 사용 하는 루프를 실행 하는 등 유해한 작업을 수행 하는 샌드 박싱된 솔루션에서를 구현 합니다.  
  
## <a name="site-collection-solution-gallery"></a>사이트 컬렉션 솔루션 갤러리  
 [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)] 2010에는 "사이트 컬렉션 솔루션 갤러리"라는 기능이 있습니다. 열어 또는 SharePoint 2010 중앙 관리 페이지에서이 기능에 액세스할 수 있습니다는 **사이트 작업** 메뉴 선택 **사이트 설정**를 선택한 다음는 **솔루션** 링크 **갤러리** SharePoint 사이트에 있습니다. 솔루션 갤러리는 사이트 모음 관리자가 사이트 컬렉션에서 솔루션을 관리할 수 있는 솔루션의 리포지토리입니다.  
  
 솔루션 갤러리는 SharePoint 사이트의 웹 루트에 저장 된 문서 라이브러리입니다. 솔루션 갤러리 사이트 서식 파일을 바꾸고 솔루션 패키지를 지원 합니다. SharePoint 솔루션 패키지 (.wsp) 파일을 업로드 하는 경우에 샌드박스 솔루션으로 처리 됩니다.  
  
## <a name="sandboxed-solution-limitations"></a>샌드박스 솔루션의 제한 사항  
 샌드박스 솔루션을 배포할 때 SharePoint 기능을 사용할 수 있는 배열을 가질 수 있는 보안 취약점을 줄이는 데 도움이 제한 됩니다. 이러한 제한 사항 중 일부는 다음과 같습니다.  
  
-   샌드박스 솔루션은 제한 된 하위 집합만 배포 가능한 솔루션 요소를 제공 합니다. 사이트 정의 워크플로, 등 잠재적으로 취약 한 SharePoint 프로젝트 템플릿을 사용할 수 없는 경우  
  
-   SharePoint 샌드박스 솔루션에서에서 코드를 실행 프로세스 (SPUCWorkerProcess.exe)의 주 별도 [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] 응용 프로그램 풀 (w3wp.exe) 프로세스입니다.  
  
-   프로젝트에 매핑된 폴더를 추가할 수 없습니다.  
  
-   에 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] 어셈블리 Microsoft.Office.Server 샌드박스 솔루션에서 사용할 수 없습니다. 또한에 입력에서 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] 어셈블리 Microsoft.SharePoint 샌드박스 솔루션에서 사용할 수 있습니다.  
  
 지정 하는 SharePoint 솔루션 샌드박스 솔루션 영향을 주지 않습니다; SharePoint 서버에 유의 해야 SharePoint 프로젝트에서 SharePoint에 배포 되는 방식을 결정만 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 어떤 어셈블리에 바인딩합니다. 생성 된.wsp 파일에는 영향을 주지 않는 및.wsp 파일에 직접 상관 관계에 있는 데이터가 *샌드박스 솔루션* 속성입니다.  
  
## <a name="capabilities-and-elements-in-sandboxed-solutions"></a>샌드박스 솔루션의 기능 및 요소  
 샌드박스 솔루션은 다음 기능과 요소를 지원합니다.  
  
-   콘텐츠 형식/필드  
  
-   사용자 지정 작업  
  
-   선언적 워크플로  
  
-   이벤트 수신자  
  
-   기능 설명선  
  
-   목록 정의  
  
-   인스턴스 나열  
  
-   모듈/파일  
  
-   탐색  
  
-   onet.xml  
  
-   SPItemEventReceiver  
  
-   SPListEventReceiver  
  
-   SPWebEventReceiver  
  
-   파생 되는 모든 웹 파트에 대 한 지원 `System.Web.UI.WebControls.WebParts.WebPart`  
  
-   웹 파트  
  
-   (대신 Webtemp.xml) 기능 요소를 웹 서식 파일  
  
-   비주얼 웹 파트  
  
 샌드박스 솔루션은 다음 기능과 요소를 지원 하지 않습니다.  
  
-   응용 프로그램 페이지  
  
-   사용자 지정 작업 그룹  
  
-   팜 범위 기능  
  
-   `HideCustomAction` 요소  
  
-   웹 응용 프로그램 범위 기능  
  
-   코드가 포함 된 워크플로  
  
## <a name="see-also"></a>참고 항목  
 [차이점 샌드박스 솔루션과 팜 솔루션](../sharepoint/differences-between-sandboxed-and-farm-solutions.md)   
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)  
  
  