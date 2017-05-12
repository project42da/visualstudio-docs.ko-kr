---
title: "방법: SharePoint 웹 파트 만들기"
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
  - "웹 파트[Visual Studio에서 SharePoint 개발], 추가"
  - "웹 파트[Visual Studio에서 SharePoint 개발], 만들기"
ms.assetid: 0d037522-c25e-4c24-93b7-518db0f791b7
caps.latest.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 20
---
# 방법: SharePoint 웹 파트 만들기
  웹 파트를 만들고 추가 하 여 웹 파트를 사용자 지정할 수는 모든 SharePoint 프로젝트에 **웹 파트** 항목을 추가한 다음 웹 파트에 대한 코드 파일을 수정하거나 또는 디자이너를 사용하여 웹파트를 생성 및 사용자 지정할 수 있습니다.  자세한 내용은 [방법: 디자이너를 사용하여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)을 참조하십시오.  
  
### SharePoint 웹 파트를 만들려면  
  
1.  SharePoint 프로젝트를 열거나 만듭니다.  
  
     자세한 내용은 [SharePoint 프로젝트 및 프로젝트 항목 템플릿](../sharepoint/sharepoint-project-and-project-item-templates.md)을 참조하십시오.  
  
2.  **솔루션 탐색기** 에서 프로젝트 노드를 선택한 다음 **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
3.  **새 항목 추가** 대화 상자에서, **SharePoint** 노드를 확장한 후 **2010** 노드를 선택합니다.  
  
4.  선택한 SharePoint 템플릿 목록에서 **웹 파트** 를 선택합니다.  
  
5.  **이름** 상자에서 웹 파트의 이름을 지정한 다음 **추가** 단추를 선택합니다.  
  
     **솔루션 탐색기**에 해당 웹 파트 항목이 표시됩니다.  웹 파트 포함하는 파일에 대한 자세한 내용은 [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md) 을 참조하십시오.  
  
6.  **솔루션 탐색기**에서 방금 만든 웹 파트 코드 파일을 엽니다.  
  
     예를 들어 웹 파트 이름이 WebPart1이면 WebPart1.vb\(Visual Basic\) 또는 WebPart1.cs\(C\#\)를 더블 클릭합니다.  
  
7.  코드 파일에서 <xref:System.Web.UI.Control.CreateChildControls%2A> 메서드에 컨트롤을 추가합니다.  
  
     예제를 보려면 [연습: SharePoint를 위한 웹 파트 만들기](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)를 참조하십시오.  
  
## 참고 항목  
 [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [방법: 디자이너를 사용하여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)   
 [연습: SharePoint를 위한 웹 파트 만들기](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)   
 [연습: 디자이너를 사용하여 SharePoint를 위한 웹 파트 만들기](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)  
  
  