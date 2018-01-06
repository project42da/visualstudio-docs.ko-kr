---
title: "방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, XML
- customizing the Ribbon, XML
- Ribbon [Office development in Visual Studio], XML
- Ribbon [Office development in Visual Studio], exporting
- XML [Office development in Visual Studio], Ribbon
- Ribbon Designer [Office development in Visual Studio]
- exporting Ribbon
ms.assetid: 96e0e9ed-4392-4f45-ac33-b6f7c22ea321
caps.latest.revision: "37"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: d7cbdf38b3debd7710ed036d008d52b8ef080d37
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml"></a>방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기
  **리본 (비주얼 디자이너)** 항목은 가능한 모든 유형의 리본 메뉴 사용자 지정을 지원 하지 않습니다. 고급 방법으로 리본을 사용자 지정 디자이너에서 리본 XML로 리본 메뉴를 내보낼 수 있으며 XML을 직접 편집 키를 누릅니다.  
  
> [!NOTE]  
>  일부 속성 값은 리본 XML 파일에 나타납니다. 자세한 내용은 참조 [리본 개요](../vsto/ribbon-overview.md)합니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml"></a>리본 디자이너에서 리본 XML로 리본 메뉴를 내보내려면  
  
1.  리본 코드 파일을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기**, 클릭 하 고 **뷰 디자이너**합니다.  
  
2.  리본 디자이너를 마우스 오른쪽 단추로 누른 **XML로 리본 내보내기**합니다.  
  
     Visual Studio 프로젝트에 리본 XML 파일 및 리본 XML 코드 파일을 추가합니다.  
  
3.  리본 코드 클래스에서로 시작 하는 설명을 찾습니다 `TODO:`합니다.  
  
4.  이러한 메모에에 있는 코드 블록을 복사는 **ThisAddin**, **ThisWorkbook**, 또는 **ThisDocument** 개발 어떤 유형의 솔루션에 따른 클래스입니다.  
  
     이 코드는 Microsoft Office 응용 프로그램을 검색 하 고 사용자 지정 리본 메뉴를 로드할 수 있습니다. 자세한 내용은 [Ribbon XML](../vsto/ribbon-xml.md)을 참조하세요.  
  
5.  에 **ThisAddin**, **ThisWorkbook**, 또는 **ThisDocument** 클래스, 코드 블록의 주석 처리 제거 합니다.  
  
     코드 주석 처리를 제거한 후 다음 예제에서는 비슷해야 합니다. 이 예제에서는 리본 클래스 라고 `MyRibbon`합니다.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.cs#1)]
     [!code-vb[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.vb#1)]  
  
6.  리본 XML 코드 파일 전환 하 고 찾을 `Ribbon Callbacks` 영역입니다.  
  
     단추 클릭과 같은 사용자 동작을 처리 하는 콜백 메서드를 작성할 위치입니다.  
  
7.  디자이너에서 리본 코드에서 작성 하는 각 이벤트 처리기에 대 한 콜백 메서드를 만듭니다.  
  
8.  콜백 메서드를 이벤트 처리기의 모든 이벤트 처리기 코드를 이동 하 고 리본 확장성 (RibbonX) 프로그래밍 모델을 사용 하려면 코드를 수정 합니다.  
  
     콜백 메서드를 작성 하 고 RibbonX 프로그래밍 모델을 사용 하는 방법에 대 한 내용은 [리본 XML](../vsto/ribbon-xml.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [리본 XML](../vsto/ribbon-xml.md)   
 [연습: 리본 디자이너를 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [연습: 리본 XML을 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  