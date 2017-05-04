---
title: "프로젝트 솔루션 | Microsoft Docs"
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
  - "프로젝트[Visual Studio에서 Office 개발], Project"
  - "Office 솔루션[Visual Studio에서 Office 개발], Project"
  - "프로젝트[Visual Studio에서 Office 개발]"
  - "템플릿[Visual Studio에서 Office 개발], Project"
  - "Office 프로젝트[Visual Studio에서 Office 개발], Project"
  - "솔루션[Visual Studio에서 Office 개발], Project"
ms.assetid: 4ce92269-eb6d-44aa-bee3-6d38ec9995f9
caps.latest.revision: 34
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 30
---
# 프로젝트 솔루션
  [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]에서는 Microsoft Office Project용 VSTO 추가 기능을 만드는 데 사용할 수 있는 프로젝트 템플릿을 제공합니다. VSTO 추가 기능을 사용하여 Project를 자동화하거나 Project 기능을 확장하거나 Project UI\(사용자 인터페이스\)를 사용자 지정할 수 있습니다.  
  
 VSTO 추가 기능에 대한 자세한 내용은 [VSTO 추가 기능 프로그래밍 시작](../vsto/getting-started-programming-vsto-add-ins.md) 및 [VSTO 추가 기능의 아키텍처](../vsto/architecture-of-vsto-add-ins.md)를 참조하세요. Microsoft Office를 사용한 프로그래밍을 처음 접하는 경우 [시작&#40;Visual Studio에서의 Office 개발&#41;](../vsto/getting-started-office-development-in-visual-studio.md)를 참조하세요.  
  
 [!INCLUDE[appliesto_projallapp](../vsto/includes/appliesto-projallapp-md.md)]  
  
## 프로젝트 개체 모델을 사용하여 프로젝트 자동화  
 Project 개체 모델은 Project 자동화에 사용할 수 있는 다양한 형식을 노출합니다. 이러한 형식을 사용하면 프로젝트에서 프로그래밍 방식으로 작업을 만들고 수정하는 등의 일반 작업을 수행하도록 코드를 작성할 수 있습니다.  
  
 VSTO 추가 기능에서 Project 개체 모델에 액세스하려면 프로젝트에서 `ThisAddIn` 클래스의 `Application` 필드를 사용합니다.`Application` 필드는 Project의 현재 인스턴스를 나타내는 Microsoft.Office.Interop.MsProject.Application  개체를 반환합니다. 자세한 내용은 [VSTO 추가 기능 프로그래밍](../vsto/programming-vsto-add-ins.md)을 참조하세요.  
  
 Project 개체 모델을 호출할 때 Project의 주 Interop 어셈블리에서 제공되는 형식을 사용합니다. 주 interop 어셈블리는 VSTO 추가 기능의 관리 코드와 Project의 COM 개체 모델 간의 다리 역할을 합니다. Project 주 interop 어셈블리의 모든 형식은 Microsoft.Office.Interop.MSProject 네임스페이스에서 정의됩니다. 주 interop 어셈블리에 대한 자세한 내용은 [Office 솔루션 개발 개요&#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md) 및 [Office 주 Interop 어셈블리](../vsto/office-primary-interop-assemblies.md)를 참조하세요.  
  
## Project 개체 모델 설명서 사용  
 Project 개체 모델에 대한 자세한 내용은 Project VBA 개체 모델 참조를 참조하세요. VBA 개체 모델 참조에서는 VBA\(Visual Basic for Applications\) 코드로 표시되는 Project 개체 모델에 대해 설명합니다. 자세한 내용은 [Project 2010 개체 모델 참조](http://go.microsoft.com/fwlink/?LinkId=199771)를 참조하세요.  
  
 VBA 개체 모델 참조의 모든 개체 및 멤버는 Project PIA\(주 interop 어셈블리\)의 형식 및 멤버에 해당합니다. 예를 들어 VBA 개체 모델 참조의 Calendar 개체는 Project PIA의 Microsoft.Office.Interop.MSProject.Calendar 형식에 해당합니다. VBA 개체 모델 참조에서는 대부분의 속성, 메서드 및 이벤트에 대한 코드 예제를 제공하지만 Visual Studio를 사용하여 만든 Project VSTO 추가 기능 프로젝트에서 사용하려면 이 참조의 VBA 코드를 Visual Basic 또는 Visual C\#으로 변환해야 합니다.  
  
> [!NOTE]  
>  이번에는 Project 주 interop 어셈블리에 대한 참조 설명서가 없습니다.  
  
### Project 주 Interop 어셈블리의 인프라 형식  
 Project PIA를 사용하는 코드를 작성할 때 VBA 참조에서 설명되지 않은 여러 형식을 알게 될 수 있습니다. 이러한 추가 형식은 Project의 COM 기반 개체 모델의 개체를 관리 코드로 변환할 수 있도록 지원하지만 코드에서 직접 사용하려는 것은 아닙니다.  
  
 자세한 내용은 [Office 주 Interop 어셈블리의 클래스 및 인터페이스 개요](http://go.microsoft.com/fwlink/?LinkId=189592)를 참조하세요.  
  
## Project의 사용자 인터페이스 사용자 지정  
 다음과 같은 방법으로 Project UI를 사용자 지정할 수 있습니다.  
  
|작업|추가 정보|  
|--------|-----------|  
|Project에서 리본에 사용자 지정 탭을 추가합니다.|[리본 개요](../vsto/ribbon-overview.md)|  
  
 Project 및 기타 Microsoft Office 응용 프로그램 UI의 사용자 지정에 대한 자세한 내용은 [Office UI 사용자 지정](../vsto/office-ui-customization.md)를 참조하세요.  
  
## 참고 항목  
 [연습: Project용 첫 VSTO 추가 기능 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)   
 [VSTO 추가 기능 프로그래밍 시작](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Office 솔루션 개발 개요&#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [VSTO 추가 기능의 아키텍처](../vsto/architecture-of-vsto-add-ins.md)   
 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [VSTO 추가 기능 프로그래밍](../vsto/programming-vsto-add-ins.md)   
 [Office 솔루션에서 코드 작성](../vsto/writing-code-in-office-solutions.md)   
 [Office 주 Interop 어셈블리](../vsto/office-primary-interop-assemblies.md)   
 [Office UI 사용자 지정](../vsto/office-ui-customization.md)   
 [Office 개발의 Project 2010 및 Project Server 2010](http://go.microsoft.com/fwlink/?LinkId=199016)  
  
  