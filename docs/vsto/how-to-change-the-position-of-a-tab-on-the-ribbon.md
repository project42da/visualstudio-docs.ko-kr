---
title: "방법: 리본의 탭 위치 변경"
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
  - "리본[Visual Studio에서 Office 개발], 탭"
ms.assetid: 3f0906e3-9708-4136-ac49-986bc4c92ea4
caps.latest.revision: 26
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 25
---
# 방법: 리본의 탭 위치 변경
  **탭 컬렉션 편집기**를 사용하여 리본 메뉴의 사용자 지정 탭 순서를 변경할 수 있습니다.  리본 메뉴의 기본 제공 탭 앞이나 뒤에 사용자 지정 탭을 배치할 수 있습니다.  기본 제공 탭은 Microsoft Office 응용 프로그램의 리본 메뉴에 이미 있는 탭입니다.  예를 들어 **데이터** 탭은 Excel의 기본 제공 탭입니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### 리본 메뉴의 탭 순서를 변경하려면  
  
1.  **솔루션 탐색기**에서 리본 코드 파일\(.vb 또는 .cs 파일\)을 선택합니다.  
  
2.  **보기** 메뉴에서 **디자이너**를 클릭합니다.  
  
3.  리본 디자이너를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
4.  **속성** 창에서 **Tabs** 속성을 선택하고 줄임표 단추\(![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.png "ASP.NET 모바일 디자이너 줄임표")\)를 클릭합니다.  
  
     **탭 컬렉션 편집기**가 나타납니다.  
  
5.  **탭 컬렉션 편집기**의 **멤버** 목록에서 이동할 탭을 선택하고 위쪽 또는 아래쪽 화살표를 클릭하여 탭 순서를 변경합니다.  
  
### 리본 메뉴의 기본 제공 탭 앞이나 뒤에 탭을 배치하려면  
  
1.  리본 디자이너에서 사용자 지정 탭을 선택합니다.  
  
2.  에  **속성** 창 확장의  **ControlId** 속성을 및 다음 있는지 확인 값의  **ControlIdType** 속성이  **사용자 지정**.  
  
3.  **속성** 창에서 **위치** 속성을 확장합니다.  
  
4.  **PositionType** 속성을 적절한 값으로 설정합니다.  
  
    -   **BeforeOfficeId** \- 그룹을 지정된 기본 제공 탭 앞에 배치합니다.  
  
    -   **AfterOfficeId** \- 그룹을 지정된 기본 제공 탭 뒤에 배치합니다.  
  
5.  **OfficeId** 속성을 기본 제공 탭의 컨트롤 ID로 설정합니다.  
  
     컨트롤 Id 목록을 보려면 참조 하십시오 [Office 2010 도움말 파일: Office Fluent 사용자 인터페이스 컨트롤 식별자](http://go.microsoft.com/fwlink/?LinkID=181052).  
  
## 참고 항목  
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [리본 XML](../vsto/ribbon-xml.md)   
 [연습: 리본 디자이너를 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [연습: 리본 XML을 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  