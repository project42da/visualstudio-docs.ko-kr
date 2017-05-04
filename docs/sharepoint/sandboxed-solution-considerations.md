---
title: "샌드박스가 적용된 솔루션 고려 사항 | Microsoft Docs"
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
  - "VS.SharePointTools.Project.SandboxedSolutions"
  - "VS.SharePointTools.Security.SandboxedSolutions"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "팜 솔루션[Visual Studio에서 SharePoint 개발]"
  - "샌드박싱된 솔루션[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 팜 솔루션"
  - "Visual Studio에서 SharePoint 개발, 샌드박싱된 솔루션"
ms.assetid: 6c2d2dc6-4acb-4b68-ba94-a61087e8dff0
caps.latest.revision: 23
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 22
---
# 샌드박스가 적용된 솔루션 고려 사항
  *샌드박스가 적용된 솔루션*은 사이트 컬렉션 사용자가 사용자 지정 코드 솔루션을 업로드할 수 있는 Microsoft SharePoint 2010의 기능입니다.  일반적인 샌드박스가 적용된 솔루션은 사용자가 고유한 웹 파트를 업로드하는 것입니다.  
  
 샌드박스가 적용된 SharePoint 응용 프로그램은 모니터링되는 보안 프로세스로 실행됩니다. 이 프로세스에서는 웹 팜의 제한된 부분에만 액세스할 수 있습니다.  Microsoft SharePoint 2010에서는 기능, 솔루션 갤러리, 솔루션 모니터링 및 유효성 검사 프레임워크의 조합을 통해 샌드박스가 적용된 솔루션을 사용할 수 있도록 합니다.  
  
## 프로젝트 신뢰 수준 지정  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 *Sandboxed Solution*이라는 부울 프로젝트 속성을 통해 샌드박스가 적용된 솔루션을 지원합니다.  이 속성은 프로젝트에서 언제든지 설정할 수 있거나 **SharePoint 사용자 지정 마법사**에서 프로젝트를 만들 때 지정할 수 있습니다.  
  
> [!NOTE]  
>  프로젝트를 만든 후 *Sandboxed Solution* 속성을 변경하면 유효성 검사 오류가 발생할 수 있습니다.  
  
 *Sandboxed Solution* 속성을 **false**로 설정하거나 **팜 솔루션으로 배포** 옵션을 선택하면 솔루션이 팜 범위의 솔루션으로 간주됩니다.  그러나 *Sandboxed Solution* 속성을 **true**로 설정하거나 마법사에서 **샌드박스가 적용된 솔루션으로 배포** 옵션을 선택하면 솔루션이 팜 솔루션과는 다르게 처리됩니다.  
  
## SharePoint 사이트 계층 구조  
 샌드박스가 적용된 솔루션의 작동 방식을 이해하려는 경우 SharePoint 사이트가 범위 계층 구조로 이루어져 있음을 알면 도움이 됩니다.  최상위 요소는 웹 팜이라고 하고 다른 요소는 모두 이 요소에 종속됩니다.  
  
 웹 팜  
  
 웹 응용 프로그램 A  
  
 사이트 컬렉션 A1  
  
 사이트 A1a  
  
 웹 응용 프로그램 B  
  
 사이트 컬렉션 B1  
  
 사이트 B1a  
  
 사이트 B1b  
  
 사이트 컬렉션 B2  
  
 사이트 B2a  
  
 보시는 것처럼 웹 팜에는 하나 이상의 웹 응용 프로그램이 포함될 수 있고, 웹 응용 프로그램에는 하나 이상의 사이트 컬렉션이 포함될 수 있으며, 사이트 컬렉션에는 하위 사이트가 포함될 수 있습니다.  한 사이트 컬렉션을 변경하면 해당 사이트 컬렉션에만 영향을 줍니다.  하지만 웹 팜 수준에서 변경하면 팜의 모든 사이트 컬렉션에 영향을 줍니다.  
  
 WSS\(Windows SharePoint Services\) 3.0을 사용하면 팜 수준에만 솔루션을 배포할 수 있지만 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)]을 사용하면 팜 수준\(팜 솔루션\) 또는 사이트 컬렉션 수준\(샌드박스가 적용된 솔루션\)에 배포할 수 있습니다.  
  
