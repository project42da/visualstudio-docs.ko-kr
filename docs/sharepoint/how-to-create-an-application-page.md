---
title: "방법: 응용 프로그램 페이지 만들기"
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
  - "응용 프로그램 페이지[Visual Studio에서 SharePoint 개발], 추가"
  - "응용 프로그램 페이지[Visual Studio에서 SharePoint 개발], 만들기"
ms.assetid: 9ad7044a-2fa7-4bba-8f25-b9f2cc1b7c6b
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 15
---
# 방법: 응용 프로그램 페이지 만들기
  하나 이상의 SharePoint 사이트를 위한 ASP.NET 웹 페이지를 만들 수 있습니다.  SharePoint에서 이러한 페이지를 응용 프로그램 페이지라고 합니다.  사이트 페이지와 달리 응용 프로그램 페이지에는 페이지에 숨겨져서 실행되는 코드가 들어 있습니다.  자세한 내용은 [SharePoint를 위한 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)을 참조하십시오.  
  
### 응용 프로그램 페이지를 만들려면  
  
1.  Visual Studio에서 SharePoint 프로젝트를 열거나 만듭니다.  
  
     자세한 내용은 [SharePoint 프로젝트 및 프로젝트 항목 템플릿](../sharepoint/sharepoint-project-and-project-item-templates.md)을 참조하십시오.  
  
2.  **솔루션 탐색기**에서 프로젝트 노드를 선택합니다.  
  
3.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택합니다.  
  
4.  **새 항목 추가** 대화 상자에서, **SharePoint** 노드를 확장한 후 **2010** 항목을 선택합니다.  
  
5.  SharePoint 템플릿 목록에서 **응용 프로그램 페이지** 를 선택합니다.  
  
6.  **이름** 상자에서, 응용 프로그램 페이지의 이름을 지정한 다음 **추가** 버튼을 선택합니다.  
  
     프로젝트에 여러 가지 폴더와 파일이 추가됩니다.  이러한 파일에 대한 자세한 내용은 [SharePoint를 위한 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)을 참조하십시오.  
  
     Visual Web Developer 디자이너의 **소스** 창에서 ASP.NET 페이지 파일이 표시됩니다.  **Toolbox** 의 컨트롤을 추가하고 자리 표시자에 위치시켜 페이지를 디자인할 수 있습니다.  자세한 내용은 [웹 페이지 디자이너, 소스 뷰](http://msdn.microsoft.com/ko-kr/5911396b-fe51-4150-9ff1-b085f812862f)를 참조하십시오.  
  
7.  컨트롤 이벤트를 처리하려면 응용 프로그램 페이지의 코드 파일에 코드를 추가합니다.  
  
     코드 파일은 프로젝트의 언어에 따라 .cs 또는 .vb 확장명을 가지고 ASP.NET 페이지 파일 노드를 확장 하면 나타납니다.  응용 프로그램 페이지 만들기에 대한 자세한 예제를 보려면 [연습: SharePoint 응용 프로그램 페이지 만들기](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md)를 참조하십시오.  
  
## 참고 항목  
 [Visual Studio Web Development Content Map](http://msdn.microsoft.com/ko-kr/9c31f93b-c8fb-4599-9b14-6194ec8c7539)   
 [SharePoint를 위한 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [연습: SharePoint 응용 프로그램 페이지 만들기](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md)  
  
  