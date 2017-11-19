---
title: "방법: Backstage 보기에 컨트롤 추가 | Microsoft Docs"
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
- customizing the Ribbon, menus
- controls, Ribbon
- menus, customizing
- Microsoft Office Button
- custom Ribbon, menus
- Ribbon, customizing
- Office button
- Ribbon, menus
- Microsoft Office Menu
ms.assetid: 4fda1278-9aea-4d54-928a-269a81584494
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7a16c564b39afdc2ec3cf3e15883fc05b2a13f5d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-controls-to-the-backstage-view"></a>방법: Backstage 보기에 컨트롤 추가
  리본 디자이너를 사용 하 여 컨트롤을 클릭할 때 열리는 메뉴에 추가 하 고 **파일** 탭 컨트롤에 추가 하는 응용 프로그램을 실행 하면는 **파일** 라는 그룹 탭이 나타나지  **추가 기능**합니다.  
  
 Visual Studio에서 리본 디자이너를 사용 하 여 기본 제공 컨트롤 전후 컨트롤을 배치할 수 없습니다. 기본 제공 컨트롤에는 이미 Backstage 보기에 표시 되는 컨트롤이입니다. 기본 제공 컨트롤 전후 컨트롤을 배치 하려는 경우 리본 XML을 사용 해야 합니다. 에 대 한 자세한 내용은 **리본 (XML)**, 참조 [리본 XML](../vsto/ribbon-xml.md)합니다. Backstage 보기 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 [개발자를 위한 Office 2010 Backstage 보기 소개](http://go.microsoft.com/fwlink/?LinkId=182189) 및 [개발자를 위한 Office 2010 Backstage 보기 사용자 지정](http://go.microsoft.com/fwlink/?LinkId=182188)합니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-add-controls-to-backstage-view"></a>Backstage 보기에 컨트롤을 추가 하려면  
  
1.  디자인 뷰에서 리본 항목을 엽니다.  
  
     추가 하는 방법에 대 한 내용은 **리본 (비주얼 디자이너)** 프로젝트에 항목을 참조 [하는 방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)합니다.  
  
2.  리본 디자이너에서 클릭 하 고 **파일** 탭 합니다.  
  
     메뉴 디자이너가 나타납니다. 이 디자인 화면에 컨트롤이 들어 있지 않습니다.  
  
3.  **Office 리본 컨트롤** 탭은 **도구 상자**, 메뉴 디자이너로 끌어 다음 컨트롤 중 하나:  
  
    -   단추  
  
    -   CheckBox  
  
    -   갤러리  
  
    -   메뉴  
  
    -   구분 기호  
  
    -   SplitButton  
  
    -   ToggleButton  
  
4.  컨트롤을 끌어 메뉴에서 새 위치로 이동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [리본 XML](../vsto/ribbon-xml.md)   
 [방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [연습: 리본 디자이너를 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)  
  
  