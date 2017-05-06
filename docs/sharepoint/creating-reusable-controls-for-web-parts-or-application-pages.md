---
title: "웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기"
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
  - "Visual Studio에서 SharePoint 개발, 사용자 정의 컨트롤"
  - "사용자 컨트롤[Visual Studio에서 SharePoint 개발], 만들기"
ms.assetid: 8fcafd98-c002-47f1-b4a9-cbb500232616
caps.latest.revision: 19
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 19
---
# 웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기
  Visual Studio에서 SharePoint에서 실행되는 응용 프로그램 페이지와 웹 파트에서 사용할 수 있는 재사용 가능한 사용자 지정 컨트롤을 만들 수 있습니다.  이러한 컨트롤을 사용자 정의 컨트롤이라고 합니다.  사용자 정의 컨트롤에 대한 자세한 내용은 [ASP.NET User Controls](http://msdn.microsoft.com/library/5e601b3d-bb16-4dbe-9e35-7e92a34565ca)을 참조하십시오.  
  
## 사용자 정의 컨트롤 만들기  
 사용자 정의 컨트롤을 만들려면 **빈 SharePoint 프로젝트**에 **사용자 정의 컨트롤**을 추가합니다.  자세한 내용은 [방법: SharePoint 응용 프로그램 페이지 또는 웹 파트를 위한 사용자 정의 컨트롤 만들기](../sharepoint/how-to-create-a-user-control-for-a-sharepoint-application-page-or-web-part.md)을 참조하십시오.  
  
 **사용자 정의 컨트롤** 항목을 추가하면 프로젝트에 폴더가 만들어지고 폴더에 여러 가지 파일이 추가됩니다.  다음 표에서는 각 파일에 대해 설명합니다.  
  
|파일|설명|  
|--------|--------|  
|사용자 정의 컨트롤 파일|사용자 정의 컨트롤을 정의합니다.  이 파일에 컨트롤과 태그를 추가하여 사용자 정의 컨트롤을 디자인합니다.|  
|코드 파일|사용자 정의 컨트롤의 코드 숨김 파일이 들어 있습니다.  이벤트를 처리하는 코드를 이 파일에 추가합니다.|  
|디자이너 코드 파일|디자이너에서 생성된 코드가 들어 있으며 이 파일을 직접 편집하면 안 됩니다.|  
  
## 사용자 정의 컨트롤 디자인  
 Visual Studio의 Visual Web Developer 디자이너를 사용하여 사용자 정의 컨트롤을 디자인합니다.  이 디자이너는 프로젝트에서 사용자 정의 컨트롤 파일을 열고 **디자인** 탭을 선택 하면 나타납니다.  이 디자이너를 사용하는 방법에 대한 자세한 내용은 [Visual Studio Web Development Content Map](http://msdn.microsoft.com/ko-kr/9c31f93b-c8fb-4599-9b14-6194ec8c7539)을 참조하십시오.  
  
## 사용자 정의 컨트롤 사용  
 응용 프로그램 페이지나 웹 파트에 사용자 정의 컨트롤을 포함해야 SharePoint에 사용자 정의 컨트롤이 표시됩니다.  
  
 사용자 정의 컨트롤을 응용 프로그램 페이지에 포함하려면 [@ Register](http://msdn.microsoft.com/ko-kr/66f34922-be41-4e36-9dc8-1774d85311d1) 지시문을 응용 프로그램 페이지에 추가한 다음 페이지에서 하나 이상의 콘텐츠 자리 표시자 안에 사용자 정의 컨트롤을 선언합니다.  표준 ASP.NET 웹 페이지에서 이 작업을 수행하는 방법에 대한 예제는 [How to: Include a User Control in an ASP.NET Web Page](http://msdn.microsoft.com/library/7c3bfd74-846c-4b88-b1ef-45d75860af92)을 참조하십시오.  
  
 사용자 정의 컨트롤을 웹 파트에 포함하려면 웹 파트 코드 파일의 웹 파트 <xref:System.Web.UI.WebControls.WebParts.Part.Controls%2A> 컬렉션에 사용자 정의 컨트롤을 추가합니다.  다음 예제에서는 웹 파트의 <xref:System.Web.UI.WebControls.WebParts.Part.Controls%2A> 컬렉션에 사용자 정의 컨트롤을 추가합니다.  
  
 [!code-csharp[SP_VisualWebPart#5](../snippets/csharp/VS_Snippets_OfficeSP/sp_visualwebpart/cs/visualwebpart1/visualwebpart1.cs#5)]
 [!code-vb[SP_VisualWebPart#5](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_visualwebpart/vb/visualwebpart1/visualwebpart1.vb#5)]  
  
## 사용자 정의 컨트롤 디버깅  
 사용자 정의 컨트롤을 디버깅하려면 SharePoint 프로젝트의 응용 프로그램 페이지나 웹 파트에 사용자 정의 컨트롤이 포함되어 있어야 합니다.  Visual Studio 프로젝트의 코드를 디버깅할 때와 같은 방법으로 사용자 정의 컨트롤의 코드를 디버깅할 수 있습니다.  
  
 Visual Studio 디버거를 시작하면 Visual Studio에서 SharePoint 사이트가 열립니다.  
  
 SharePoint에서 사용자 정의 컨트롤이 포함된 응용 프로그램 페이지를 엽니다.  사용자 정의 컨트롤이 웹 파트에 포함되어 있으면 해당 웹 파트를 SharePoint의 웹 파트 페이지에 추가합니다.  
  
 SharePoint 프로젝트 디버깅에 대한 자세한 내용은 [SharePoint 솔루션 문제 해결](../sharepoint/troubleshooting-sharepoint-solutions.md)을 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[방법: SharePoint 응용 프로그램 페이지 또는 웹 파트를 위한 사용자 정의 컨트롤 만들기](../sharepoint/how-to-create-a-user-control-for-a-sharepoint-application-page-or-web-part.md)|SharePoint에서 실행되는 응용 프로그램 페이지와 웹 파트에서 사용할 수 있는 재사용 가능한 사용자 지정 컨트롤을 만드는 방법을 보여 줍니다.|  
|[Visual Web Developer 작업](http://msdn.microsoft.com/ko-kr/9c31f93b-c8fb-4599-9b14-6194ec8c7539)|프로젝트에서 웹 페이지를 열 때 나타나는 디자이너를 사용하는 방법에 대해 설명합니다.|  
  
  