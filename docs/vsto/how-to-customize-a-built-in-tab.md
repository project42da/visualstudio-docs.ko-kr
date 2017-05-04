---
title: "방법: 기본 제공 탭 사용자 지정 | Microsoft Docs"
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
  - "기본 제공 탭[Visual Studio에서 Office 개발]"
  - "리본[Visual Studio에서 Office 개발], 탭"
ms.assetid: 197a7aaa-a51d-496c-b904-b9421849fad9
caps.latest.revision: 28
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 27
---
# 방법: 기본 제공 탭 사용자 지정
  기본 제공 탭에 그룹과 컨트롤을 추가할 수 있습니다.  기본 제공 탭은 Microsoft Office 응용 프로그램의 리본 메뉴에 이미 있는 탭입니다.  예를 들어 **데이터** 탭은 Excel의 기본 제공 탭입니다.  사용자 지정 그룹을 만드는 경우 탭에서 마지막에 표시되지만 탭의 아무곳으로나 그룹을 이동할 수 있습니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
> [!NOTE]  
>  기본 제공 탭에 그룹을 추가할 수 있지만 기본 제공 탭에서 기본 제공 그룹을 제거할 수는 없습니다.  
  
### 기본 제공 탭에 그룹을 추가하려면  
  
1.  **솔루션 탐색기**에서 리본 코드 파일을 마우스 오른쪽 단추로 클릭하고 **뷰 디자이너**를 클릭합니다.  
  
    > [!NOTE]  
    >  리본 코드 파일이 **솔루션 탐색기**에 표시되지 않는 경우 **리본 항목**을 프로젝트에 추가해야 합니다.  [방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)을 참조하세요.  
  
2.  리본 디자이너에서 임의 탭을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  
  
3.  **속성** 창에서 **ControlId** 속성을 확장하고 **ControlIdType** 속성을 **Office**로 설정합니다.  
  
4.  **OfficeId** 속성을 사용자 지정하려는 기본 제공 탭의 *컨트롤 ID*로 설정합니다.  
  
     컨트롤 ID는 Microsoft Office 응용 프로그램에 기본 제공된 탭, 그룹 및 컨트롤을 고유하게 식별하는 이름입니다.  
  
     컨트롤 ID 목록은 [Office 2010 도움말 파일: Office Fluent 사용자 인터페이스 컨트롤 식별자](http://go.microsoft.com/fwlink/?LinkID=181052)\(영문\)를 참조하세요.  
  
5.  **도구 상자**의 **Office 리본 컨트롤** 탭에 있는 그룹을 탭으로 끌어옵니다.  
  
    > [!NOTE]  
    >  기본 제공 그룹은 디자이너에 표시되지 않습니다.  따라서 기본 제공 탭을 사용 중인지 확인하는 방법은 탭의 **ControlId** 속성을 검사하는 것뿐입니다.  
  
### 기본 제공 탭에 그룹을 배치하려면  
  
1.  리본 디자이너에서 사용자 지정 그룹을 선택합니다.  
  
2.  **속성** 창에서 **Position** 속성을 확장합니다.  
  
3.  **PositionType** 속성을 적절한 값으로 설정합니다.  
  
    -   **BeforeOfficeId**는 지정된 기본 제공 그룹 앞에 그룹을 배치합니다.  
  
    -   **AfterOfficeId**는 지정된 기본 제공 그룹 뒤에 그룹을 배치합니다.  
  
4.  **OfficeId** 속성을 기본 제공 그룹의 컨트롤 ID로 설정합니다.  
  
     컨트롤 ID 목록은 [Office 2010 도움말 파일: Office Fluent 사용자 인터페이스 컨트롤 식별자](http://go.microsoft.com/fwlink/?LinkID=181052)\(영문\)를 참조하세요.  
  
## 참고 항목  
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [리본 XML](../vsto/ribbon-xml.md)   
 [연습: 리본 디자이너를 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [연습: 리본 XML을 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)   
 [방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [방법: 리본의 탭 위치 변경](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)   
 [방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)   
 [방법: 추가 기능 사용자 인터페이스 오류 표시](../vsto/how-to-show-add-in-user-interface-errors.md)  
  
  