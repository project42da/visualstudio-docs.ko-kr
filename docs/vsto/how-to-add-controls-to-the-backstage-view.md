---
title: "방법: Backstage 보기에 컨트롤 추가"
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
  - "컨트롤, 리본 메뉴"
  - "사용자 지정 리본, 메뉴"
  - "리본 메뉴 사용자 지정, 메뉴"
  - "메뉴, 사용자 지정"
  - "Microsoft Office 단추"
  - "Microsoft Office 메뉴"
  - "Office 단추"
  - "리본 메뉴, 사용자 지정"
  - "리본 메뉴, 메뉴"
ms.assetid: 4fda1278-9aea-4d54-928a-269a81584494
caps.latest.revision: 30
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 29
---
# 방법: Backstage 보기에 컨트롤 추가
  리본 디자이너를 사용 하 여 컨트롤을 클릭 하면 열리는 메뉴를 추가 하 여  **파일** 탭입니다.  응용 프로그램을 추가 하는 컨트롤을 실행할 때의  **파일** 탭 표시 라는 그룹이  **추가 기능**.  
  
 Visual Studio 리본 디자이너를 사용 하 여 기본 제공 컨트롤 전후 컨트롤을 배치할 수 없습니다.  기본 제공 컨트롤 Backstage 보기에서 나타나는 컨트롤이입니다.  기본 제공 컨트롤의 앞이나 뒤에 컨트롤을 배치하려면 리본 XML을 사용해야 합니다.  에 대 한 자세한 내용은  **리본 \(XML\)**을 참조 하십시오 [리본 XML](../vsto/ribbon-xml.md).  Backstage 보기를 사용자 지정하는 방법에 대한 자세한 내용은 [Introduction to the Office 2010 Backstage View for Developers](http://go.microsoft.com/fwlink/?LinkId=182189) 및 [Customizing the Office 2010 Backstage View for Developers](http://go.microsoft.com/fwlink/?LinkId=182188)를 참조하십시오.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### Backstage 보기에 컨트롤을 추가 하려면  
  
1.  디자인 뷰에서 리본 항목을 엽니다.  
  
     프로젝트에 **리본\(비주얼 디자이너\)** 항목을 추가하는 방법에 대한 자세한 내용은 [방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)을 참조하십시오.  
  
2.  리본 디자이너를 클릭 하 여  **파일** 탭입니다.  
  
     메뉴 디자이너가 나타납니다.  이 디자인 화면에는 컨트롤이 들어 있지 않습니다.  
  
3.  **도구 상자**의 **Office 리본 컨트롤** 탭에서 다음 컨트롤을 메뉴 디자이너로 끌어 옵니다.  
  
    -   Button  
  
    -   CheckBox  
  
    -   Gallery  
  
    -   메뉴  
  
    -   Separator  
  
    -   SplitButton  
  
    -   ToggleButton  
  
4.  컨트롤을 끌어 메뉴의 새 위치로 이동합니다.  
  
## 참고 항목  
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [리본 XML](../vsto/ribbon-xml.md)   
 [방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [연습: 리본 디자이너를 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)  
  
  