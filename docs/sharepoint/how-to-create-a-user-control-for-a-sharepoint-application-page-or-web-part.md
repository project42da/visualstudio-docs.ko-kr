---
title: "방법: SharePoint 응용 프로그램 페이지 또는 웹 파트를 위한 사용자 정의 컨트롤 만들기"
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
  - "사용자 컨트롤[Visual Studio에서 SharePoint 개발], 추가"
  - "사용자 컨트롤[Visual Studio에서 SharePoint 개발], 만들기"
ms.assetid: 492ea376-7188-4b5a-a2eb-adc0e3f51484
caps.latest.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# 방법: SharePoint 응용 프로그램 페이지 또는 웹 파트를 위한 사용자 정의 컨트롤 만들기
  사용자는 SharePoint 솔루션에 대한 사용자 지정 기능을 제공하는 사용자 지정 컨트롤을 만들 수 있고, 프로젝트 내에서 해당 기능을 다시 사용할 수 있습니다.  웹 파트 또는 응용 프로그램에 사용자 정의 컨트롤을 포함하거나, 페이지 다른 ASP.NET 컨트롤과 SharePoint 컨트롤을 추가, 또 컨트롤을 위한 속성 및 메서드를 정의할 수 있습니다.  사용자 정의 컨트롤에 대한 자세한 내용은 [웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md) 및 [SharePoint에서 서버 컨트롤과 사용자 컨트롤](http://blogs.msdn.com/b/kaevans/archive/2011/04/28/user-controls-and-server-controls-in-sharepoint.aspx) 을 참조하십시오.  
  
### SharePoint를 위한 사용자 정의 컨트롤을 만들려면  
  
1.  Visual Studio에서 SharePoint 프로젝트를 열거나 만듭니다.  
  
     [SharePoint 프로젝트 및 프로젝트 항목 템플릿](../sharepoint/sharepoint-project-and-project-item-templates.md)를 참조하십시오.  
  
2.  **솔루션 탐색기**에서 프로젝트 노드를 선택합니다.  
  
3.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택합니다.  
  
     **새 항목 추가** 대화 상자가 열립니다.  
  
4.  **설치 된** 창에서 **Office\/SharePoint** 노드를 선택합니다.  
  
5.  SharePoint 템플릿 목록에서 **사용자 컨트롤 \(팜 솔루션 전용\)** 을 선택합니다.  
  
    > [!NOTE]  
    >  사용자 정의 컨트롤은 팜 솔루션에서만 작동합니다.  
  
6.  **이름** 상자에 사용자 정의 컨트롤의 이름을 지정한 다음 **추가** 단추를 선택합니다.  
  
     프로젝트에 여러 가지 폴더와 파일이 추가됩니다.  이러한 파일에 대한 자세한 내용은 [웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)을 참조하십시오.  
  
     기본적으로 사용자 정의 컨트롤 파일은 Visual Web Developer 디자이너의 **소스**  뷰에 나타나며  이 보기에서 컨트롤의 XML 표시를 편집할 수 있습니다.  **도구 상자** 의 컨트롤을 끌어서 컨트롤을 시각적으로 디자인하려면 **디자인** 뷰로 전환합니다.  [NIB: Design View, Web Page Designer](http://msdn.microsoft.com/ko-kr/d8f2270a-357d-40a4-9b39-1a3f2366216d)를 참조하십시오.  
  
7.  컨트롤에서 발생하는 이벤트를 처리 하려면 사용자 정의 컨트롤의 코드 파일에 코드를 추가합니다.  
  
     이 파일은 **솔루션 탐색기** 에서 사용자 정의 컨트롤 파일 아래에 나타나고 프로젝트의 언어에 따라 .cs 또는.vb 확장명을 가집니다.  
  
## 참고 항목  
 [웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)   
 [SharePoint를 위한 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)  
  
  