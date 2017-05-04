---
title: "방법: 이벤트 수신자 만들기 | Microsoft Docs"
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
  - "VS.SharePointTools.SPE.EventReceiver"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "이벤트 수신자[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 이벤트 수신자"
ms.assetid: 6f90cb48-eb8f-43c2-a3f7-ed4ce81aedf2
caps.latest.revision: 20
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 19
---
# 방법: 이벤트 수신자 만들기
  *이벤트 수신기* 를 생성하여 사용자가 목록 또는 목록 항목과 같은 SharePoint 항목을 사용할 때 응답할 수 있습니다.  예를 들어, 일정을 변경하거나 연락처 목록에서 이름을 삭제하면 이벤트 수신자의 코드가 트리거됩니다.  이 항목에 따라 목록 인스턴스에 이벤트 수신자를 추가 하는 방법을 배울 수 있습니다.  
  
 이러한 단계를 완료 하려면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 와 SharePoint 및 Windows 지원 버전을 설치해야 합니다.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  이 예제에서는 SharePoint 프로젝트를 하기 때문에, [연습: SharePoint용 사이트 열, 콘텐츠 형식 및 목록 만들기](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md) 항목의 절차도 완료 해야 합니다.  
  
## 이벤트 수신자 추가  
 [연습: SharePoint용 사이트 열, 콘텐츠 형식 및 목록 만들기](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md) 에서 만든 프로젝트는 사용자 지정 사이트 열, 목록, 그리고 콘텐츠 형식을 포합합니다.  다음 절차에서는 목록과 같은 SharePoint 항목에서 일어나는 이벤트들을 처리하는 방법을 보여주기 위해 간단한 이벤트 처리기 \(이벤트 수신자\) 를 목록 인스턴스에 추가하여 이 프로젝트를 확장할 것입니다.  
  
#### 목록 인스턴스에 이벤트 수신자를 추가하려면  
  
1.  [연습: SharePoint용 사이트 열, 콘텐츠 형식 및 목록 만들기](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)에서 만든 프로젝트를 엽니다.  
  
2.  **솔루션 탐색기**에서, **연구소** SharePoint 프로젝트 노드를 선택합니다.  
  
3.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택합니다.  
  
4.  **Visual C\#** 또는 **Visual Basic** 에서 **SharePoint** 노드를 확장한 다음 **2010** 항목을 선택합니다.  
  
5.  **템플릿** 창에서 **이벤트 수신기** 를 선택하고, TestEventReceiver1 로 명명한 다음, **확인** 버튼을 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  
  
6.  **원하는 이벤트 수신자 유형을 선택하십시오.** 목록에서 **목록 항목 이벤트**를 선택합니다.  
  
7.  **이벤트 소스에 대한 항목을 선택하십시오.** 목록에서 **환자 \(Clinic\\Patients\)** 를 선택합니다.  
  
8.  **다음 이벤트를 처리** 목록에서 **항목이 추가되었습니다** 확인란을 선택한 다음 **완료** 버튼을 선택합니다.  
  
     새 이벤트 수신자 코드 파일에는 `ItemAdded`라는 단일 메서드가 포함되어 있습니다.  다음 단계에서는 이 메서드에 코드를 추가하여 모든 연락처가 기본적으로 Scott Brown 으로 명명되도록 합니다.  
  
9. 기존 `ItemAdded` 메서드를 다음 코드로 바꾼 다음 F5 키를 누릅니다.  
  
     [!code-csharp[SP_EventReceiver#1](../snippets/csharp/VS_Snippets_OfficeSP/sp_eventreceiver/CS/CustomField1/TestEventReceiver1/TestEventReceiver1.cs#1)]
     [!code-vb[SP_EventReceiver#1](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_eventreceiver/VB/CustomField1_VB/EventReceiver1/EventReceiver1.vb#1)]  
  
     코드는 실행되고 SharePoint 사이트가 웹 브라우저에 나타납니다.  
  
10. 빠른 실행 표시줄에서 **환자** 링크를 선택한 다음 **새 항목 추가** 링크를 선택합니다.  
  
     새 항목에 대한 입력 폼이 열립니다.  
  
11. 필드에 데이터를 입력한 다음 **저장** 버튼을 선택합니다.  
  
     **저장** 버튼을 선택한 후 **환자 이름** 열이 Scott Brown 이라는 이름으로 자동으로 업데이트 합니다.  
  
## 참고 항목  
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)  
  
  