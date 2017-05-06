---
title: "방법: Visual Studio에서 Office 프로젝트 만들기"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VST.SelectDocWizard.Page1"
  - "VST.SelectDocWizard.Http"
  - "VST.SelectDocWizard.Extension"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "추가 기능[Visual Studio에서 Office 개발], 프로젝트 만들기"
  - "응용 프로그램 수준 추가 기능[Visual Studio에서 Office 개발], 프로젝트 만들기"
  - "문서 수준 사용자 지정[Visual Studio에서 Office 개발], 만들기"
  - "Office 응용 프로그램[Visual Studio에서 Office 개발], 만들기"
  - "Office 프로젝트[Visual Studio에서 Office 개발]"
  - "프로젝트[Visual Studio에서 Office 개발], 만들기"
ms.assetid: 0037dbd8-0d2a-4766-90ea-81c819379582
caps.latest.revision: 96
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 95
---
# 방법: Visual Studio에서 Office 프로젝트 만들기
  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 사용하여 Microsoft Office 응용 프로그램에 대한 VSTO 추가 기능과 문서 수준 사용자 지정을 만들 수 있습니다. 이들 형식 프로젝트에 대한 자세한 내용은 [Office 솔루션 개발 개요&#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)를 참조하세요.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### VSTO 추가 기능 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택합니다.  IDE\(통합 개발 환경\)가 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] 개발 설정을 사용하도록 설정되면 **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
    > [!NOTE]  
    >  기본적으로 Office 프로젝트는 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]을\(를\) 대상으로 합니다.  자세한 내용은 [.NET Framework Client Profile](http://msdn.microsoft.com/library/f0219919-1f02-4588-8704-327a62fd91f1)를 참조하세요.  
  
2.  템플릿 창에서 사용할 언어 노드 아래에 있는 **Office\/SharePoint**를 확장합니다.  
  
3.  **Office 추가 기능** 노드를 선택합니다.  
  
4.  프로젝트 템플릿 목록에서 VSTO 추가 기능 프로젝트 템플릿을 선택합니다.  사용 가능한 VSTO 추가 기능 프로젝트 템플릿 목록을 보려면 [Office 프로젝트 템플릿 개요](../vsto/office-project-templates-overview.md)를 참조하세요.  
  
    > [!NOTE]  
    >  **Office 추가 기능** 노드를 선택할 때 프로젝트 템플릿이 표시되지 않으면 대화 상자 위쪽에 있는 콤보 상자에서 **.NET Framework 4** 이상이 선택되었는지 확인합니다.  두 .NET Framework 버전에 대해 모두 Office 프로젝트 템플릿이 표시됩니다.  
  
5.  **이름** 상자에 프로젝트 이름을 입력합니다.  기본적으로 프로젝트 이름은 솔루션 이름으로도 사용됩니다.  
  
6.  **위치** 상자에 프로젝트를 만들 경로를 입력합니다.  절대 경로와 UNC\(범용 명명 규칙\) 경로를 사용할 수 있습니다.  HTTP, FTP 또는 기타 프로토콜 경로 사용하지 마세요.  
  
     위치 형식은 다음과 같습니다.  
  
    -   \[*drive*\]:\\  
  
    -   \\\\*Server*\\*Share*  
  
     위치에 다음 문자를 사용하지 마세요.  
  
    -   \*\(별표\)  
  
    -   세로 막대\(|\)  
  
    -   콜론\(:\)\(드라이브 문자 뒤에는 제외\)  
  
    -   큰따옴표\("\)\(공백이 포함된 경로에는 따옴표가 필요하지 않음\)  
  
    -   보다 작음\(\<\)  
  
    -   보다 큼\(\>\)  
  
    -   물음표\(?\)  
  
    -   백분율 기호\(%\)  
  
7.  **확인** 단추를 선택합니다.  
  
    > [!NOTE]  
    >  추가 기능 프로젝트는 생성될 때 항상 저장됩니다.  이 프로젝트를 임시 프로젝트로 만들 수 없습니다.  임시 프로젝트에 대한 자세한 내용은 [임시 프로젝트](http://msdn.microsoft.com/ko-kr/9cf1944c-7045-44cc-8701-7b0eb4099f2b)를 참조하세요.  
  
### 문서 수준 사용자 지정 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택합니다.  IDE가 Visual Basic 개발 설정을 사용하도록 설정되면 **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
    > [!NOTE]  
    >  기본적으로 Office 프로젝트는 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]을\(를\) 대상으로 합니다.  자세한 내용은 [.NET Framework Client Profile](http://msdn.microsoft.com/library/f0219919-1f02-4588-8704-327a62fd91f1)를 참조하세요.  
  
2.  템플릿 창에서 사용할 언어 노드 아래에 있는 **Office\/SharePoint**를 확장합니다.  
  
3.  **Office 추가 기능** 노드를 선택합니다.  
  
4.  프로젝트 템플릿 목록에서 문서 수준 프로젝트 템플릿을 선택합니다.  사용 가능한 문서 수준 프로젝트 템플릿 목록을 보려면 [Office 프로젝트 템플릿 개요](../vsto/office-project-templates-overview.md)를 참조하세요.  
  
    > [!NOTE]  
    >  **Office 추가 기능** 노드를 선택할 때 프로젝트 템플릿이 표시되지 않으면 대화 상자 위쪽에 있는 콤보 상자에서 **.NET Framework 4** 이상이 선택되었는지 확인합니다.  두 .NET Framework 버전에 대해 모두 Office 프로젝트 템플릿이 표시됩니다.  
  
5.  **이름** 상자에 프로젝트 이름을 입력합니다.  기본적으로 이 이름은 문서에도 사용됩니다.  IDE가 Visual C\# 개발 설정이나 일반 개발 설정을 사용하도록 설정되면 위치 및 솔루션 이름도 입력합니다.  
  
    > [!NOTE]  
    >  프로젝트 위치 경로 또는 프로젝트 이름에는 서로게이트 문자를 사용할 수 없습니다.  서로게이트 문자에 대한 자세한 내용은 [NIB: Unicode Support for Surrogate Pairs and Combining Character Sequences](http://msdn.microsoft.com/ko-kr/cba3285c-7b47-4ce8-8970-f48d6ac03e39)을 참조하세요.  솔루션을 오프라인에서 사용하도록 배포하려면 프로젝트 이름의 문자가 HTTP 프로토콜 사양에 맞아야 합니다.  
  
6.  **확인** 단추를 선택합니다.  
  
     **Visual Studio Tools for Office 프로젝트 마법사**가 열립니다.  
  
7.  솔루션에 대한 새 문서를 만들려면 **새 문서 만들기**를 선택하고, 기존 문서를 사용자 지정하려면 **기존 문서 복사**를 선택합니다.  
  
     새 문서를 만들 경우 **이름** 상자에 이름을 지정하고 **형식** 상자를 사용하여 문서 형식을 선택합니다.  사용 가능한 형식에 대한 자세한 내용은 [문서 수준 사용자 지정 아키텍처](../vsto/architecture-of-document-level-customizations.md)를 참조하세요.  
  
     기존 문서를 사용할 경우 **기존 문서의 전체 경로** 상자에서 문서 위치를 지정합니다.  절대 경로와 UNC 경로를 사용할 수 있습니다.  문서에 대한 HTTP, FTP 또는 기타 프로토콜 경로 사용하지 마세요.  
  
     위치 형식은 다음과 같습니다.  
  
    -   \[*drive*\]:\\  
  
    -   \\\\*Server*\\*Share*  
  
     위치에 다음 문자를 사용하지 마세요.  
  
    -   \*\(별표\)  
  
    -   세로 막대\(|\)  
  
    -   콜론\(:\)\(드라이브 문자 뒤에는 제외\)  
  
    -   큰따옴표\("\)\(공백이 포함된 경로에는 따옴표가 필요하지 않음\)  
  
    -   보다 작음\(\<\)  
  
    -   보다 큼\(\>\)  
  
    -   물음표\(?\)  
  
    -   백분율 기호\(%\)  
  
    > [!NOTE]  
    >  [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] 프로젝트에서 기존 문서를 사용할 경우 [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]에서 생성되거나 해당 항목으로 변환된 문서만 사용하세요.  마찬가지로 Word 2010 프로젝트의 기존 문서를 사용할 경우 Word 2010에서 생성되거나 해당 항목으로 변환된 문서만 사용하세요.  이전 버전 Word에서 생성된 문서를 사용하면 문서에서 특정 기능이 사용하지 않도록 설정됩니다.  이들 기능을 사용하는 코드를 작성하려고 하면 프로젝트에서 오류가 발생할 수 있습니다.  문서를 변환하려면 [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] 또는 Word 2010에서 문서를 열고 기본의 **파일** 탭에서 **정보**, **변환**을 차례로 선택합니다.  
  
8.  **마침**을 선택합니다.  
  
9. 다음 경우에 Word의 보안 센터에 있는 신뢰할 수 있는 위치 목록에 프로젝트 폴더와 하위 폴더를 추가합니다.  
  
    -   .docm 파일을 기반으로 Word 문서를 만들고 있고 문서가 VBA 프로젝트를 포함하거나 Windows Forms 컨트롤을 호스트합니다.  신뢰할 수 있는 위치 목록에 프로젝트 폴더를 추가하면 디자인 타임에 문서가 예상대로 작동하는지 확인할 수 있습니다.  
  
    -   .dotx 파일을 기반으로 Word 템플릿 프로젝트를 만들고 있습니다.  프로젝트를 실행하고 디버그할 수 있도록 신뢰할 수 있는 위치 목록에 프로젝트 폴더를 추가해야 합니다.  
  
     신뢰할 수 있는 위치에 문서를 추가하는 방법에 대한 자세한 내용은 Microsoft Office Online 웹 사이트 [파일을 저장할 신뢰할 수 있는 위치 만들기, 제거 또는 변경](https://support.office.com/en-au/article/Create-remove-or-change-a-trusted-location-for-your-files-f5151879-25ea-4998-80a5-4208b3540a62)을 참조하세요.  
  
## 참고 항목  
 [Office 프로젝트 템플릿 개요](../vsto/office-project-templates-overview.md)   
 [Office 솔루션 공동 개발](../vsto/collaborative-development-of-office-solutions.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)   
 [VSTO 추가 기능 프로그래밍 시작](../vsto/getting-started-programming-vsto-add-ins.md)  
  
  