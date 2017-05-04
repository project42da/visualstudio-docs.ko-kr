---
title: "방법: 주 Interop 어셈블리를 통한 Office 응용 프로그램 대상 선택 | Microsoft Docs"
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
  - "응용 프로그램 개발[Visual Studio에서 Office 개발], 자동화"
  - "어셈블리[Visual Studio에서 Office 개발], PIA 참조"
  - "Office 응용 프로그램[Visual Studio에서 Office 개발], 자동화"
  - "Visual Studio의 Office 주 interop 어셈블리, 참조 추가"
  - "주 interop 어셈블리[Visual Studio에서 Office 개발], 참조 추가"
ms.assetid: 9bedae85-32b6-4df6-82b2-9d124fb49636
caps.latest.revision: 40
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 39
---
# 방법: 주 Interop 어셈블리를 통한 Office 응용 프로그램 대상 선택
  새 Office 프로젝트를 만들 때 Visual Studio는 프로젝트를 빌드하는 데 필요한 Microsoft Office PIA\(주 interop 어셈블리\)에 대한 참조를 자동으로 추가합니다.  다음과 같은 시나리오에서는 다른 PIA에 대한 참조를 추가해야 합니다.  
  
-   프로젝트에서 다른 Microsoft Office 응용 프로그램의 기능을 사용하려고 합니다.  예를 들어 Microsoft Office Word용 프로젝트에서 Microsoft Office Excel의 기능을 사용할 수 있습니다.  
  
-   Microsoft Office Access와 같이 Visual Studio에 전용 프로젝트가 없는 Microsoft Office 응용 프로그램을 자동화하려고 합니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### 주 interop 어셈블리에 대한 참조를 추가하려면  
  
1.  Office 프로젝트를 열고 **솔루션 탐색기**에서 프로젝트 이름을 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.  
  
3.  **프레임워크** 탭의 **구성 요소 이름** 목록에서 원하는 PIA를 선택합니다.  사용 가능한 Microsoft Office 주 Interop 어셈블리에 대한 자세한 내용은 [Office 주 Interop 어셈블리](../vsto/office-primary-interop-assemblies.md)를 참조하세요.  
  
     프로젝트가 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 경우 어셈블리 참조에 대한 **Interop 형식 포함** 속성이 기본적으로 **True**로 설정됩니다.  이 설정을 사용하면 최종 사용자 컴퓨터에서 솔루션에 PIA가 필요하지 않습니다.  자세한 내용은 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)를 참조하세요.  
  
    > [!NOTE]  
    >  Office 프로젝트에서 **COM** 탭 대신 항상 **참조 추가** 대화 상자의 **.NET** 탭을 사용하여 Office PIA에 대한 참조를 추가합니다.  자세한 내용은 [Office 주 Interop 어셈블리](../vsto/office-primary-interop-assemblies.md)를 참조하세요.  
  
4.  **확인**을 클릭합니다.  
  
     어셈블리 이름이 **솔루션 탐색기**의 **참조** 폴더에 나타납니다.  
  
## 참고 항목  
 [Office 주 Interop 어셈블리](../vsto/office-primary-interop-assemblies.md)   
 [Office 솔루션에서 코드 작성](../vsto/writing-code-in-office-solutions.md)   
 [Office 솔루션 개발](../vsto/developing-office-solutions.md)   
 [방법: Office 주 Interop 어셈블리 설치](../vsto/how-to-install-office-primary-interop-assemblies.md)  
  
  