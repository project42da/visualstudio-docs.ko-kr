---
title: "워크플로의 폼 지원"
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
helpviewer_keywords: 
  - "Visual Studio에서 SharePoint 개발, 워크플로"
  - "워크플로[Visual Studio에서 SharePoint 개발]"
ms.assetid: 1706f6a2-ea84-4234-85ae-19feb8540507
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# 워크플로의 폼 지원
  워크플로에서 사용할 수 있는 네 가지 유형의 양식은 연결, 시작, 작업 및 수정입니다.  이러한 양식 유형은 ASPX 양식이나 InfoPath 양식을 기반으로 할 수 있습니다.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 특정 양식에 제공하는 지원 수준은 다음 표에서 설명하는 몇 가지 요소에 따라 결정됩니다.  워크플로 양식 유형에 대한 자세한 내용은 MSDN 웹 사이트에서 [워크플로 양식 개요](http://go.microsoft.com/fwlink/?LinkId=185228) 를 참조하십시오.  
  
## XML 리팩터링  
 ASPX 연결 또는 시작 양식을 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 워크플로 프로젝트 항목에 추가하는 경우 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 워크플로의 Elements.xml 파일에서 XML을 자동으로 리팩터링하여 양식 이름이나 배포 경로가 업데이트되거나 양식이 삭제될 때마다 연결 또는 시작 양식을 참조하는 특성을 동기화 상태로 유지합니다.  그러나 워크플로에서 작업 양식이나 수정 양식 등의 다른 양식 유형을 사용하는 경우 Elements.xml 파일이 리팩터링되지 않습니다.  
  
## 새 Visual Studio 워크플로의 양식 지원  
 다음 표에는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 만들어진 워크플로에서 ASPX 또는 InfoPath 양식의 다른 양식 유형에 대한 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 지원이 나와 있습니다.  
  
|양식 유형|ASPX 양식을 사용하여 Visual Studio에서 만들어진 워크플로|InfoPath 양식을 사용하여 Visual Studio에서 만들어진 워크플로|  
|-----------|---------------------------------------------|-------------------------------------------------|  
|연결|-   ASPX 연결 양식은 **워크플로 연결 양식** 항목 템플릿을 사용하여 워크플로에 추가할 수 있습니다.<br />-   워크플로의 Elements.xml 파일은 양식을 추가하거나, 양식의 이름을 바꾸거나, 양식을 삭제할 때 또는 배포 경로가 변경될 때 리팩터링됩니다.<br />-   자세한 내용은 [연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)을 참조하십시오.|-   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에는 InfoPath 연결 양식 템플릿이 없습니다.<br />-   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]와 InfoPath Designer 간의 통합이 없습니다.<br />-   워크플로의 Elements.xml 파일은 리팩터링되지 않습니다.|  
|시작|-   ASPX 시작 양식은 **워크플로 시작 양식** 항목 템플릿을 사용하여 워크플로에 추가할 수 있습니다.<br />-   워크플로의 Elements.xml 파일은 양식을 추가하거나, 양식의 이름을 바꾸거나, 양식을 삭제할 때 또는 배포 경로가 변경될 때 리팩터링됩니다.<br />-   자세한 내용은 [연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)을 참조하십시오.|-   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에는 InfoPath 연결 양식 템플릿이 없습니다.<br />-   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]와 InfoPath Designer 간의 통합이 없습니다.<br />-   워크플로의 Elements.xml 파일은 리팩터링되지 않습니다.|  
|Task|-   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 ASPX 작업 양식 템플릿을 사용할 수 없습니다.  응용 프로그램 페이지를 만들고 이 페이지에 코드를 추가해야 합니다.<br />-   워크플로의 Elements.xml 파일은 리팩터링되지 않습니다.<br />-   자세한 내용은 [워크플로 작업 양식 \(SharePoint 기반\)](http://go.microsoft.com/fwlink/?LinkId=187674) 을 참조하십시오.|-   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에는 InfoPath 작업 양식 템플릿이 없습니다.<br />-   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]와 InfoPath Designer 간의 통합이 없습니다.<br />-   워크플로의 Elements.xml 파일은 리팩터링되지 않습니다.|  
|수정|-   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 ASPX 수정 양식 템플릿을 사용할 수 없습니다.  수정 양식을 추가하려면 응용 프로그램 페이지를 만들고 이 페이지에 코드를 추가해야 합니다.<br />-   워크플로의 Elements.xml 파일은 리팩터링되지 않습니다.  필요에 따라 수동으로 이 파일을 편집해야 합니다.<br />-   자세한 내용은 [워크플로 수정 양식 \(SharePoint 기반\)](http://go.microsoft.com/fwlink/?LinkId=187675)|-   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에는 InfoPath 수정 양식 템플릿이 없습니다.<br />-   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]와 InfoPath Designer 간의 통합이 없습니다.<br />-   워크플로의 Elements.xml 파일은 리팩터링되지 않습니다.|  
  
## 가져온 SharePoint 재사용 가능한 워크플로의 양식 지원  
 다음 표에는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]로 가져온 SharePoint 재사용 가능한 워크플로에서 ASPX 또는 InfoPath 양식의 다른 양식 유형에 대한 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 지원이 나와 있습니다.  
  
|양식 유형|SharePoint Designer에서 가져온 ASPX 양식이 있는 재사용 가능한 워크플로|SharePoint Designer에서 가져온 InfoPath 양식이 있는 재사용 가능한 워크플로|  
|-----------|--------------------------------------------------------|------------------------------------------------------------|  
|연결|-   양식이 워크플로의 Elements.xml 파일에서 참조됩니다.<br />-   워크플로의 Elements.xml 파일은 양식의 이름을 바꾸거나 양식을 삭제할 때 또는 배포 경로가 변경될 때 리팩터링됩니다.|-   양식을 가져오게 되지만 양식이 워크플로의 Elements.xml에서 참조되지 않습니다.<br />-   워크플로의 Elements.xml 파일은 리팩터링되지 않습니다.|  
|시작|-   양식이 워크플로의 Elements.xml 파일에서 워크플로에 의해 참조됩니다.<br />-   워크플로의 Elements.xml 파일은 양식의 이름을 바꾸거나 양식을 삭제할 때 또는 배포 경로가 변경될 때 리팩터링됩니다.|-   양식을 가져오게 되지만 양식이 워크플로의 Elements.xml에서 참조되지 않습니다.<br />-   워크플로의 Elements.xml 파일은 리팩터링되지 않습니다. **Note:**  이 시나리오가 작동하려면 규칙과 속성을 추가하고 변경해야 합니다.|  
|Task|-   양식이 워크플로의 Elements.xml 파일에서 참조됩니다.<br />-   워크플로의 Elements.xml 파일은 리팩터링되지 않습니다.|-   양식을 가져오게 되지만 양식이 워크플로의 Elements.xml에서 참조되지 않습니다.<br />-   워크플로의 Elements.xml 파일은 리팩터링되지 않습니다. **Note:**  이 시나리오가 작동하려면 규칙과 속성을 추가하고 변경해야 합니다.|  
|수정|해당 사항 없음.  ASPX 수정 양식은 SharePoint Designer에서 만들 수 없습니다.|해당 사항 없음.  워크플로를 내보낼 때 .wsp 파일에 포함되지 않는 기본 제공 SharePoint Server 워크플로를 제외하고 InfoPath 수정 양식은 SharePoint Designer에서 만들 수 없습니다.|  
  
## 참고 항목  
 [연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)   
 [SharePoint 워크플로 솔루션 만들기](../sharepoint/creating-sharepoint-workflow-solutions.md)   
 [기존 SharePoint 사이트에서 항목 가져오기](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)  
  
  