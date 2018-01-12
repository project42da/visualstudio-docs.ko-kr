---
title: "방법: 리본 메뉴 사용자 지정 시작 | Microsoft Docs"
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
- custom Ribbon, adding Ribbon to project
- Ribbon [Office development in Visual Studio], adding
- Ribbon [Office development in Visual Studio], customizing
- customizing the Ribbon, adding Ribbon to project
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6856ca88f6f8d0b6d0c983da2ee068e5618964b9
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-get-started-customizing-the-ribbon"></a>방법: 리본 메뉴 사용자 지정 시작
  Microsoft Office 응용 프로그램의 리본을 사용자 지정 하려면 추가 **리본 (비주얼 디자이너)** 또는 **리본 (XML)** 을 Office 프로젝트 항목입니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-add-a-ribbon-to-a-project"></a>프로젝트에 리본 메뉴를 추가 하려면  
  
1.  에 **프로젝트** 메뉴를 클릭 하 여 **새 항목 추가**합니다.  
  
2.  에 **새 항목 추가** 대화 상자에서 **리본 (비주얼 디자이너)** 또는 **리본 (XML)**합니다. 이러한 서식 파일에 대 한 자세한 내용은 참조 [리본 개요](../vsto/ribbon-overview.md)합니다.  
  
3.  에 **이름** 리본 항목에 대 한 이름을 입력 합니다.  
  
     이름은 다음 문자를 포함할 수 없습니다.  
  
    -   파운드 (#)  
  
    -   백분율 (%)  
  
    -   앰퍼샌드 (&)  
  
    -   *(별표)  
  
    -   세로 막대(|)  
  
    -   백슬래시(\\)  
  
    -   콜론 (:)  
  
    -   큰따옴표(")  
  
    -   보다 작은 (\<)  
  
    -   보다 큼(>)  
  
    -   물음표(?)  
  
    -   슬래시 (/)  
  
    -   선행 또는 후행 공백 (' ')  
  
    -   ("Nul", "aux", "con", "com1", "lpt1" 등)와 같은 Windows 또는 DOS에 대해 예약 된 이름  
  
4.  **확인**을 클릭합니다.  
  
 에 리본 항목을 표시할지 **솔루션 탐색기**합니다. 다음 단계에 대 한 정보를 참조 하십시오. [리본 개요](../vsto/ribbon-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Accessing the Ribbon at Run Time](../vsto/accessing-the-ribbon-at-run-time.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [리본 XML](../vsto/ribbon-xml.md)   
 [연습: 리본 디자이너를 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [연습: 리본 XML을 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  