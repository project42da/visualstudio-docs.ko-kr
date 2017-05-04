---
title: "방법: 리본 그룹에 대화 상자 시작 관리자 추가 | Microsoft Docs"
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
  - "대화 상자 표시 아이콘[Visual Studio에서 Office 개발]"
  - "리본[Visual Studio에서 Office 개발], 대화 상자 표시 아이콘"
ms.assetid: 5972664f-4e37-4dc6-90d0-69cedd057e60
caps.latest.revision: 19
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 18
---
# 방법: 리본 그룹에 대화 상자 시작 관리자 추가
  리본 메뉴의 그룹에 대화 상자 표시 아이콘을 추가할 수 있습니다.  대화 상자 표시 아이콘은 그룹에 나타나는 작은 아이콘입니다.  이 아이콘을 클릭하면 해당 그룹과 관련된 추가 옵션을 제공하는 관련 대화 상자 또는 작업 창이 열립니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### 리본 그룹에 대화 상자 표시 아이콘을 추가하려면  
  
1.  **솔루션 탐색기**에서 리본 코드 파일\(.vb 또는 .cs 파일\)을 선택합니다.  
  
2.  **보기** 메뉴에서 **디자이너**를 클릭합니다.  
  
3.  리본 디자이너에서 그룹을 마우스 오른쪽 단추로 클릭하고 **DialogBoxLauncher 추가**를 클릭합니다.  
  
     그룹의 <xref:Microsoft.Office.Tools.Ribbon.RibbonGroup.DialogLauncherClick> 이벤트에 사용자 지정 또는 기본 제공 대화 상자를 여는 코드를 추가합니다.  
  
## 참고 항목  
 [리본 개요](../vsto/ribbon-overview.md)   
 [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [리본 개체 모델 개요](../vsto/ribbon-object-model-overview.md)   
 [리본 XML](../vsto/ribbon-xml.md)   
 [방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [방법: 리본의 탭 위치 변경](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)   
 [방법: 기본 제공 탭 사용자 지정](../vsto/how-to-customize-a-built-in-tab.md)   
 [방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)   
 [Outlook에 대해 리본 메뉴 사용자 지정](../vsto/customizing-a-ribbon-for-outlook.md)   
 [방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [방법: 추가 기능 사용자 인터페이스 오류 표시](../vsto/how-to-show-add-in-user-interface-errors.md)   
 [연습: 리본 디자이너를 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [연습: 런타임에 리본 메뉴의 컨트롤 업데이트](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)   
 [연습: 리본 XML을 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  