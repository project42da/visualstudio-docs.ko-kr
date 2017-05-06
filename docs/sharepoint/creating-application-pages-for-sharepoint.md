---
title: "SharePoint를 위한 응용 프로그램 페이지 만들기"
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
  - "응용 프로그램 페이지[Visual Studio에서 SharePoint 개발], 만들기"
  - "응용 프로그램 페이지[Visual Studio에서 SharePoint 개발], 개발"
  - "Visual Studio에서 SharePoint 개발, 응용 프로그램 페이지"
  - "Visual Studio에서 SharePoint 개발, 콘텐츠 페이지"
  - "Visual Studio에서 SharePoint 개발, 웹 페이지"
ms.assetid: a6e97149-15dd-4bdb-8d75-3b53f886f76c
caps.latest.revision: 36
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 35
---
# SharePoint를 위한 응용 프로그램 페이지 만들기
  *응용 프로그램 페이지*는 SharePoint 웹 사이트에서 사용하도록 디자인된 ASP.NET 웹 페이지입니다.  응용 프로그램 페이지는 특수한 형태의 ASP.NET 페이지로서  SharePoint 마스터 페이지와 병합되는 콘텐츠를 포함하고 있다는 점에서 표준 ASP.NET 페이지와 다릅니다.  마스터 페이지는 응용 프로그램 페이지가 사이트의 다른 페이지와 같은 모양 및 동작을 공유할 수 있게 해 줍니다.  
  
 Visual Studio에서 디자이너를 사용하여 응용 프로그램 페이지를 디자인할 수 있습니다.  디자이너는 마스터 페이지에 정의되어 있는 각 콘텐츠 자리 표시자에 대한 콘텐츠 영역을 표시합니다.  이러한 콘텐츠 영역으로 컨트롤을 끌어와 응용 프로그램 페이지를 디자인할 수 있습니다.  
  
