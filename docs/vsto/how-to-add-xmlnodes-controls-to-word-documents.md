---
title: "방법: Word 문서에 XMLNodes 컨트롤 추가"
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
  - "컨트롤[Visual Studio에서 Office 개발], 문서에 추가"
  - "XMLNodes 컨트롤, 문서에 추가"
ms.assetid: 315c6def-51f6-4ba6-bd9e-55cdf70f15bf
caps.latest.revision: 28
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 27
---
# 방법: Word 문서에 XMLNodes 컨트롤 추가
  **중요 한** Microsoft Word와 관련 된이 항목에 설정 된 정보 혜택 및 개인과 누가 미국과 해당 영토 밖에 위치한 되 나 누구를 사용 하 여 또는 2010 년 1 월 Microsoft 제거 경우 Microsoft Word에서 사용자 지정 XML에 관련 된 특정 기능을 구현 하기 전에 Microsoft에서 사용이 허가 된 제품을 Microsoft Word를 실행 하는 프로그램 개발 회사의 사용에 대 한 독점적으로 제공 됩니다.  Microsoft Word에 대한 정보는 2010년 1월 10일 이후 Microsoft에서 사용 허가를 받고 Microsoft Word에서 실행되는 프로그램을 사용 또는 개발하고 있는 미국 또는 미국 자치령의 개인 또는 조직에서 읽거나 사용하지 못할 수 있습니다. 이런 제품은 해당 날짜 이전에 사용 허가를 받거나 미국이 아닌 다른 곳에서 사용하기 위해 구매하고 사용 허가를 받은 동일한 제품처럼 작동하지 않습니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 반복되는 XML 스키마 요소를 Microsoft Office Word 문서에 매핑할 때 Visual Studio에서는 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤을 문서에 자동으로 추가합니다.  
  
 반복되지 않는 XML 스키마 요소 매핑에 대한 자세한 내용은 [방법: Word 문서에 XMLNode 컨트롤 추가](../vsto/how-to-add-xmlnode-controls-to-word-documents.md)를 참조하십시오.  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤은 **도구 상자**나 **데이터 소스** 창에서 사용할 수 없고 프로그래밍 방식으로 만들 수도 없습니다.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### 문서에 XMLNodes 컨트롤을 추가하려면  
  
1.  Visual Studio 디자이너의 문서 리본 메뉴에서 **개발자** 탭을 클릭합니다.  
  
    > [!NOTE]  
    >  **개발 도구** 탭이 표시되지 않으면 먼저 이 탭을 표시해야 합니다.  자세한 내용은 [방법: 리본 메뉴에 개발 도구 탭 표시](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)을 참조하십시오.  
  
2.  **XML** 그룹에서 **스키마**를 클릭합니다.  
  
     **서식 파일 및 추가 기능** 대화 상자가 열립니다.  
  
3.  **XML 스키마** 탭을 클릭합니다.  
  
4.  **스키마 추가**를 클릭합니다.  
  
     **스키마 추가** 대화 상자가 열립니다.  
  
5.  반복되는 스키마 요소를 포함하는 XML 스키마를 선택하고 **열기**를 클릭합니다.  
  
     **스키마 설정** 대화 상자가 나타납니다.  
  
6.  별칭을 할당합니다. 별칭 없이 스키마를 추가하려면 **확인**을 클릭합니다.  
  
     **스키마 추가** 대화 상자에 스키마가 추가됩니다.  
  
7.  **스키마 추가** 대화 상자에서 **확인**을 클릭합니다.  
  
     **XML 구조** 작업 창이 열립니다.  
  
8.  반복되는 스키마 요소를 **XML 구조** 작업 창에서 클릭하여 문서에 추가합니다.  
  
     <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤이 작성되고 프로젝트에 추가됩니다.  
  
## 참고 항목  
 [XMLNodes 컨트롤](../vsto/xmlnodes-control.md)   
 [확장된 개체를 사용하여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  