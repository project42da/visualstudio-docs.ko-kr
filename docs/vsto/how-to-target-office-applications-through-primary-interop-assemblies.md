---
title: "방법: 주 Interop 어셈블리를 통해 Office 응용 프로그램 대상 | Microsoft Docs"
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
- assemblies [Office development in Visual Studio], PIA references
- primary interop assemblies [Office development in Visual Studio], adding references to
- Office primary interop assemblies in Visual Studio, adding references to
- Office applications [Office development in Visual Studio], automating
- application development [Office development in Visual Studio], automating
ms.assetid: 9bedae85-32b6-4df6-82b2-9d124fb49636
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9a96ec16afda8823ddf9918340498e29efdff2f0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-target-office-applications-through-primary-interop-assemblies"></a>How to: Target Office Applications Through Primary Interop Assemblies
  새 Office 프로젝트를 만들 때 Visual Studio는 프로젝트를 빌드하는 데 필요한 Microsoft Office PIA(주 interop 어셈블리)에 대한 참조를 자동으로 추가합니다. 다음과 같은 시나리오에서는 다른 PIA에 대한 참조를 추가해야 합니다.  
  
-   프로젝트에서 다른 Microsoft Office 응용 프로그램의 기능을 사용하려고 합니다. 예를 들어 Microsoft Office Word용 프로젝트에서 Microsoft Office Excel의 기능을 사용할 수 있습니다.  
  
-   Microsoft Office Access와 같이 Visual Studio에 전용 프로젝트가 없는 Microsoft Office 응용 프로그램을 자동화하려고 합니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-to-a-primary-interop-assembly"></a>주 interop 어셈블리에 대한 참조를 추가하려면  
  
1.  프로젝트 이름을 선택 하 고 Office 프로젝트를 열고 **솔루션 탐색기**합니다.  
  
2.  **프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.  
  
3.  에 **프레임 워크** 탭에서 원하는 PIA를 선택 합니다는 **구성 요소 이름을** 목록입니다. 사용 가능한 Microsoft Office 주 interop 어셈블리에 대 한 자세한 내용은 참조 [Office 주 Interop 어셈블리](../vsto/office-primary-interop-assemblies.md)합니다.  
  
     하는 경우 프로젝트 대상의 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상에서는 **Interop 형식 포함** 어셈블리 참조에 대 한 속성이로 설정 되어 **True** 기본적으로 합니다. 이 설정을 사용하면 최종 사용자 컴퓨터에서 솔루션에 PIA가 필요하지 않습니다. 자세한 내용은 [Designing and Creating Office Solutions](../vsto/designing-and-creating-office-solutions.md)을 참조하세요.  
  
    > [!NOTE]  
    >  Office 프로젝트에서 항상 추가 Office Pia에 대 한 참조를 사용 하 여는 **.NET** 탭은 **참조 추가** 대화 보다는 **COM** 탭 합니다. 자세한 내용은 [Office 주 Interop 어셈블리](../vsto/office-primary-interop-assemblies.md)를 참조하세요.  
  
4.  **확인**을 클릭합니다.  
  
     어셈블리 이름에 표시 된 **참조** 의 폴더 **솔루션 탐색기**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Office 주 Interop 어셈블리](../vsto/office-primary-interop-assemblies.md)   
 [Office 솔루션에서 코드 작성](../vsto/writing-code-in-office-solutions.md)   
 [Office 솔루션 개발](../vsto/developing-office-solutions.md)   
 [방법: Office 주 Interop 어셈블리 설치](../vsto/how-to-install-office-primary-interop-assemblies.md).  
  
  