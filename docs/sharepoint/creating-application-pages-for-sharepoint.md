---
title: "SharePoint 용 응용 프로그램 페이지 만들기 | Microsoft Docs"
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
- SharePoint development in Visual Studio, Web pages
- SharePoint development in Visual Studio, content pages
- SharePoint development in Visual Studio, application pages
- application pages [SharePoint development in Visual Studio], developing
- application pages [SharePoint development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 0ae0580ed4f684f888175ae83afe21dbcd9bf42c
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="creating-application-pages-for-sharepoint"></a>SharePoint를 위한 응용 프로그램 페이지 만들기
  *응용 프로그램 페이지* SharePoint 웹 사이트에서 사용 하기 위해 설계 된 ASP.NET 웹 페이지입니다. 응용 프로그램 페이지는 ASP.NET 페이지의 특수화 된 형식입니다. 응용 프로그램 페이지 및 ASP.NET 페이지를 표준 간의 주요 차이점은 응용 프로그램 페이지를 SharePoint 마스터 페이지 콘텐츠를 포함 합니다. 마스터 페이지를 응용 프로그램 페이지를 사이트의 다른 페이지와 동일한 모양 및 동작을 공유할 수 있습니다.  
  
 Visual Studio를 사용 하면 디자이너를 사용 하 여 응용 프로그램 페이지를 디자인할 수 있습니다. 디자이너는 마스터 페이지에 정의 된 각 콘텐츠 자리 표시자에 대 한 콘텐츠 영역을 표시 합니다. 이러한 콘텐츠 영역에 컨트롤을 끌어 페이지에 응용 프로그램을 디자인할 수 있습니다.  
  
## <a name="application-pages"></a>응용 프로그램 페이지  
 반면 사이트 페이지는 단일 사이트 에서만 응용 프로그램 페이지, 서버의 모든 사이트에서 공유 됩니다. 자세한 내용은 [SharePoint 페이지 유형은](http://go.microsoft.com/fwlink/?LinkID=211584)합니다.  
  
 기본적으로 대부분의 SharePoint 사이트를 만들 때 표시 되는 페이지는 사이트 페이지를 사용 합니다. 사이트 페이지를 SharePoint 페이지 라이브러리에 추가할 수 있습니다. 사용자는 SharePoint 디자이너와 같은 도구를 사용 하 여 사이트 페이지를 지정할 수 있습니다. 사이트 페이지, 동적 웹 파트와 웹 파트 영역 등의 기능을 호스트할 수 있습니다.  
  
 응용 프로그램 페이지는 다음과 같은이 작업을 수행할 수 없습니다. 그러나 응용 프로그램 페이지는 가장 적합 한 유형의 사용자 지정 코드를 포함 하도록 페이지를 만들 수 있습니다. 사이트 페이지에 사용자 지정 코드를 추가할 수 있습니다, 있지만 코드 사용자가 SharePoint 디자이너와 같은 도구를 사용 하 여 페이지를 사용자 지정 실행이 중지 됩니다.  
  
> [!NOTE]  
>  Visual Studio에서는 도움이 되는 템플릿도 SharePoint 사이트에 대 한 사이트 페이지를 만듭니다. 자세한 내용은 참조 [SharePoint 페이지 유형은](http://go.microsoft.com/fwlink/?LinkID=211584)합니다.  
  
## <a name="creating-an-application-page"></a>응용 프로그램 페이지 만들기  
 응용 프로그램 페이지를 만들려면 추가 **응용 프로그램 페이지** 을 SharePoint 프로젝트 항목입니다. 응용 프로그램 페이지를 만들 때 Visual Studio 프로젝트에 다음 폴더를 추가 합니다.  
  
|폴더|설명|  
|------------|-----------------|  
|레이아웃|SharePoint 파일 시스템의 레이아웃 가상 디렉터리에 매핑됩니다.|  
|레이아웃 하위 폴더|응용 프로그램 페이지를 구성 하는 파일을 포함 합니다. 기본적으로이 폴더에 프로젝트와 동일한 이름이 들어 있습니다. 언제 든 지가이 폴더를 바꿀 수 있습니다. 프로젝트를 실행 하면 Visual Studio SharePoint 파일 시스템의 레이아웃 가상 디렉터리를이 폴더를 배포 합니다.|  
  
 Visual Studio 프로젝트에 다음 파일을 추가합니다.  
  
|파일|설명|  
|----------|-----------------|  
|ASP.NET 페이지 파일 (.aspx)|페이지를 정의 하는 XML 태그를 포함 합니다.|  
|응용 프로그램 페이지 코드 파일|코드 숨김 응용 프로그램 페이지를 포함합니다. 이 파일에 이벤트를 처리 하는 코드를 추가 합니다.|  
|응용 프로그램 페이지 디자이너 코드 파일|디자이너에서 생성 되는 코드를 포함 합니다. 이 파일을 직접 편집 하지 마십시오.|  
  
## <a name="designing-and-debugging-an-application-page"></a>디자인 및 응용 프로그램 페이지를 디버깅 합니다.  
 Visual Studio에서 디자이너 뷰를 사용 하 여 응용 프로그램 페이지의 내용을 디자인 합니다. 이 디자이너는 프로젝트에서 응용 프로그램 페이지를 열면 나타납니다 (번 클릭 하거나 바로 가기 메뉴를 열고 선택 하 여 **열고**)를 선택한 후는 **디자인** 아래쪽의 단추 편집기입니다.  
  
> [!NOTE]  
>  페이지를 디자인할 수에는 **소스** 디자이너의 뷰. **디자인** 뷰 디자이너의 응용 프로그램 페이지에 표시 되지 않습니다.  
  
 Visual Studio에서 SharePoint 프로젝트 항목 다른 디버그와 마찬가지로 응용 프로그램 페이지를 디버깅할 수 있습니다. Visual Studio 디버거를 시작할 때 Visual Studio는 SharePoint 사이트를 엽니다.  
  
 응용 프로그램 페이지를 보려면 페이지에 응용 프로그램의 위치로 이동 수동으로 해야 합니다 (예: http://*Server_Name*/_layouts/*Project_Name*/ApplicationPage1.aspx).  
  
 SharePoint 프로젝트를 디버깅 하는 방법에 대 한 자세한 내용은 참조 [SharePoint 솔루션 문제 해결](../sharepoint/troubleshooting-sharepoint-solutions.md)합니다.  
  
## <a name="choosing-a-master-page"></a>마스터 페이지를 선택합니다.  
 기본적으로는 **응용 프로그램 페이지** 항목 프로젝트를 디버깅 하는 데 사용 하는 사이트의 마스터 페이지를 참조 합니다. 페이지 v4.master 라는 있으며에 나열 된 것을 찾을 수는 **마스터 페이지 갤러리** SharePoint 사이트의 합니다.  
  
 설정 하 여 응용 프로그램 페이지에서 사용 되는 마스터 페이지를 명시적으로 변경할 수는 `MasterPageFile` 응용 프로그램의 특성 `Page` 요소입니다. (예: `MasterPageFile="~/_layouts/applicationv4.master"`). 사실, SharePoint 서버에서 동적 마스터 페이지를 사용할 수 없는 경우이 특성을 설정 해야 합니다. SharePoint에서 마스터 페이지에 대 한 자세한 내용은 참조 [마스터 페이지](http://go.microsoft.com/fwlink/?LinkID=169281)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [깊이에서 SharePoint Foundation 개발](http://go.microsoft.com/fwlink/?LinkID=182103)   
 [ASP.NET 개요](/aspnet/overview)   
 [ASP.NET 웹 페이지 2](/aspnet/web-pages/index)   
  
  