## 응용 프로그램 페이지  
 응용 프로그램 페이지는 서버의 모든 사이트에서 공유되는 반면 사이트 페이지는 사이트마다 고유합니다.  자세한 내용은 [SharePoint 페이지 종류](http://go.microsoft.com/fwlink/?LinkID=211584) 을 참조하십시오.  
  
 기본적으로 SharePoint 사이트를 만들 때 표시되는 대부분의 페이지는 사이트 페이지입니다.  사이트 페이지는 SharePoint 페이지 라이브러리에 추가할 수 있습니다.  사용자는 SharePoint Designer와 같은 도구를 사용하여 사이트 페이지를 사용자 지정할 수 있습니다.  사이트 페이지는 동적 웹 파트 및 웹 파트 영역과 같은 기능을 호스팅할 수도 있습니다.  
  
 응용 프로그램 페이지는 이러한 기능을 수행할 수 없지만  사용자 지정 코드를 포함할 페이지가 필요한 경우 이러한 페이지를 만들기에 적합한 형식입니다.  사이트 페이지에 사용자 지정 코드를 추가할 수는 있지만 사용자가 SharePoint Designer와 같은 도구를 사용하여 페이지를 사용자 지정하면 코드의 실행이 중지됩니다.  
  
> [!NOTE]  
>  Visual Studio에서는 SharePoint 사이트를 위한 사이트 페이지를 만드는 데 사용할 수 있는 템플릿을 제공하지 않습니다.  자세한 내용은 [SharePoint 페이지 종류](http://go.microsoft.com/fwlink/?LinkID=211584) 을 참조하십시오.  
  
## 응용 프로그램 페이지 만들기  
 응용 프로그램 페이지를 만들려면 SharePoint 프로젝트에 **응용 프로그램 페이지** 항목을 추가합니다.  응용 프로그램 페이지를 만들면 프로젝트에 다음 폴더가 추가됩니다.  
  
|폴더|설명|  
|--------|--------|  
|레이아웃|SharePoint 파일 시스템의 \_layouts 가상 디렉터리에 매핑됩니다.|  
|레이아웃 하위 폴더|응용 프로그램 페이지를 구성하는 파일이 들어 있습니다.  기본적으로 이 폴더의 이름은 프로젝트 이름과 같으며  언제든지 이름을 바꿀 수 있습니다.  프로젝트를 실행하면 Visual Studio에서 SharePoint 파일 시스템의 \_layouts 가상 디렉터리에 이 폴더를 배포합니다.|  
  
 프로젝트에 다음 파일이 추가됩니다.  
  
|파일|설명|  
|--------|--------|  
|ASP.NET 페이지 파일\(.aspx\)|페이지를 정의하는 XML 태그가 들어 있습니다.|  
|응용 프로그램 페이지 코드 파일|응용 프로그램 페이지의 코드 숨김 파일이 들어 있습니다.  이벤트를 처리하는 코드를 이 파일에 추가합니다.|  
|응용 프로그램 페이지 디자이너 코드 파일|디자이너에서 생성되는 코드가 들어 있습니다.  이 파일을 직접 편집하지 마십시오.|  
  
## 응용 프로그램 페이지 디자인 및 디버깅  
 Visual Studio의 Visual Web Developer 디자이너를 사용하여 응용 프로그램 페이지의 콘텐츠를 디자인합니다.  이 디자이너는 프로젝트의 응용 프로그램 페이지를 열 때 두 번 클릭 하거나 바로 가기 메뉴를 연 다음 **열기** 를 선택하여 나타납니다.  이 디자이너를 사용하는 방법에 대한 자세한 내용은 [Visual Studio Web Development Content Map](http://msdn.microsoft.com/ko-kr/9c31f93b-c8fb-4599-9b14-6194ec8c7539)을 참조하십시오.  
  
> [!NOTE]  
>  이 페이지는 디자이너의 **소스** 뷰에서만 디자인할 수 있습니다.  디자이너의 **디자인** 뷰는 응용 프로그램 페이지에 사용하지 못합니다.  
  
 Visual Studio에서 다른 SharePoint 프로젝트 항목을 디버깅할 때와 같은 방법으로 응용 프로그램 페이지를 디버깅할 수 있습니다.  Visual Studio 디버거를 시작하면 Visual Studio에서 SharePoint 사이트가 열립니다.  
  
 응용 프로그램 페이지를 보려면, 응용 프로그램 페이지의 위치\(예: http:\/\/*Server\_Name*\/\_layouts\/*Project\_Name*\/ApplicationPage1.aspx\)로 직접 이동해야 합니다.  
  
 SharePoint 프로젝트를 디버깅하는 방법에 대한 자세한 내용은 [SharePoint 솔루션 문제 해결](../sharepoint/troubleshooting-sharepoint-solutions.md)을 참조하십시오.  
  
## 마스터 페이지 선택  
 기본적으로 **응용 프로그램 페이지** 항목은 프로젝트를 디버깅하는 데 사용하는 사이트의 마스터 페이지를 참조합니다.  이 페이지의 이름은 v4.master이며 SharePoint 사이트의 **마스터 페이지 갤러리**에서 찾을 수 있습니다.  
  
 응용 프로그램의 `MasterPageFile` 특성을 `Page` 요소로 설정하여 응용 프로그램 페이지에 사용되는 마스터 페이지를 명시적으로 변경할 수 있습니다. 예를 들면 `MasterPageFile="~/_layouts/applicationv4.master"`와 같이 설정합니다.  SharePoint 서버에서 동적 마스터 페이지를 사용하지 않을 경우 이 특성을 설정해야 합니다.  SharePoint의 마스터 페이지에 대한 자세한 내용은 [마스터 페이지](http://go.microsoft.com/fwlink/?LinkID=169281) 를 참조하십시오.  
  
## 참고 항목  
 [SharePoint Foundation Development in Depth](http://go.microsoft.com/fwlink/?LinkID=182103)   
 [ASP.NET 웹 페이지 개요](http://msdn.microsoft.com/library/52fa0455-41ea-4315-8208-2861d1527da2)   
 [ASP.NET 웹 페이지 구문 개요](http://msdn.microsoft.com/library/09074b20-ece9-46fa-bc8f-ab2595ed2c02)   
 [ASP.NET 웹 페이지 프로그래밍](http://msdn.microsoft.com/ko-kr/5626c661-8057-4de8-b658-c2e35ed4b4c9)  
  
  