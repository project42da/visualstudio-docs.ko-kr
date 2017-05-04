---
title: "방법: 리본 메뉴 사용자 지정 시작 | Microsoft Docs"
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
  - "사용자 지정 리본, 프로젝트에 리본 메뉴 추가"
  - "리본 메뉴 사용자 지정, 프로젝트에 리본 메뉴 추가"
  - "리본[Visual Studio에서 Office 개발], 추가"
  - "리본[Visual Studio에서 Office 개발], 사용자 지정"
ms.assetid: 9eb6b8b3-1842-4cb3-8229-273ce35c64fb
caps.latest.revision: 22
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 21
---
# 방법: 리본 메뉴 사용자 지정 시작
  Microsoft Office 응용 프로그램의 리본 메뉴를 사용자 지정하려면 Office 프로젝트에 **리본\(비주얼 디자이너\)** 또는 **리본\(XML\)** 항목을 추가합니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### 프로젝트에 리본 메뉴를 추가하려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
2.  **새 항목 추가** 대화 상자에서 **리본\(비주얼 디자이너\)** 또는 **리본\(XML\)**을 선택합니다.  이러한 템플릿에 대한 자세한 내용은 [리본 개요](../vsto/ribbon-overview.md)을 참조하십시오.  
  
3.  **이름** 상자에 리본 항목의 이름을 입력합니다.  
  
     이름에는 다음 문자를 사용할 수 없습니다.  
  
    -   파운드\(\#\)  
  
    -   백분율\(%\)  
  
    -   앰퍼샌드\(&\)  
  
    -   별표\(\*\)  
  
    -   세로줄\(|\)  
  
    -   백슬래시\(\\\)  
  
    -   콜론\(:\)  
  
    -   큰따옴표\("\)  
  
    -   보다 작음\(\<\)  
  
    -   보다 큼\(\>\)  
  
    -   물음표\(?\)  
  
    -   슬래시\(\/\)  
  
    -   선행 공백 또는 후행 공백\(' '\)  
  
    -   Windows 또는 DOS에서 예약된 이름\(예: "nul", "aux", "con", "com1", "lpt1" 등\)  
  
4.  **확인**을 클릭합니다.  
  
 리본 항목이 **솔루션 탐색기**에 나타납니다.  다음 단계에 대한 자세한 내용은 [리본 개요](../vsto/ribbon-overview.md)을 참조하십시오.  
  
## 참고 항목  
 [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [리본 XML](../vsto/ribbon-xml.md)   
 [연습: 리본 디자이너를 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [연습: 리본 XML을 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  