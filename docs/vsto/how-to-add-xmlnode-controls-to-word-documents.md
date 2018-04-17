---
title: '방법: Word 문서에 XMLNode 컨트롤 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLNode control, adding to documents
- controls [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4dd214262f66bfa21cdb168e948c70437487761e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-xmlnode-controls-to-word-documents"></a>방법: Word 문서에 XMLNode 컨트롤 추가
  **중요 한** Microsoft Word에 대 한이 항목에 정보는 이점과 개인 및 United States 및 해당 지역 외부에 있는 사용자 또는 사용자를 사용 하는 조직의 사용에 대해 독점적으로 발표 된 또는 개발 실행 되는 프로그램, Microsoft Word 2010 년 1 월, Microsoft 구현의 특정 기능을 제거 하는 경우 하기 전에 Microsoft에서 사용이 허가 된 제품에서에서와 관련 된 사용자 지정 XML Microsoft Word입니다. Microsoft Word에 대 한이 정보를 읽거나 개인 이나 조직에는 미국이 나 Microsoft Word 2010 년 1 월 10 일 이후에 Microsoft에서 사용이 허가 된 제품에서 실행 되는 프로그램을 개발 하거나를 사용 하는 사용자의 지역에서 사용 될 수 있습니다. ; 이러한 제품 해당 날짜 이전에 사용이 허가 또는 구입 해야 하 고 미국 이외의 용도로 사용이 허가 된 제품와 동일 하 게 작동 하지 않습니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Microsoft Office Word 문서에 반복 되지 않는 XML 스키마 요소를 매핑할 때 자동으로 추가 된 <xref:Microsoft.Office.Tools.Word.XMLNode> 컨트롤을 문서로 합니다. 매핑 XML 스키마 요소를 반복 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Word 문서에 XMLNodes 컨트롤 추가](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md)합니다.  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Word.XMLNode> 컨트롤에서 지원 하지 않는 **도구 상자** 또는 **데이터 소스** 창 프로그래밍 방식으로 만들 수 없습니다.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-an-xmlnode-control-to-a-document"></a>문서에 XMLNode 컨트롤을 추가 하려면  
  
1.  리본 메뉴에서 Visual Studio 디자이너에서 문서에서 클릭 된 **개발자** 탭 합니다.  
  
    > [!NOTE]  
    >  **개발자** 탭이 표시되지 않는 경우 먼저 개발자 탭을 표시해야 합니다. 자세한 내용은 [방법: 리본 메뉴에 개발 도구 탭 표시](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)을 참조하세요.  
  
2.  에 **XML** 그룹에서 클릭 **스키마**합니다.  
  
     **템플릿 및 추가 기능** 대화 상자가 열립니다.  
  
3.  클릭는 **XML 스키마** 탭 합니다.  
  
4.  클릭 **스키마 추가**합니다.  
  
     **스키마 추가** 대화 상자가 열립니다.  
  
5.  -반복 되지 않는 스키마 요소를 포함 하는 XML 스키마를 선택는 **스키마 추가** 대화 상자와 클릭 **열려**합니다.  
  
     **스키마 설정** 대화 상자가 나타납니다.  
  
6.  별칭을 지정 하거나 클릭 **확인** 별칭 없이 스키마를 추가 합니다.  
  
     스키마에 추가 되는 **스키마 추가** 대화 상자.  
  
7.  에 **스키마 추가** 대화 상자를 클릭 **확인**합니다.  
  
8.  **XML 구조** 작업창이 열립니다.  
  
9. -반복 되지 않는 스키마 요소를 클릭할는 **XML 구조** 작업창은 문서에 추가 합니다.  
  
     <xref:Microsoft.Office.Tools.Word.XMLNode> 컨트롤이 만들어지고 프로젝트에 추가 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XMLNode 컨트롤](../vsto/xmlnode-control.md)   
 [확장 된 개체를 사용 하 여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  