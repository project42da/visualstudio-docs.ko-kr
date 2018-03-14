---
title: "방법: Visual Studio 내부의 Word 문서에 스키마 매핑 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XML schemas [Office development in Visual Studio], mapping
- mappings [Office development in Visual Studio], XML schemas to Word documents
- Word [Office development in Visual Studio], mapping XML schemas
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 65ecd3adbeb6f554a901345c2fa5dbf8359a1428
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-map-schemas-to-word-documents-inside-visual-studio"></a>방법: Visual Studio 내부의 Word 문서에 스키마 매핑
  **중요 한** Microsoft Word에 대 한이 항목에 정보는 이점과 개인 및 United States 및 해당 지역 외부에 있는 사용자 또는 사용자를 사용 하는 조직의 사용에 대해 독점적으로 발표 된 또는 개발 실행 되는 프로그램, Microsoft Word 2010 년 1 월, Microsoft 구현의 특정 기능을 제거 하는 경우 하기 전에 Microsoft에서 사용이 허가 된 제품에서에서와 관련 된 사용자 지정 XML Microsoft Word입니다. Microsoft Word에 대 한이 정보를 읽거나 개인 이나 조직에는 미국이 나 Microsoft Word 2010 년 1 월 10 일 이후에 Microsoft에서 사용이 허가 된 제품에서 실행 되는 프로그램을 개발 하거나를 사용 하는 사용자의 지역에서 사용 될 수 있습니다. ; 이러한 제품 해당 날짜 이전에 사용이 허가 또는 구입 해야 하 고 미국 이외의 용도로 사용이 허가 된 제품와 동일 하 게 작동 하지 않습니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 문서가 Visual Studio에서 열려 있는 동안에 XML 스키마 문서에 매핑할 수 있습니다. Visual Studio 외부에서 문서가 열릴 때 사용 하는 동일한 Microsoft Office Word 도구를 사용 합니다. Office 프로젝트는 해당 문서에 스키마 매핑 여부 Word 솔루션을 만든 후 동일한 개체를 만듭니다.  
  
### <a name="to-map-an-xml-schema-to-a-word-document-in-visual-studio"></a>Visual Studio에서 Word 문서에 XML 스키마를 매핑할 수  
  
1.  Visual Studio 내부의 Word 문서 또는 서식 파일 프로젝트를 엽니다.  
  
2.  문서에서 디자이너에 포커스를 이동를 클릭 합니다.  
  
3.  리본에서 **개발자** 탭을 클릭합니다.  
  
    > [!NOTE]  
    >  **개발자** 탭이 표시되지 않는 경우 먼저 개발자 탭을 표시해야 합니다. 자세한 내용은 [방법: 리본 메뉴에 개발 도구 탭 표시](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)을 참조하세요.  
  
4.  에 **XML** 그룹에서 클릭 **스키마**합니다.  
  
     **템플릿 및 추가 기능** 대화 상자가 열립니다.  
  
5.  클릭는 **XML 스키마** 탭 합니다.  
  
6.  클릭 **스키마 추가**합니다.  
  
     **스키마 추가** 대화 상자가 열립니다.  
  
7.  스키마 파일을 찾아를 선택한 다음 클릭 **열려**합니다.  
  
     **스키마 설정** 대화 상자가 열립니다.  
  
8.  별칭을 지정 하거나 클릭 **확인** 별칭 없이 스키마를 추가 합니다.  
  
9. **확인**을 클릭합니다.  
  
     **XML 구조** 창이 열립니다.  
  
10. 요소를 끌어는 **XML 구조** 문서에서 해당 컨트롤을 만들 위치를 창.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Visual Studio 내에서 워크시트에 스키마 매핑](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)   
 [문서 수준 사용자 지정의 XML 스키마 및 데이터](../vsto/xml-schemas-and-data-in-document-level-customizations.md)  
  
  