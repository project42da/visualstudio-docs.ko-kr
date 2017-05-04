---
title: "방법: Visual Studio 내부의 Word 문서에 스키마 매핑 | Microsoft Docs"
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
  - "매핑[Visual Studio에서 Office 개발], XML 스키마를 Word 문서에"
  - "Word[Visual Studio에서 Office 개발], XML 스키마 매핑"
  - "XML 스키마[Visual Studio에서 Office 개발], 매핑"
ms.assetid: 9bfb3c7b-6392-45bd-b4c1-b2012b9ded69
caps.latest.revision: 27
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 26
---
# 방법: Visual Studio 내부의 Word 문서에 스키마 매핑
  **중요 한** Microsoft Word와 관련 된이 항목에 설정 된 정보 혜택 및 개인과 누가 미국과 해당 영토 밖에 위치한 되 나 누구를 사용 하 여 또는 2010 년 1 월 Microsoft 제거 경우 Microsoft Word에서 사용자 지정 XML에 관련 된 특정 기능을 구현 하기 전에 Microsoft에서 사용이 허가 된 제품을 Microsoft Word를 실행 하는 프로그램 개발 회사의 사용에 대 한 독점적으로 제공 됩니다.  Microsoft Word에 대한 정보는 2010년 1월 10일 이후 Microsoft에서 사용 허가를 받고 Microsoft Word에서 실행되는 프로그램을 사용 또는 개발하고 있는 미국 또는 미국 자치령의 개인 또는 조직에서 읽거나 사용하지 못할 수 있습니다. 이런 제품은 해당 날짜 이전에 사용 허가를 받거나 미국이 아닌 다른 곳에서 사용하기 위해 구매하고 사용 허가를 받은 동일한 제품처럼 작동하지 않습니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 문서가 Visual Studio에 열려 있는 동안 XML 스키마를 문서에 매핑할 수 있습니다.  이 경우 문서가 Visual Studio 외부에 열려 있을 때 사용하는 것과 동일한 Microsoft Office Word 도구를 사용합니다.  Word 솔루션을 만들기 전에 스키마를 문서에 매핑하는지 응용 프로그램을 만든 후에 매핑하는지 여부에 상관없이 Office 프로젝트에서는 동일한 개체를 만듭니다.  
  
### Visual Studio에서 Word 문서에 XML 스키마를 매핑하려면  
  
1.  Visual Studio 내에서 Word 문서 또는 서식 파일 프로젝트를 엽니다.  
  
2.  문서를 클릭하여 디자이너로 포커스를 옮깁니다.  
  
3.  리본 메뉴에서 **개발 도구** 탭을 클릭합니다.  
  
    > [!NOTE]  
    >  **개발 도구** 탭이 표시되지 않으면 먼저 이 탭을 표시해야 합니다.  자세한 내용은 [방법: 리본 메뉴에 개발 도구 탭 표시](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)을 참조하십시오.  
  
4.  **XML** 그룹에서 **스키마**를 클릭합니다.  
  
     **서식 파일 및 추가 기능** 대화 상자가 열립니다.  
  
5.  **XML 스키마** 탭을 클릭합니다.  
  
6.  **스키마 추가**를 클릭합니다.  
  
     **스키마 추가** 대화 상자가 열립니다.  
  
7.  스키마 파일을 찾아 선택한 다음 **열기**를 클릭합니다.  
  
     **스키마 설정** 대화 상자가 열립니다.  
  
8.  별칭을 할당합니다. 별칭 없이 스키마를 추가하려면 **확인**을 클릭합니다.  
  
9. **확인**을 클릭합니다.  
  
     **XML 구조** 창이 열립니다.  
  
10. **XML 구조** 창에서 문서의 원하는 위치로 요소를 끌어와 해당 컨트롤을 만듭니다.  
  
## 참고 항목  
 [방법: Visual Studio 내에서 워크시트에 스키마 매핑](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)   
 [문서 수준 사용자 지정의 XML 스키마 및 데이터](../vsto/xml-schemas-and-data-in-document-level-customizations.md)  
  
  