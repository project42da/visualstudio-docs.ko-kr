---
title: "방법: 응용 프로그램 페이지 만들기 | Microsoft Docs"
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
- application pages [SharePoint development in Visual Studio], adding
- application pages [SharePoint development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9429f2834997ce5ad2c3359fb04c164995dd2e12
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-create-an-application-page"></a>방법: 응용 프로그램 페이지 만들기
  하나 이상의 SharePoint 사이트에 대한 ASP.NET 웹 페이지를 만들 수 있습니다. Sharepoint에서 이러한 페이지에 응용 프로그램 페이지 라고 합니다. 사이트 페이지와 달리 응용 프로그램 페이지의 페이지 뒤에서 실행 되는 코드를 포함 합니다. 자세한 내용은 참조 [SharePoint 용 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)합니다.  
  
### <a name="to-create-an-application-page"></a>응용 프로그램 페이지를 만들려면  
  
1.  Visual Studio에서 SharePoint 프로젝트를 열거나 만듭니다.  
  
     자세한 내용은 참조 [SharePoint 프로젝트 및 프로젝트 항목 템플릿](../sharepoint/sharepoint-project-and-project-item-templates.md)합니다.  
  
2.  **솔루션 탐색기**에서 프로젝트 노드를 선택합니다.  
  
3.  메뉴 모음에서 **프로젝트**, **새 항목 추가**합니다.  
  
4.  에 **새 항목 추가** 대화 상자에서 **SharePoint** 노드를 선택한 후는 **2010** 항목입니다.  
  
5.  SharePoint 템플릿의 목록에서 선택 **응용 프로그램 페이지**합니다.  
  
6.  에 **이름** 상자 응용 프로그램 페이지에 대 한 이름을 지정 하 고 선택 합니다는 **추가** 단추입니다.  
  
     Visual Studio 프로젝트에 여러 폴더와 파일을 추가합니다. 이러한 파일에 대 한 자세한 내용은 참조 [SharePoint 용 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)합니다.  
  
     에 **소스** Visual Web Developer 디자이너는 ASP.NET 페이지 파일의 뷰가 표시 됩니다. 컨트롤을 추가 하 여 페이지를 디자인할 수는 **도구 상자** 콘텐츠 자리 표시자에 배치 하 고 있습니다. 자세한 내용은 참조 [웹 페이지 디자이너, 소스 뷰](http://msdn.microsoft.com/en-us/5911396b-fe51-4150-9ff1-b085f812862f)합니다.  
  
7.  컨트롤 이벤트를 처리하려면 응용 프로그램 페이지의 코드 파일에 코드를 추가합니다.  
  
     코드 파일은 ASP.NET 페이지 파일의 노드를 확장하면 나타나며 프로젝트의 언어에 따라 확장명이 .cs 또는 .vb입니다. 응용 프로그램 페이지를 만드는 방법의 종단 간 예제를 보려면 [연습: SharePoint 응용 프로그램 페이지 만들기](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 용 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [연습: SharePoint 응용 프로그램 페이지 만들기](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md)  
  
  