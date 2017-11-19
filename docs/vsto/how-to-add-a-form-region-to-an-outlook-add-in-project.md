---
title: "방법: Outlook 추가 기능 프로젝트에 양식 영역 추가 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VSTO.NewFormRegionWizard.Page1
- VSTO.NewFormRegionWizard.Page3
- VSTO.NewFormRegionWizard.Page2
- VSTO.NewFormRegionWizard.Page0
dev_langs:
- VB
- CSharp
helpviewer_keywords: form regions [Office development in Visual Studio], adding
ms.assetid: 49fa3d1e-1b8a-48be-95fb-35c59c4711f6
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b5074bae9d7f150f60af40c599cc0e61c9757679
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-form-region-to-an-outlook-add-in-project"></a>방법: Outlook 추가 기능 프로젝트에 양식 영역 추가
  **새 Outlook 양식 영역** 마법사를 사용하여 표준 또는 사용자 지정 Microsoft Office Outlook 양식을 확장하는 양식 영역을 만듭니다. Visual Studio에서 새 양식 영역을 만들어서 사용자 인터페이스를 디자인하거나 Outlook에서 디자인한 양식 영역을 가져와서 Visual Basic 또는 C# 코드를 추가할 수 있습니다.  
  
 다른 Outlook 프로젝트에서 사용한 Outlook 양식 영역이 있는 경우 **기존 항목 추가** 대화 상자를 사용하여 현재 Outlook VSTO 추가 기능 프로젝트에서 다시 사용할 수 있습니다. 자세한 내용은 [Creating Outlook Form Regions](../vsto/creating-outlook-form-regions.md)을 참조하세요.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
### <a name="to-add-a-new-form-region-to-an-outlook-project"></a>Outlook 프로젝트에 새 양식 영역을 추가하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 Outlook VSTO 추가 기능 프로젝트를 열거나 만듭니다. 자세한 내용은 [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하세요.  
  
2.  **솔루션 탐색기**에서 Outlook VSTO 추가 기능 프로젝트 노드를 선택합니다.  
  
3.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
4.  **새 항목 추가** 대화 상자에서 **Outlook 양식 영역**을 선택합니다.  
  
5.  **이름** 상자에서 양식 영역의 이름을 입력한 다음 **추가**를 클릭합니다.  
  
     **NewOutlook 양식 영역** 마법사가 시작 합니다.  
  
6.  **양식 영역을 만드는 방법 선택** 페이지에서 관리되는 컨트롤을 비주얼 디자이너에 끌어 놓고 양식 영역을 디자인할지 또는 Outlook에서 디자인한 양식 영역을 가져올지 선택합니다.  
  
    > [!NOTE]  
    >  Outlook에서 디자인한 양식 영역을 가져오는 방법을 선택하는 경우 Outlook 양식 저장 파일(.ofs)의 위치를 지정해야 합니다. Outlook에서 디자인하는 양식 영역에 관리되는 컨트롤을 추가할 수 없습니다. 코드는 기존 UI 뒤에만 추가할 수 있습니다. 자세한 내용은 [Creating Outlook Form Regions](../vsto/creating-outlook-form-regions.md)을 참조하세요.  
  
7.  **만들 양식 영역 형식 선택** 페이지에서 양식 영역 형식을 검토하고 하나를 선택한 후 **다음**을 클릭합니다. 양식 영역 형식에 대한 자세한 내용은 [Creating Outlook Form Regions](../vsto/creating-outlook-form-regions.md)를 참조하세요.  
  
8.  **설명 텍스트를 입력하고 디스플레이 기본 설정을 선택하세요.** 페이지의 **이름** 상자에 양식 영역에 대한 이름을 입력합니다. 대체 및 모두 대체 양식 영역 형식에는 **제목** 및 **설명** 상자를 사용할 수도 있습니다.  
  
     양식 영역을 배포할 때 Outlook에서 이름, 제목 및 설명이 표시되는 위치에 대한 자세한 내용은 [Creating Outlook Form Regions](../vsto/creating-outlook-form-regions.md)를 참조하세요.  
  
9. 양식 영역을 표시하려는 하나 이상의 디스플레이 모드를 선택합니다.  
  
     모든 양식 영역 형식은 검사기에 항목을 만들 때는 작성 모드로, 항목을 볼 때는 읽기 모드로 표시될 수 있습니다. 또한 인접, 대체 또는 모두 대체 양식 영역 형식이 읽기 창에 표시될 수 있습니다.  
  
10. **다음**을 클릭합니다.  
  
11. **이 양식 영역을 표시할 메시지 클래스를 지정하세요.** 페이지에서 표준 Outlook 메시지 클래스를 선택하거나 하나 이상의 사용자 지정 메시지 클래스의 이름을 입력한 다음 **마침**을 클릭합니다. 자세한 내용은 [Associating a Form Region with an Outlook Message Class](../vsto/associating-a-form-region-with-an-outlook-message-class.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [런타임에 양식 영역 액세스](../vsto/accessing-a-form-region-at-run-time.md)   
 [Outlook 솔루션](../vsto/outlook-solutions.md)   
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [Outlook 양식 영역 만들기 지침](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [연습: Outlook에서 디자인 한 양식 영역 가져오기](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)   
 [Outlook 양식 영역의 사용자 지정 작업](../vsto/custom-actions-in-outlook-form-regions.md)  
  
  