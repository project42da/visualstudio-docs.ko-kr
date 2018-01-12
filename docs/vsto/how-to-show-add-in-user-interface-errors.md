---
title: "방법: 추가 기능 사용자 인터페이스 오류 표시 | Microsoft Docs"
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
- add-ins [Office development in Visual Studio], user interface errors
- errors [Office development in Visual Studio], user interface errors
- user interfaces [Office development in Visual Studio], errors
- application-level add-ins [Office development in Visual Studio], user interface errors
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4ce5204855cd6ebe468d652b8420cddc7fd19a1a
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-show-add-in-user-interface-errors"></a>방법: 추가 기능 사용자 인터페이스 오류 표시
  기본적으로 VSTO 추가 기능은 Microsoft Office UI(사용자 인터페이스) 조작이 실패한 경우 오류 메시지를 표시하지 않습니다. 그러나 UI에 관련된 오류에 대한 메시지를 표시하도록 Microsoft Office 응용 프로그램을 구성할 수 있습니다. 이러한 메시지를 사용하여 사용자 지정 리본이 나타나지 않는 이유 또는 리본이 나타나지만 컨트롤이 표시되지 않는 이유를 확인할 수 있습니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-show-vsto-add-in-user-interface-errors"></a>VSTO 추가 기능 사용자 인터페이스 오류를 표시하려면  
  
1.  응용 프로그램을 시작합니다.  
  
2.  **파일** 탭을 클릭합니다.  
  
3.  **옵션**을 클릭합니다.  
  
4.  범주 창에서 **고급**을 클릭합니다.  
  
5.  세부 정보 창에서 **VSTO 추가 기능 사용자 인터페이스 오류 표시**를 선택하고 **확인**을 클릭합니다.  
  
    > [!NOTE]  
    >  Outlook의 경우 세부 정보 창의 **개발자** 섹션에 **VSTO 추가 기능 사용자 인터페이스 오류 표시** 확인란이 있습니다. 다른 응용 프로그램의 경우 이 확인란은 세부 정보 창의 **일반** 섹션에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Office UI 사용자 지정](../vsto/office-ui-customization.md)   
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [리본 개요](../vsto/ribbon-overview.md)   
 [작업창 개요](../vsto/actions-pane-overview.md)  
  
  