## 샌드박스가 적용된 솔루션을 사용하는 이유  
 WSS 3.0에서는 팜 수준에만 솔루션을 배포할 수 있었습니다.  즉, 전체 팜과 그 아래에서 실행되는 다른 모든 사이트 컬렉션 및 응용 프로그램에 영향을 주는 유해하거나 불안정한 솔루션이 배포될 수 있었습니다.  하지만 샌드박스가 적용된 솔루션을 사용하면 솔루션을 팜의 하위 영역인 특정 사이트 컬렉션에 배포할 수 있습니다.  보호 기능을 강화하기 위해 솔루션의 어셈블리는 주요 [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] 프로세스\(w3wp.exe\)에 로드되지 않습니다.  대신 별도의 프로세스로 로드됩니다\(SPUCWorkerProcess.exe\).  CPU 사이클을 소비하는 자주 반복되는 루프의 실행 등과 같이 위험한 동작을 수행하는 샌드박스가 적용된 솔루션으로부터 팜을 보호하기 위해 이 프로세스를 모니터링하고 할당량 및 사용량 조절을 구현합니다.  
  
## 사이트 컬렉션 솔루션 갤러리  
 [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)] 2010은 "사이트 컬렉션 솔루션 갤러리" 기능을 가집니다. SharePoint 2010 중앙 관리 페이지에서 또는 ShaerPoint 사이트의 **사이트 작업** 메뉴에서 **사이트 설정** 을 선택하고 **갤러리** 밑의 **솔루션** 을 선택하여 이 기능에 액세스할 수 있습니다.  솔루션 갤러리는 사이트 컬렉션 관리자가 사이트 컬렉션의 솔루션을 관리할 수 있는 솔루션 리포지토리입니다.  
  
 솔루션 갤러리는 SharePoint 사이트의 루트 웹에 저장된 문서 라이브러리입니다.  솔루션 갤러리는 사이트 템플릿을 대체하며 솔루션 패키지를 지원합니다.  SharePoint 솔루션 패키지 파일\(.wsp\)을 업로드하면 샌드박스가 적용된 솔루션으로 처리됩니다.  
  
## 샌드박스가 적용된 솔루션 제한 사항  
 샌드박스가 적용된 솔루션을 배포하면 솔루션에서 사용할 수 있는 SharePoint 기능 배열이 제한되어 이 솔루션으로 인한 보안 취약점을 줄일 수 있습니다.  이러한 제한에는 다음이 포함됩니다.  
  
-   샌드박스가 적용된 솔루션은 배포 가능한 솔루션 요소 중 제한된 하위 집합만 사용할 수 있습니다.  사이트 정의 및 워크플로와 같은 잠재적으로 취약한 SharePoint 프로젝트 템플릿은 사용할 수 없습니다.  
  
-   SharePoint는 주요 [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] 응용 프로그램 풀\(w3wp.exe\) 프로세스와는 별도의 프로세스\(SPUCWorkerProcess.exe\)에서 샌드박스가 적용된 솔루션 코드를 실행합니다.  
  
-   매핑된 폴더는 프로젝트에 추가할 수 없습니다.  
  
-   샌드박스가 적용된 솔루션에는 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] 어셈블리 Microsoft.Office.Server의 형식을 사용할 수 없습니다.  샌드박스가 적용된 솔루션에는 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] 어셈블리 Microsoft.SharePoint의 형식만 사용할 수 있습니다.  
  
 SharePoint 솔루션을 샌드박스가 적용된 솔루션으로 지정하면 SharePoint 서버에는 영향을 주지 않고 SharePoint 프로젝트가 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint로 배포되는 방법 및 바인딩되는 어셈블리만 결정합니다.  생성된 .wsp 파일에는 영향을 주지 않으며, .wsp 파일에 *Sandboxed Solution* 속성과 직접 상호 관련된 데이터가 없습니다.  
  
## 샌드박스가 적용된 솔루션의 기능 및 요소  
 샌드박스가 적용된 솔루션은 다음 기능과 요소를 지원합니다.  
  
-   콘텐츠 형식\/필드  
  
-   사용자 지정 작업  
  
-   선언적 워크플로  
  
-   이벤트 수신자  
  
-   기능 설명선  
  
-   목록 정의  
  
-   목록 인스턴스  
  
-   모듈\/파일  
  
-   탐색  
  
-   Onet.xml  
  
-   SPItemEventReceiver  
  
-   SPListEventReceiver  
  
-   SPWebEventReceiver  
  
-   `System.Web.UI.WebControls.WebParts.WebPart`에서 파생되는 모든 웹 파트에 대한 지원  
  
-   웹 파트  
  
-   WebTemplate 기능 요소\(Webtemp.xml 대신\)  
  
-   비주얼 웹 파트  
  
 샌드박스가 적용된 솔루션은 다음 기능과 요소를 지원하지 않습니다.  
  
-   응용 프로그램 페이지  
  
-   사용자 지정 작업 그룹  
  
-   팜 범위 기능  
  
-   `HideCustomAction` 요소  
  
-   웹 응용 프로그램 범위 기능  
  
-   코드가 포함된 워크플로  
  
## 참고 항목  
 [샌드박스 솔루션과 팜 솔루션의 차이점](../sharepoint/differences-between-sandboxed-and-farm-solutions.md)   
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)  
  
  