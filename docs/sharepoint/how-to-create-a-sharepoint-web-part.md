---
title: "방법: SharePoint 웹 파트 만들기 | Microsoft Docs"
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
- Web Parts [SharePoint development in Visual Studio], adding
- Web Parts [SharePoint development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 27826859d2bac9b247132e7fcb2c3721b6d38092
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-create-a-sharepoint-web-part"></a>방법: SharePoint 웹 파트 만들기
  만들고 추가 하 여 웹 파트를 사용자 지정할 수는 **웹 파트** 을 SharePoint 프로젝트 항목 및 다음 웹 파트 또는 디자이너를 사용 하 여 코드 파일을 편집 합니다. 자세한 내용은 참조 [하는 방법: 디자이너를 사용 하 여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)합니다.  
  
### <a name="to-create-a-sharepoint-web-part"></a>SharePoint 웹 파트를 만들려면  
  
1.  SharePoint 프로젝트를 만들거나 엽니다.  
  
     자세한 내용은 참조 [SharePoint 프로젝트 및 프로젝트 항목 템플릿](../sharepoint/sharepoint-project-and-project-item-templates.md)합니다.  
  
2.  SharePoint 프로젝트 노드를 선택 **솔루션 탐색기** 선택한 후 **프로젝트**, **새 항목 추가**합니다.  
  
3.  에 **새 항목 추가** 대화 상자에서 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
4.  SharePoint 템플릿의 목록에서 선택 **웹 파트**합니다.  
  
5.  에 **이름** 상자 웹 파트에 대 한 이름을 지정 하 고 선택 합니다는 **추가** 단추입니다.  
  
     웹 파트에 표시 **솔루션 탐색기**합니다. 웹 파트에 포함 된 파일에 대 한 자세한 내용은 참조 하십시오. [SharePoint 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)합니다.  
  
6.  **솔루션 탐색기**, 방금 만든 웹 파트에 대 한 코드 파일을 엽니다.  
  
     예를 들어 웹 파트의 이름이 WebPart1인 경우 WebPart1.vb(Visual Basic) 또는 WebPart1.cs(C#)를 엽니다.  
  
7.  코드 파일에서 <xref:System.Web.UI.Control.CreateChildControls%2A> 메서드에 컨트롤을 추가합니다.  
  
     예를 들어 참조 [연습: SharePoint를 위한 웹 파트 만들기](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [방법: 디자이너를 사용 하 여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)   
 [연습: SharePoint를 위한 웹 파트 만들기](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)   
 [연습: 디자이너를 사용하여 SharePoint를 위한 웹 파트 만들기](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)  
  
  