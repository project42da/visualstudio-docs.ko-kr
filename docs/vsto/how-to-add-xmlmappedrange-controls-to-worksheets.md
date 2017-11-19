---
title: "방법: 워크시트에 XMLMappedRange 컨트롤 추가 | Microsoft Docs"
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
- XMLMappedRange control, adding to worksheets
- controls [Office development in Visual Studio], adding to worksheets
ms.assetid: e1d4f2a8-1157-49c2-9158-a1253b709cb8
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0d83241e265db0e0ef0165cbc1615f23ea2ec5a2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-xmlmappedrange-controls-to-worksheets"></a>방법: 워크시트에 XMLMappedRange 컨트롤 추가
  Microsoft Office Excel의 셀에는 XML 요소를 매핑할 때 자동으로 추가 된 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤을 워크시트입니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤에서 사용할 수 없으면는 **도구 상자** 또는 **데이터 소스** 창. 만들 수 없습니다는 또한 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 프로그래밍 방식으로 제어 합니다.  
  
### <a name="to-add-an-xmlmappedrange-control-to-a-worksheet"></a>워크시트에 XMLMappedRange 컨트롤을 추가 하려면  
  
1.  Visual Studio 디자이너에서 Excel 통합 문서를 엽니다.  
  
2.  컨트롤을 추가 하려면 워크시트를 엽니다.  
  
3.  에 **개발자** 탭을 클릭 **소스**합니다.  
  
    > [!NOTE]  
    >  경우는 **개발자** 탭이 리본 메뉴에 표시 되지 않으면, 사용 하도록 설정 해야 합니다. 자세한 내용은 [How to: Show the Developer Tab on the Ribbon](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)을 참조하세요.  
  
     **XML 원본은** 작업창이 표시 됩니다.  
  
4.  에 **XML 원본은** 작업창에서 **XML 맵**합니다.  
  
5.  에 **XML 맵** 대화 상자를 클릭 **추가**합니다.  
  
     **XML 원본은** 대화 상자가 나타납니다.  
  
6.  XML 스키마를 선택는 **XML 원본은** 대화 상자와 클릭 **열려**합니다.  
  
     스키마에 추가 되는 **XML 맵** 대화 상자.  
  
7.  에 **XML 맵** 대화 상자를 클릭 **확인**합니다.  
  
8.  요소를 끌어 놓습니다는 **XML 원본은** 작업창 워크시트에서 셀을 합니다.  
  
     <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 생성 되어 프로젝트에 추가 합니다.  
  
    > [!NOTE]  
    >  부모 요소를 끌면는 **XML 원본은** 작업창은 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤이 만들어집니다.  
  
## <a name="see-also"></a>참고 항목  
 [XmlMappedRange 컨트롤](../vsto/xmlmappedrange-control.md)   
 [확장 된 개체를 사용 하 여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)   
 [Programmatic Limitations of Host Items and Host Controls](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [방법: Visual Studio 내에서 워크시트에 스키마 매핑](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)  
  
  