---
title: "Visual Studio Tools for the Microsoft Office System 프로젝트를 만들거나 열려면 우선 Microsoft Office Visual Basic for Applications 프로젝트에 대한 액세스를 명시적으로 활성화해야 합니다. | Microsoft Docs"
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
  - "vst.project.vbawrongversion"
  - "VST.Project.VBASecurityGenericError"
  - "VST.Project.VBASecurityPermissions"
  - "VST.SelectDocWizard.MissingCOM"
  - "VST.Project.VBASecurityNotSet"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 538021e6-1776-453d-9899-d7fca2f1f58f
caps.latest.revision: 19
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 18
---
# Visual Studio Tools for the Microsoft Office System 프로젝트를 만들거나 열려면 우선 Microsoft Office Visual Basic for Applications 프로젝트에 대한 액세스를 명시적으로 활성화해야 합니다.
  Office 개발 프로젝트에서는 Visual Basic for Applications를 사용하지 않더라도 Microsoft Office Word 및 Microsoft Office Excel에서 Visual Basic for Applications 프로젝트 시스템에 액세스할 수 있어야 합니다.  Visual Basic 및 C\# 프로젝트의 디자인 타임 컨트롤 지원은 Visual Basic for Applications 프로젝트 시스템에 따라 달라집니다.  
  
 일부 Microsoft Office 매크로 바이러스는 자신을 전파하기 위한 수단으로 Visual Basic for Applications 프로젝트 시스템을 자동화하려 할 수 있습니다.  Visual Basic for Applications 프로젝트 시스템에 액세스할 수 있도록 설정하는 순간 매크로 바이러스 확산을 방지할 수 있는 안전 기능이 작동하지 않게 되는 것입니다.  그러나 일반적인 매크로 보안은 계속 적용되므로 Office 응용 프로그램에 대해 유지 관리하는 신뢰할 수 있는 게시자 목록과 매크로 보안 수준을 통해 매크로를 컴퓨터에서 실행해도 되는지 여부가 결정됩니다.  
  
> [!NOTE]  
>  이 옵션은 개발 컴퓨터에만 적용됩니다.  최종 사용자 컴퓨터에서는 Office 솔루션을 실행하기 위해 이 옵션을 사용하도록 설정하지 않아도 됩니다.  
  
 Visual Basic for Applications 프로젝트 시스템에 액세스할 수 없도록 설정하는 것 자체만으로는 바이러스로부터 컴퓨터를 보호할 수 없으며, 컴퓨터가 매크로 바이러스에 감염되는 경우 일부 바이러스가 다른 문서로 확산되는 것을 중지할 수 있을 뿐입니다.  이 옵션은 컴퓨터에 대한 추가 보호 계층으로 기본적으로 사용하지 않도록 설정됩니다. 그러나 이 옵션을 사용하도록 설정해도 보안 모범 사례를 따르면 컴퓨터가 바이러스에 더 감염되기 쉬운 상태가 되지는 않습니다.  
  
 Office 매크로 바이러스를 가장 효율적으로 방지하는 방법은 Office를 높음 또는 매우 높음 보안 수준으로 실행하고, 확인된 알려진 출처의 매크로만 신뢰하고, 보안 패치 및 바이러스 스캐너를 사용하여 Office를 최신 상태로 유지하는 것입니다.  
  
 바이러스와 기타 악성 코드로부터 PC를 보호하는 방법에 대한 자세한 내용은 [http:\/\/www.microsoft.com\/protect](http://www.microsoft.com/protect)를 참조하세요.  
  
 **Visual Basic 프로젝트에 안전하게 액세스할 수 있음** 옵션을 수동으로 사용하거나 사용하지 않도록 설정할 수 있습니다.  
  
 VBA 또는 COM 오류가 발생하는 경우에는 Office 설치를 복구할 수 있습니다.  
  
### Visual Basic 프로젝트에 액세스하거나 할 수 없도록 설정하려면  
  
1.  Word 또는 Excel의 **도구** 메뉴에서 **매크로**를 가리킨 다음 **보안**을 클릭합니다.  
  
2.  **보안** 대화 상자에서 **신뢰할 수 있는 게시자** 탭을 클릭합니다.  
  
3.  **Visual Basic 프로젝트에 안전하게 액세스할 수 있음**을 선택하여 사용하도록 설정하거나 선택을 취소하여 사용하지 않도록 설정합니다.  
  
4.  **확인**을 클릭합니다.  
  
### Office 매크로 보안 수준을 설정하려면  
  
1.  Word 또는 Excel의 **도구** 메뉴에서 **매크로**를 가리킨 다음 **보안**을 클릭합니다.  
  
2.  **보안 수준** 탭에서 원하는 설정을 선택합니다.  
  
     **보안 수준** 탭에는 각 수준에 대한 세부 정보가 포함되어 있습니다.  자세한 내용은 Office 도움말에서 "매크로 보안 수준" 항목을 참조하세요.  
  
### 2007 Microsoft Office system과 함께 VBA를 설치하려면  
  
1.  제어판에서 **프로그램 추가\/제거** 또는 **프로그램 및 기능**을 실행합니다.  
  
2.  **현재 설치된 프로그램** 목록에서 Office를 선택합니다.  
  
3.  **변경**을 클릭합니다.  
  
4.  **기능 추가\/제거**를 선택하고 **계속**을 클릭합니다.  
  
5.  **응용 프로그램의 고급 사용자 지정을 선택하십시오.**를 선택하고 **다음**을 클릭합니다.  
  
6.  **응용 프로그램 및 도구에 대한 업데이트 옵션을 선택하십시오.** 목록에서 **Office 공유 기능**을 확장합니다.  
  
7.  **Visual Basic for Applications** 옆의 드롭다운 메뉴를 열고 **내 컴퓨터에서 실행**을 클릭합니다.  
  
8.  **계속**을 클릭합니다.  
  
9. **닫기**를 클릭합니다.  
  
### Office 설치를 복구하려면  
  
1.  제어판에서 **프로그램 추가\/제거** 또는 **프로그램 및 기능**을 실행합니다.  
  
2.  **현재 설치된 프로그램** 목록에서 사용 중인 Office 버전을 선택합니다.  
  
3.  **변경**을 클릭합니다.  
  
4.  **다시 설치 또는 복구**를 선택하고 **다음**을 클릭합니다.  
  
5.  **설치한 Office에서 오류 검색 및 복구**를 선택하고 **설치**를 클릭합니다.  
  
## 참고 항목  
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)  
  
  